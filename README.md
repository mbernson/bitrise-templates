# Bitrise templates

Bitrise workflow templates that I re-use between projects

## iOS (`bitrise-ios.yml`)

This configuration contains the following workflows:

- `unit-test` runs the test plan UnitTests on a simulator.
- `ui-test` runs the test plan UITests on a simulator.
- `deploy-to-app-store` creates a release build and submits it to App Store Connect.

In order to use it on Bitrise, you should do the following:

1. In your Bitrise **profile/organisation settings**, create an 'Apple Service connection' using an App Store Connect API key (.p8 file).
2. In your Bitrise **project settings**, under 'team', select the Apple service connection you just created.
3. In the Bitrise project, under **code signing assets**, upload a code signing certificate (.p12 file). 
   I always export both the 'Apple Development' and 'Apple Distribution' certificates using Keychain Access on my Mac.
4. Paste this yaml into Bitrise. Fill in the environment variables using the 'env vars' in the Bitrise workflow editor.
