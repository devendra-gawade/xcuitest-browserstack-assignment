# XCUI Test Assignment — BrowserStack

## Files
- BrowserStack-SampleApp.ipa — the sample iOS app
- BrowserStack-SampleXCUITest-v2.zip — the XCUITest bundle

## How to run
1. Upload the .ipa:
   curl -u "USERNAME:ACCESS_KEY" \
   -X POST "https://api-cloud.browserstack.com/app-automate/xcuitest/v2/app" \
   -F "file=@BrowserStack-SampleApp.ipa"

2. Upload the test suite:
   curl -u "USERNAME:ACCESS_KEY" \
   -X POST "https://api-cloud.browserstack.com/app-automate/xcuitest/v2/test-suite" \
   -F "file=@BrowserStack-SampleXCUITest-v2.zip"

3. Trigger a build:
   curl -u "USERNAME:ACCESS_KEY" \
   -X POST "https://api-cloud.browserstack.com/app-automate/xcuitest/v2/build" \
   -H "Content-Type: application/json" \
   -d '{
     "app": "bs://79c4636edb38e40ba48e0fbb23ad2fa7513b3431",
     "testSuite": "bs://370346645845f0a2a5541c7bcdde2cefe3cd84e8",
     "devices": [{"device": "iPhone.*", "os_version": "16"}]
   }'

4. Check the build results on BrowserStack Dashboard.
