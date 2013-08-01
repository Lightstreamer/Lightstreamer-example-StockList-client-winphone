# Lightstreamer StockList Demo Client for Microsoft Windows Phone #

This project contains a demo client showing integration between Lightstreamer Windows Phone Client and the Windows Phone platform.

## Windows Phone 7 Stock-List Demo ##

<table>
  <tr>
    <td style="text-align: left">
      &nbsp;<a href="zune://navigate?phoneAppID=2cf8750d-ab7f-e011-986b-78e7d1fa76f8" target="_blank"><img src="http://www.lightstreamer.com/img/demo/screen_wp.png"></a>&nbsp;
      
    </td>
    <td>
      &nbsp;To install the app from the Windows Store<br>
      &nbsp;<a href="zune://navigate?phoneAppID=2cf8750d-ab7f-e011-986b-78e7d1fa76f8" target="_blank">zune://navigate?phoneAppID=2cf8750d-ab7f-e011-986b-78e7d1fa76f8</a>
    </td>
  </tr>
</table>

This is a Windows Phone version of the [Stock-List Demos](https://github.com/Weswit/Lightstreamer-example-Stocklist-client-javascript).<br>
This app uses the <b>Windows Phone Client API for Lightstreamer</b>, based on Silverlight, to handle the communications with Lightstreamer Server. A simple user interface is implemented to display the real-time data received from Lightstreamer Server.

In particular, this readme file details the steps required in order to execute the demo together with the Windows Phone emulator contained in Visual Studio (Express) for Windows Phone.

## Dig the code ##

* <b>App.xaml.cs</b> is the main application file, it contains application events handling code (application launching, closed, activated, etc), Lightstreamer Client streaming controls (start, stop) and part of the auto-reconnection logic required when connection quality is weak.
* <b>MainPage.xaml.cs</b> is the place where all the application widgets are handled. The application in fact, consists in a simple table containing real-time (simulated) stock quotes, whose cells are kept up-to-date by implementing the ILightstreamerListener interface.
  Several lines in this file are dedicated to the animation code used for highlighting cells in case of real-time updates, you can ignore them altogether if you feel more comfortable.
* <b>LightstreamerClient.cs</b> is a simple wrapper for LSClient public class (see Lightstreamer Silverlight API) and uses two listeners: <b>StocklistConnectionListener.cs</b> and <b>StocklistHandyTableListener.cs</b>, respectively implementing a Connection Status listener and a Real-Time Data Updates listener.

Check out the sources for further explanations.<br>
  
<i>NOTE: not all the functionalities of the Lightstreamer Windows Phone Demo are exposed by the classes listed above. You can easily expand those functionalities using the Silverlight Client API as a reference.<br>
If in trouble check out the [specific Lightstreamer forum](http://forums.lightstreamer.com/forumdisplay.php?34-Windows-Phone-Client-API).</i>

# Build #

If you want to skip the build process of this demo please note that you can install the app from the Windows Phone Marketplace, either click the image or link above from your Windows Phone, or go to the Marketplace and search for "Lightstreamer".<br>

Otherwise, to directly import the project as is you can use Microsoft Visual Studio 2010 Express for Windows Phone. You can download it from the [Microsoft website](http://www.microsoft.com/express/Phone/).

<i>NOTE: You may also use the sources of the demo with another IDE or without any IDE but such approach is not covered in this readme.</i>
  
You may run the demo against your local server or using our online server at http://push.lightstreamer.com:80. The server to which the demo will connect to is configured in the App.xaml.cs file.

You should complete this project with the Lightstreamer Windows Phone Client Library, to be used for the build process.<br>
Please, download the [latest Lightstreamer distribution](http://www.lightstreamer.com/download/) and copy the WindowsPhoneClient.dll and WindowsPhoneClient.pdb files from theLightstreamer Windows Phone Client SDK (that is located under the /DOCS-SDKs/sdk_client_windows_phone/lib folder) into the "lib" folder of this project.
  
You're now ready to import the project into Visual Studio, click on New Project->Windows Phone Application and import all the files located in the demo folder.
  
From Visual Studio, click on the WP7StockListDemo project in the Solution Explorer menu and press the "Run (debug)" button. The Windows Phone Emulator will be started and the application loaded.

# See Also #

## Lightstreamer Adapters needed by these demo clients ##

* [Lightstreamer StockList Demo Adapter](https://github.com/Weswit/Lightstreamer-example-Stocklist-adapter-java)
* [Lightstreamer Reusable Metadata Adapter in Java](https://github.com/Weswit/Lightstreamer-example-ReusableMetadata-adapter-java)

## Similar demo clients that may interest you ##

* [Lightstreamer StockList Demo Client for JavaScript](https://github.com/Weswit/Lightstreamer-example-Stocklist-client-javascript)
* [Lightstreamer StockList Demo Client for jQuery](https://github.com/Weswit/Lightstreamer-example-StockList-client-jquery)
* [Lightstreamer StockList Demo Client for Dojo](https://github.com/Weswit/Lightstreamer-example-StockList-client-dojo)
* [Lightstreamer StockList Demo Client for Adobe Flex SDK](https://github.com/Weswit/Lightstreamer-example-StockList-client-flex)
* [Lightstreamer StockList Demo Client for Java SE](https://github.com/Weswit/Lightstreamer-example-StockList-client-java)
* [Lightstreamer StockList Demo Client for .NET](https://github.com/Weswit/Lightstreamer-example-StockList-client-dotnet)
* [Lightstreamer StockList Demo Client for Microsoft Silverlight](https://github.com/Weswit/Lightstreamer-example-StockList-client-silverlight)
* [Lightstreamer StockList Demo Client for Microsoft WinRT](https://github.com/Weswit/Lightstreamer-example-StockList-client-winrt)

# Lightstreamer Compatibility Notes #

- Compatible with Lightstreamer WinRT Client Library version 1.0 or newer.