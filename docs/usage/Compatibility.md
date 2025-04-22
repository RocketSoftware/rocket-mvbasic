# U2 Product Compatibility

For the Rocket MV BASIC Extension product, not all features are currently supported on all U2 products & platforms. Users need to pay attention to the U2 product version and platform information first, as some feature may not working properly.

For more details, please refer [Rocket-MV-BASIC-Extension-features-support-matrix](https://my.rocketsoftware.com/RocketCommunity/s/article/Rocket-MV-BASIC-Extension-features-support-matrix).

# VS Code Compatibility 

Upgrading VS Code may potentially introduce some issues that could result in anomalies with the compilation or debugging functions of our extension. In such cases, you can consider downgrading VS Code as a workaround. We have summarized a list of recent stable versions of VS Code for your reference.

|  VS Code  |   GRPC Debug  |  CLI Debug  | Compilation | Online Editing |
| --------- | ------------- | ----------- | ----------- | -------------- |
|  1.83.1   |      x        |      x      |      √      |       √        |
|  1.82.3   |      x        |      x      |      √      |       √        |
|  1.82.2   |      √        |      √      |      √      |       √        |
|  1.82.1   |      √        |      √      |      √      |       √        |
|  1.81.0   |      √        |      √      |      √      |       √        |
|  1.80.2   |      √        |      ×      |      √      |       √        |
|  1.79.2   |      √        |      ×      |      √      |       √        |
|  1.78.2   |      √        |      √      |      √      |       √        |
|  1.77.3   |      √        |      √      |      √      |       √        |
|  1.76.2   |      √        |      √      |      √      |       √        |
|  1.75.1   |      √        |      √      |      √      |       √        |

 - Due to the upgrades to VS Code versions 1.82.3 and 1.83.1, the restart functionality in the debugging feature cannot be used properly, but other debugging functions work without issues.

**Note**: Please refer [Debugging](./Debugging.md) to find out suitable UniVerse / UniData for debugging features.