# iOS Guide
## Development build

To create a development build,

1. Follow the quickstart guide to create a new app with the app builder and install all the dependencies
2. Run npm start in the project root. This will launch the CLI
3. Select Build in the main menu
Linux_Build
4. Select iOS in the platforms menu
iOS_Platform
5. Select Development in the build menu
Linux_Type_Development
6. Xcode will now launch with your app
7. Select your project in the Xcode project navigator
8. Type in a bundle id and build number for your project
9. To configure automatic signing,
  1. Navigate to signing and capabilities
  2. Select your signing team
10. Select your device on the top bar and press build
11. This will launch the development edition of the application on your iOS device

# Production build with code signing

To create a production build,

1. Follow the quickstart guide to create a new app with the app builder and install all the dependencies
2. Run npm start in the project root. This will launch the CLI
3. Select Build in the main menu
Linux_Build
4. Select iOS in the platforms menu
iOS_Platform
5. Select Production in the build menu
Linux_Type_Production
6. Xcode will now launch with your app
7. Select your project in the Xcode project navigator
8. Type in a bundle id and build number for your project
9. To configure automatic signing,
  1. Navigate to signing and capabilities
  2. Select your signing team
10. To enable deep links,
  1. Set up the web deployment according to [this guide](web-guide.md)
  2. Navigate to Build Phases > Copy Bundle Resources and select ```ravian-aristocrat.entitlements```
11. Select the connected iOS device on the top panel
12. Select Product > Archive. This will create a new distributable archive
13. Select Window > Organizer. You should see all your archives listed here
14. Select Distribute app > App Store Connect to start the export wizard for testflight