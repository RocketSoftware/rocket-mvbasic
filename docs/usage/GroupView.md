## Using Auto Group View

### Introduction

The auto-group view function is used to combine files that have similar names into groups. This allows you to organize file lists with more concise groupings. You can also customize group content and hide unnecessary files.

### Configuration

You can specify source code directories and add customized groups by modifying the configuration file. If no customized groups are added, a default rule will be used instead. Note that this default rule can also be changed.

If a source code directory is not specified, the current opened folder will be used as the source code directory. Folders will not be displayed in the group view unless they are specified as source directories.

Group view related settings are set from the "groupView" section of the configuration file. 

If you make changes to the configuration file, refresh the group view to make the change take effect.

### Ignore files list

You can specify which files to ignore (not be displayed in the group view) from the "ignore" section in "groupView".

Here is a sample configuration:

```
"ignore": [
    "VOC", 
    "D_*", 
    "BP/SAMPLE"
]
```

The following file specification methods can be used in the "ignore" section:

- File names: for example, "VOC", "D_VOC". 
- Using the wildcard character: for example, "D**" specifies that all files that start with "D*" in the current directory will be ignored.
- Using a relative path: for example, if the current opened folder is "C:\U2\UV\XDEMO", then "BP/SAMPLE" specifies that "C:\U2\UV\XDEMO\BP\SAMPLE" will not be displayed in the group view. Note that in this example, "BP" should be configured as the source code folder.

### Default auto-group rule

If you do not add customized groups in the configuration file, the auto-group view function will use a default rule to organize the files and create groups in current opened folder.

Here is the `default` configuration:

```
"default": {
    "delimiter": ".", 
    "level": 2
}
```

`delimiter` specifies the character(s) to use to separate the file names. For example, if specifying the "." delimiter, the file "SAMPLE.BASIC.PROGRAM" is separated to 3 parts: "SAMPLE", "BASIC" and "PROGRAM". 

Both single character and multiple character delimiters are supported in "delimiter", but for readability, we recommend using only single character.

`level` specifies how to combine group names based on the separated parts of the file names. 

For example, there are three files: "SAMPLE.BASIC.FILE", "SAMPLE.BASIC.CODE" and "SAMPLE.BASIC.PROGRAM". These three files all have a uniform file name format in the first two parts of the files: "SAMPLE.BASIC".

These can be placed into one group. 

If "level" is set to 2, then these will be placed into the group "SAMPLE.BASIC". If "level" is set to 1, then these will be placed into the group "SAMPLE". 

As you can see, "level" specifies that the default group name contains the number of the same parts in file names. If "level" is set to an invalid number (for example, -1), then default value of 2 is used instead.

Files that do not have similar name formats will not be placed into any groups.

### Source directories and customized groups

In the `groups` section, you can add source code directories and customize groups.

Here is a sample configuration:

```
"groups": [
    {
        "sourceDir": "PARENT/BP"
    }
]
```

You can add a source code folder by adding an element in `groups`. Use `sourceDir` to specify the source code folder name or a relative path. Multiple source code folders can be specified.

If no source code folder is specified, or if there is only one source code folder configured, the source code folder name will be omitted.

If there are no customized groups in the source code folder, the default rule will be applied. 

Here is a sample configuration for adding customized groups:

```
"groups": [
    {
        "sourceDir": "PARENT/BP", 
        "groupName": "SAMPLE", 
        "include": [
            "SAMPLE.*"
        ], 
        "exclude": [
            "SAMPLE.BASIC.CODE"
        ]
    }
]
```

- `groupName` specifies the customized group name. 
- `include` specifies which files will be included in this group.
- `exclude` specifies which files should be excluded from this group. Note that when files are excluded from a group, they can alternatively be placed into other groups.

If you need to add multiple groups into one source code folder, add multiple element items in `groups`. For example:

```
"groups": [
    {
        "sourceDir": "PARENT/BP", 
        "groupName": "SAMPLE", 
        "include": [
            "SAMPLE.*"
        ], 
        "exclude": [
            "SAMPLE.BASIC.CODE"
        ]
    }, 
    {
        "sourceDir": "PARENT/BP", 
        "groupName": "SAMPLE2", 
        "include": [
            "TEST.*"
        ]
    }
]
```

