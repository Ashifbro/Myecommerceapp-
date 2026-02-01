
name: Build PWA to APK

on:
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3

      - name: Build PWA to APK
        uses: sharadcodes/pwa-to-apk-action@v1.0.0
        with:
          url: "https://YOUR-PWA-APP-URL"
          name: "MyEcommerceApp"
          package: "com.yourname.myecommerceapp"

      - name: Upload APK
        uses: actions/upload-artifact@v3
        with:
          name: android-apk
          path: app-release.apk
