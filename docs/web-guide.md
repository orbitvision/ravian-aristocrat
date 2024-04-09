# Web Guide

## Development Build
To create a development build,

1. Follow the quickstart guide to create a new app with the app builder and install all the dependencies
2. Run npm start in the project root. This will launch the CLI
3. Select Build in the main menu
![Select build](.\images\web-build\1.png)
4. Select Web in the platforms menu
![Select Web](images/web-build/2.png)
5. Select Development in the build menu
![Select Development](images/web-build/3.png)
6. This will launch the development edition of the Web application on your system

## Production build

To create a production build,

1. Follow the quickstart guide to create a new app with the app builder and install all the dependencies

2. Run npm start in the project root. This will launch the CLI

3. Select Build in the main menu
![Select build](images/web-build/1.png)
4. Select Web in the platforms menu
![Select Web](images/web-build/2.png)
5. Select Production in the build menu
![Select Production](images/web-build/4.png)
6. This will build the production edition of the Web application on your system

7. The binary will be located at ```agora-app-builder/ravian-aristocrat/dist```

8. This project uses react-router to perform front-end routing. So you need to configure your website host (or webserver) to redirect all the requests to index.html. We have already provided the config for two popular SPA hosts: vercel & netlify


*Copy paste the appropriate redirect file into ```agora-app-builder/ravian-aristocrat/dist``` (which contains the built index.html and js).*

vercel.json (for vercel)


```
{
  "rewrites": [{ "source": "/(.*)", "destination": "/index.html" }]
}
```
_redirects (for netlify. It's just _redirects no file extension)


```/* /index.html 200```

Optionally, If you are also building an iOS app, add an apple-app-site-association file in agora-app-builder/&lt;PRODUCT_ID&gt;/dist
apple-app-site-association (It's just apple-app-site-association no file extension)


```
{
  "applinks": {
    "apps": [],
    "details": [
      {
        "appID": "TEAM_ID.BUNDLE_ID",
        "paths": ["*"]
      }
    ]
  }
}
```

Replace TEAM_ID and BUNDLE_ID with your own apple team id and bundle id.

Also, add appropriate headers to your CDN to ensure that the apple-app-site-association file is served with Content-Type=application/pkcs7-mime header. Here is an example vercel.json with configured headers:

vercel.json


```
{
  "rewrites": [{ "source": "/(.*)", "destination": "/index.html" }],
  "headers": [
    {
      "source": "/apple-app-site-association",
      "headers": [
        {
          "key": "Content-Type",
          "value": "application/pkcs7-mime"
        }
      ]
    }
  ]
}
```

This is how your directory will look like once you are done:

```
dist/
├── 0c70ae08030483b5c6ff179bd61b411d.png
├── 0dbb46afd5749f6d8979f9be7869cd5d.png
├── 44da239f706935fc51d14bdc287e6afb.png
├── a09a7277eaeb33e1f28d4f649ce04444.png
├── af43cb6e35c119682e2f40bcec56da30.png
├── b292d48f1bbd5845fd620265eb258d71.png
├── d33dc98eed44cac76032f4d9ad428b3e.png
├── f7215317ffec2eaeee0261c58935f3dc.png
├── index.html
├── main.js
├── apple-app-site-association // Only if you are building for iOS
└── vercel.json //If you are deplying to vercel
```