In this example, two customized groups (SAMPLE, SAMPLE2) are added to the source code folder "PARENT/BP".

Note that a file can only be placed into one group. This means that if you were to specify that a file be included in multiple different groups, it would only be added to the first specified group.

### Examples

The samples below illustrate how to configure the auto-group view function.

#### Example 1

In this example, the default rule’s delimiter is changed from "." to "_".

The directory structure of the opened folder is:

```
DEMO/
 |- SAMPLE_BASIC_FILE_1
 |- SAMPLE_BASIC_FILE_2
 |- SAMPLE_BASIC_FILE_3
 |- SAMPLE_MENU_FILE_1
 |- SAMPLE_MENU_FILE_2
 |- SAMPLE_FILE
 |- SAMPLE.CODE
```

The configuration for group view is:

```
"groupView": {
    "default": {
        "delimiter": "_", 
        "level": 2
    }
}
```

In the auto-group result, files with names that contain "_" will be grouped automatically. The result is shown below:

```
SAMPLE_BASIC
 |- SAMPLE_BASIC_FILE_1
 |- SAMPLE_BASIC_FILE_2
 |- SAMPLE_BASIC_FILE_3
 |
SAMPLE_MENU
 |- SAMPLE_MENU_FILE_1
 |- SAMPLE_MENU_FILE_2
 |
SAMPLE.CODE
SAMPLE_FILE
```



#### Example 2

In this example, a source code directory and a customized group are specified in the settings. 

The directory structure of the opened folder is:

```
DEMO/
 |- BP1/
 |  |- SAMPLE.BASIC.FILE_1
 |  |- SAMPLE.BASIC.FILE_2
 |  |- SAMPLE.CODE.FILE_1
 |  |- SAMPLE.CODE.FILE_2
 | 
 |- BP2/
 |  |- SAMPLE.BASIC.FILE
 |
 |- SAMPLE.FILE
```

Below is the configuration file content:

```
"groupView": {
    "default": {
        "delimiter": ".", 
        "level": 2
    }, 
    "groups": [
        {
            "sourceDir": "BP1", 
            "groupName": "SAMPLE", 
            "include": [
                "SAMPLE.BASIC.*"
            ]
        }
    ]
}
```

In the auto-group result below, groups will be displayed, but the source code folder "BP1" will not. "SAMPLE" group is a customized group, and "SAMPLE.CODE" is generated based on the default auto-group rule.

```
SAMPLE
 |- SAMPLE.BASIC.FILE_1
 |- SAMPLE.BASIC.FILE_2
 |
SAMPLE.CODE
 |- SAMPLE.CODE.FILE_1
 |- SAMPLE.CODE.FILE_2
```



#### Example 3

In this example, there are multiple source code directories and customized groups.

The directory structure of opened folder is:

```
DEMO/
 |- BP1/
 |  |- SAMPLE.BASIC.FILE_1
 |  |- SAMPLE.BASIC.FILE_2
 |  |- SAMPLE.CODE.FILE_1
 |  |- SAMPLE.CODE.FILE_2
 |
 |- BP2/
 |  |- SAMPLE.CODE.FILE_3
 |  |- SAMPLE.CODE.FILE_4
 |
 |- SAMPLE.FILE
```

The configuration for group view is:

```
"groupView": {
    "ignore": [
    ], 
    "default": {
        "delimiter": ".", 
        "level": 2
    }, 
    "groups": [
        {
            "sourceDir": "BP1", 
            "groupName": "BASIC", 
            "include": [
                "SAMPLE.BASIC.*"
            ]
        }, 
        {
            "sourceDir": "BP1", 
            "groupName": "CODE", 
            "include": [
                "SAMPLE.CODE.*"
            ]
        }, 
        {
            "sourceDir": "BP2"
        }
    ]
}
```

In the configuration file, there are different groups which are filled with different elements of the "groups" section. The auto-group result is shown below:

```
BP1
 |- BASIC
 |  |- SAMPLE.BASIC.FILE_1
 |  |- SAMPLE.BASIC.FILE_2
 |
 |- CODE
   |- SAMPLE.CODE.FILE_1
   |- SAMPLE.CODE.FILE_2
BP2
 |- SAMPLE.CODE
   |- SAMPLE.CODE.FILE_3
   |- SAMPLE.CODE.FILE_4
```

