
# Smart Map Widget for Cumulocity[<img width="35" src="https://user-images.githubusercontent.com/67993842/97668428-f360cc80-1aa7-11eb-8801-da578bda4334.png"/>](https://github.com/SoftwareAG/cumulocity-smart-map-widget/releases/download/2.1.1/smartmap-runtime-widget-2.1.1.zip)

  

  

The Smart Map widget help you to track real-time device locations in indoor with multi floor infrastructure as well as in outdoor.

  > ### ⚠️ This project is no longer under development. Please use [cumulocity-smart-map-widget-plugin](https://github.com/SoftwareAG/cumulocity-smart-map-widget-plugin) for Application Builder >=2.x.x and Cumulocity >=1016.x.x⚠️
### Please choose Smart Map release based on Cumulocity/Application builder version:

|APPLICATION BUILDER | CUMULOCITY | SMART MAP WIDGET |
|--------------------|------------|------------------|
| 1.3.x              | >= 1011.x.x| 2.x.x            |
| 1.2.x              | 1010.x.x   | 1.x.x            |  


  

  

![](https://user-images.githubusercontent.com/32765455/94537868-f5452f00-0260-11eb-830e-e103546d9567.png)

    

## What's new?

*  **Asset Hierarchy/DTM:** Now Smart Map support up to three level of asset hierarchy to display assets and devices on the Map.

*  **Marker Icons:** Now user can select any icon from pre-configured list or use from Asset Types.

*  **Display Mode:** User can select devices, assets, infrastructure, etc. to display on map.

*  **Marker styles:** Now user configure custom colors for markers and select shape. User can also configure custom fragment(from device managed object) to change marker styles dynamically.
 
*  **Navigation from Map(Improved):** Smart map support dashboard navigation directly from map (Available only in Application Builder) based on device/asset types.

## Features

*  **Smart Map:** Smart Map widget upgrade to angular 11. 
  
*  **Heat Map:** Location event based real time Heat Map for Indoor as well as for Outdoor devices. Heat Map also supports based on realtime last location event.

*  **Cluster Map:** Indoor and outdoor cluster map to show case real time device tracking.

*  **Geo-fences and Smart Rule:** Configure and fire smart rules based on geo-fences for indoor and outdoor devices.
  
*  **SVG and GeoJSON Support:**  Now Smart Map supports SVG and GeoJSON file format.

*  **Historical Heat Map:** Build Heat Map for indoor or outdoor based on historical data.

*  **Hybrid Map:** An unique map for real time tracking of your device in indoor as well as outdoor.

*  **Support single device and group devices:** Based on configuration during widget configuration.

*  **Support Indoor Infrastructure settings :** Beacons, Cameras, Tags and Devices (Applicable for Indoor Map only).

*  **Support Multiple floors :** Based on Altitude settings in device manage objects.

*  **Smart Configuration:** Simplified configuration options based on map type and also control Indoor Zoom, Outdoor Zoom, Heat intensity and much more during smart map configuration.

*  **[Smart Map Settings](https://github.com/SoftwareAG/cumulocity-smart-map-settings-widget):** Configure multiple floor plans with live preview.

*  **Follow Device:** Unique Feature to follow/track your single device when device move from one floor to another floor.

*  **Display Modes:** show/hide devices/infrastructure on indoor map.
  

## Installation

  
### Runtime Widget Deployment?

* This widget support runtime deployment. Download [Runtime Binary](https://github.com/SoftwareAG/cumulocity-smart-map-widget/releases/download/2.1.1/smartmap-runtime-widget-2.1.1.zip) and use application builder to install your runtime widget.

### Installation of widget through Appbuilder 
  

**Supported Cumulocity Environments:**

  

  

*  **App Builder:** Tested with Cumulocity App Builder version 1.3.1.


  

  

**Requirements:**

  

  

* Git

  

  

* NodeJS (release builds are currently built with `v14.18.0`)

  

  

* NPM (Included with NodeJS)

  

  

**External dependencies:**

  

  

```
  
 "angular-resize-event": "^2.1.0" 
 
 "fontawesome": "4.7.2"
 
 "group-array": "^1.0.0"
 
 "leaflet-draw": "^1.0.4"
 
 "leaflet-extra-markers": "^1.2.1"
 
 "leaflet2": "npm:leaflet@1.7.1"
 
 "@angular/material": "11.2.3"
 
 "ngx-bootstrap": "6.2.0"
 
 "leaflet.markercluster": "^1.4.1"

```

  

**Installation Steps For App Builder:**

  

  

**Note:** If you are new to App Builder or not yet downloaded/clone app builder code then please follow [App builder documentation(Build Instructions)](https://github.com/SoftwareAG/cumulocity-app-builder) before proceeding further.

  

  

1. Open Your existing App Builder project and install external dependencies by executing below command or install it manually.


    ```
    npm i angular-resize-event@2.1.0 fontawesome@4.7.2 group-array@1.0.0 leaflet-draw@1.0.4 leaflet-extra-markers@1.2.1 leaflet2@npm:leaflet@1.7.1 @angular/material@11.2.3 ngx-bootstrap@6.2.0 leaflet.markercluster@1.4.1
    ```


  
2. Install **[Smart Map Settings Widget](https://github.com/SoftwareAG/cumulocity-smart-map-settings-widget)** for indoor configuration.


  

3. Grab the Smart Map **[Latest Release Binary](https://github.com/SoftwareAG/cumulocity-smart-map-widget/releases/download/2.1.1/gp-smart-map-2.1.1.tgz)**.

  

  

4. Install the Binary file in app builder.

  

  

    ```
        
    npm i <binary file path>/gp-smart-map-x.x.x.tgz

    ```

  

  

5. Copy smart-map.css file [from here](https://github.com/SoftwareAG/cumulocity-smart-map-widget/releases/download/2.1.1/smart-map.css) and paste it at /cumulocity-app-builder/ui-assets/


      



6. Open index.less located at /cumulocity-app-builder/ui-assets/

  

  

7. Update index.less file with below Material theme. Import at first line in file/begining of file(Please ignore this step if it already exist).

  
  

    ```

    @import '~@angular/material/prebuilt-themes/indigo-pink.css';

    ```

  

  

8. Update index.less file with below smart-map.css. Import at last line/end of file.

  

  

    ```

    @import 'smart-map.css';    

    ```

  

9. Import SmartMapModule in custom-widget.module.ts file located at /cumulocity-app-builder/custom-widgets/

  

  

    ```

    import {GPSmartMapModule} from 'gp-smart-map';

    @NgModule({    

      imports: [

      GPSmartMapModule

      ]
    })
    
    ```

  

  

10. Congratulation! Installation is now completed. Now you can run app builder locally or build and deploy it into your tenant.

  

  

    ```

    //Start App Builder

    npm run start

    // Build App

    npm run build

    // Deploy App

    npm run deploy

    ```

  

  
  

## Build Instructions

  

  

**Note:** It is only necessary to follow these instructions if you are modifying/extending this widget, otherwise see the [Installation Guide](#Installation).

  

  

**Requirements:**

  

  

* Git

  

  

* NodeJS (release builds are currently built with `v14.18.0`)

  

  

* NPM (Included with NodeJS)

  

  

**Instructions**

  

  

1. Clone the repository:

  

    ```

    git clone https://github.com/SoftwareAG/cumulocity-smart-map-widget.git

    ```

  

2. Change directory:

  
    ```
    cd cumulocity-smart-map-widget

    ```

  

3. (Optional) Checkout a specific version:

  

    ```
    git checkout <your version>

    ```

  

4. Install the dependencies:

  

    ```
    npm install

    ```

  

5. (Optional) Local development server:

  

    ```
    npm run start

    ```

  

6. Build the app:

  

    ```

    npm run build

    ```

  

7. Deploy the app:

  

    ```
    npm run deploy

    ```

  

  

## QuickStart

  

This guide will teach you how to add widget in your existing or new dashboard.

  

**NOTE:** This guide assumes you have followed the [Installation instructions](#Installation)

  

1. Open you application from App Switcher

  

2. Add new dashboard or navigate to existing dashboard

  

3. Click `Add Widget`

  

4. Search for `Smart Map`

  

5. Select `Target Assets or Devices`

  

7. Click `Save`

  

Congratulations! Smart Map is configured.

  

  

## User Guide

  

  

**Outdoor Map:**

  
  

*  **Target assets or devices:** User can select a device or a group. Based on device/group, list of devices will be display on Map. Only those devices are visible on map where position attributes are configured. Altitude value represent floor number in this map.

  
  
*  **Asset Type:** User can select any Asset Type From Drop down. This asset types will be populated from Smart-Map-Settings widget where user has ability to create asset type and tag it with indoor floor plan or geo-fences. Based on selected asset type, corresponding asset(s) will be loaded on Smart Map.


*  **Display Mode:** User has ability to select only devices(live tracker), only assets, only devices and assets or all. Based on selection, devices will be display on map.



**Indoor Map:**

  
  

*  **Target assets or devices:** Same as outdoor Map.

  
  

*  **Asset Type:** Same as outdoor Map.
  
  

*  **Infra Group ID:** This group should have devices which are represent infrastructure of building/floor plan such as Camera, Tag, Beacon. Smart map support Camera, Tag and Beacon and identify by device type field in device object. (Please make sure that device type field must contains keyword either 'Camera', 'Tag' or 'Beacon'. For example, c8y_assetTag, c8y_beacon, c8y_camera).

  

*  **Display Mode:** User has ability to select only devices(live tracker), only assets, only devices and assets, only infrastructure devices(beacon, tag, etc) or all. Based on selection, devices will be display on map.



**Hybrid Map:**

  

*  **Scenario:** Hybrid Map is a unique combination of Indoor and outdoor tracking for a particular device or asset. Here selection of target assets/devices represent a asset which have two child devices which will represent indoor tracker device and outdoor tracker device. Indoor tracker device will get activated as soon as it will come in proximity of a beacon which is located as part of infrastructure of a building. If indoor tracker device did not receive any location event for certain time period(time period is calculated based on location event received in recent past) then Smart Map will automatically switch to outdoor tracker and display the location based on outdoor tracker.

  

*  **Target assets or devices:** Same as Outdoor Map. In Hybrid Map, it is recommended to select single asset or group which have single asset and asset should have two child devices(Indoor tracker and outdoor tracker).

  

*  **Asset Type:** Same as outdoor Map.

  
  

*  **Infra Group ID:** Same as Indoor Map.

  
  

*  **Display Mode:** Same as Indoor Map.

  

*  **Indoor Tracker ID:** This is indoor tracker device id which must be child device of an asset. If not provided, then outdoor tracker will be used for asset tracking.

  

*  **Outdoor Tracker ID:** This is outdoor tracker device id which must be child device of an asset. If not provided, then asset's location will be used for tracking.

  
  

*  **Location Event Type(s):** One more location event types separated by comma. Default : "c8y_LocationUpdate"


  

**Heat Map/ Indoor Heat Map:**

  

*  **Target assets or devices:** Same as Outdoor Map. In Heat Map, device(s) are used to capture location events. Please note that Heat Map is not floor specific.


*  **Asset Type:** Same as outdoor Map(Applicable for Indoor Heat Map only).


*  **Display Mode:** Same as Outdoor Map.
  

*  **Location Event Type(s):** Same as Hybrid Map.


*  **Event Fragment Type:** User has ability to provide custom fragment name(e.g., c8y_location). This fragment is used to access location event for device/asset (default is c8y_Position).
  

*  **Heat Map Event Quantity:** If custom location event has any field which can represent intensity/count of events then user can provide it. by default, system will auto calculate intensity for heat map.

  
  
*  **Heat Map Intensity Legends:** User has ability to provide custom legends for Low, Medium and High Intensity.



**Cluster Map/ Indoor Cluster Map:**


*  **Target assets or devices:** Same as outdoor Map.


*  **Asset Type:** Same as outdoor Map(applicable only for Indoor Cluster Map).

  
*  **Display Mode:** Same as Outdoor Map.


**Advance Configuration:**


  

*  **Follow Device:** Switch on to follow/track your single device when device move from one floor to another floor.

  

*  **Geofence:** Switch on to see geofence option on Smart Map(Subject to geofence configuration in smart map configuration widget).

  
*  **Include Child Device:** Switch on to include/consider child device to display instead of parent device based on active location event/tracking. Not applicable for Hybrid map.

  
*  **Heat Map Last Event Only:** Switch on to display map based on last location event.  As soon as new event comes for same device, existing event location will be removed from map.


*  **Default Zoom:** User has ability to change outdoor zoom level. Default is Auto.


*  **Default Indoor Zoom:**   User has ability to change indoor zoom level. Default is Auto.

 
*  **Heat Map Event Intensity:** User has ability to change location event intensity for Heat  Map. Default is Auto.


*  **Marker Icon:**   User has ability to use marker icon which is configured during asset type creation in Digital Twin Manager(DTM) or select from pre-defined list.

*  **Marker Icon Color:** User can select color for marker Icon by selecting color from color picker or entering color code(hex) directly in input field. Alternatively, user can also provide field name from device managed object which is having color code(hex).

*  **Marker Color:** User can select color for marker by selecting color from color picker or entering color code(hex) directly in input field. Alternatively, user can also provide field name from device managed object which is having color code(hex).

*  **Marker Shape:** User can select marker shape from dropdown menu. Smart map support four shapes(Circle, Star, Square, Penta) currently. Alternatively, user can also provide field name from device managed object which is having shape name. Please note that shape name should be any one of circle, star, square, penta(all in small letter).

*  **Hierarchy Level:** User has ability to select hierarchy level of devices/assets. Based o user selection, all devices/assets will be display on map. Currently up to 3 levels are supported. Please note that changing level from default may downgrade performance subject to number of devices/assets at each level you have.


*  **Dashboard Settings(Application Builder Only):** This feature is available only in application builder. User can navigate to any other dashboard by providing below details:
    * **Device/Asset Type:** Select a device or asset type. Navigation will be applied to all devices/assets of this device/asset type to a specific dashboard.
    * **Dashboard ID:** Dashboard ID of a dashboard where user need to navigate. You can find dashboard id in browser URL.
    * **DeviceId as TabGroup:** Select this option only if you are using Group Template as dashboard in application builder and selected deviceId as tabgroup field during group template configuration.
    * **TabGroup ID(optional):** If your dashboard is based on tabgroup then provide tabgroup id.


    * **Dashboard Field(Deprecated):** User has ability to provide device object field which represent dashboard Id. Based on this field, smart map will display navigation link for device. This option will be removed from next version.
    * **TabGroup Field(Deprecated):** User has ability to provide device object field which represent dashboard tab group name. Based on this field, smart map will display navigation link for device. This option will be removed from next version.


**Note:** Some of the Advance configuration options are map type specific.




**Smart Map On Screen Options:**

  

  

*  **Realtime**: Realtime tracking is activated by default. Use can click on it to on/off real time tracking of device(s).

  
  

*  **Reload**: Useful for force reload/refresh map.

  

  

*  **Active Tracker**: Indicator for user about active tracker(Indoor/Outdoor). Available only for Hybrid Map.

  

*  **Date Range Filter**: Date range filter to generate heat map based on historical events. Available only for Heat Map when Real time is off.

  

  

## Troubleshooting

  

  

*  **Floor Plan not loaded:**

  

  

    * Verify that your device is located on floor plan.

    

    

    * Check and verify smart-map-settings widget for exact geo coordinates.

    

    

    * Check in browser console for any content security violation error. If any content violation error present then update content security policy in your app. Content security policy located in package.json file in your app. You can compare and update as per below example:

  

  

```  

"contentSecurityPolicy": "base-uri 'none'; default-src 'self' 'unsafe-inline' http: https: ws: wss:; connect-src 'self' *.billwerk.com http: https: ws: wss:; script-src 'self' open.mapquestapi.com *.twitter.com *.twimg.com 'unsafe-inline' 'unsafe-eval' data:; style-src * 'unsafe-inline' blob:; img-src * data: blob:; font-src * data:; frame-src *;"


```

  

  

------------------------------

  

  

  

This widget is provided as-is and without warranty or support. They do not constitute part of the Software AG product suite. Users are free to use, fork and modify them, subject to the license agreement. While Software AG welcomes contributions, we cannot guarantee to include every contribution in the master project.

  

  

_____________________

  

  

For more information you can Ask a Question in the [TECHcommunity Forums](https://tech.forums.softwareag.com/tags/c/forum/1/Cumulocity-IoT).

  

  

  

You can find additional information in the [Software AG TECHcommunity](https://tech.forums.softwareag.com/tag/Cumulocity-IoT).
