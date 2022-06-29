# Getting started Guide

# Objective : 
  Set up a local environment to run simple web applications with LaunchDarkly platform.

# Prerequisites : 
- On your local machine nodeJS is installed. 
  If not please download stable nodeJS version from https://nodejs.org/en/download/On your machine.
- On your machine any code text editor exists. Preferred one is visual studio code.
  If there is none, please visit https://code.visualstudio.com/download  
- Integrate your visual studio code with Github extension. 
  For more information visit https://code.visualstudio.com/docs/editor/github
- You have access to Launch Darkly platform. 
  If not start your free trial from https://launchdarkly.com/start-trial/
  
# How to get GitHub code?
- Pull GitHub code from repository https://github.com/pranaliu/LDAssignment/tree/master/LaunchDarkly_1/launch-darkly-test
- After pulling repo code, check that pulled code is accessible in your text code editor.

# How to configure LaunchDarkly platform?       
- Once you have access to LaunchDarkly platform you will see by default one project (name of organization you enter while starting free trial) is available to you.       
- After clicking on the project by default production and test environments are available.
- Configure an additional environment (for example Dev) if you need to use it for a sample application test. 
  Click on Account Settings -> Projects -> <your project> -> Environment -> create environment       
- Additionally you can set up more projects if needed to use. 
  Click on Account Settings -> Projects -> create project       
- Copy client side key for integrating your desired launch darkly environment.
  Go to Account Settings -> Projects -> <your project> -> Environment -> Client-side ID
  
# Add feature flag definitions
- Go to the LaunchDarkly platform. 
- Click on tab Feature flags -> create flag.
- Add below feature flags as described with name and type. 
  Click the checkbox on for SDKs using Client-side ID for all flags defined.
  1. headerText : "Boolean" type flag variation. Variation is true or false and add your description and rest other details. 
                  After save, on the targeting tab add default serve false when targeting is off.
  2. footerText : "String" type flag variation. 
                  Add variation1 value "Join new and fast way of deploying your features" for key LD text. 
                  Add variation2 value "LaunchDarkly is not yet an option?" 
                  For true add variation value1 with key "LDText". for false variation value2, add key "NoLDText".
  3. logoSwitch : "Boolean" type flag variation. Variation is true or false. 
                  After save, on the targeting tab add default serve false when targeting is off.
  4. EmailUser  : "Boolean" type flag variation. Variation is true or false. 
                  After save, on the targeting tab add default serve false when targeting is off.
                  In the Targeting section Target users who match these rules,
                  add If email ends with and supply your preferred email domain for example "gmail.com".
                  
# How to configure the LaunchDarkly environment in your application code?     
- Install LaunchDarkly REACT Web SDK in your environment through visual studio code terminal.
- Open terminal -> Go to your project code folder ->run command "npm install launchdarkly-react-client-sdk". 
  For more information visit https://docs.launchdarkly.com/sdk/client-side/react/react-web
- Go to visual studio code. Open code file ~LaunchDarkly_1/launch-darkly-test/src/LaunchDarklyConfig.json 
  For key "REACT_APP_CLIENT_ID" add value copied for client-side ID in above step.
  For key "Email" add your owner email for the environment chosen.
- Install additional npm packages for the application to run without any errors.
  npm install react-bootstrap bootstrap
  npm install react-router
  
# How to run application code?
- Open visual studio code terminal. Go to your React project root folder.  
  1. Install react-scripts with this command: npm i react-scripts  
  2. Run application with command npm start
