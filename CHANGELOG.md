# Change Log
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/)
and this project adheres to [Semantic Versioning](http://semver.org/).

## [0.7.0] - 2017-07-14
### Added
- Added capability to send messages from parent page to iframe using
postMessage
- Added config field to control whether the iframe should automatically
load
- Added a ready event sent by chatbot UI when running embedded to signal
the parent that the component loaded successfully
- Added capability to programatically post text messages to the
chatbot UI from a parent page when running embedded as an iframe
- Added capability to programatically minimize the chatbot UI
from a parent page when running embedded as an iframe
- Added Config field to control whether the iframe should load minimized

### Changed
- Major refactoring of the bot loader script to make it more modular
- Improved the documentation to include more details on embedding as an iframe
- Bumped dependency versions
- Changed indentation of various portions of the chatbot UI code to
conform to the the latest airbnb eslint config
- Changed vuetify components to work latest version
- Changed responseCard rendering style
- Changed bot loader CSS to better adapt to smaller resolutions
- Changed iframe minimize/expand to use new parent to iframe message passing

### Fixed
- Fixed responseCard parsing when using postContent

## [0.6.0] - 2017-07-07
### Added
- Added the ability to pass dynamic configuration from parent page to the
  bot loader via an event
- Added response cards object display to sample parent page

### Changed
- Bot loader script now uses its own credential variable instead of setting
  it into the global AWS object
- Bumped AWS SDK version in bot loader
- Added functionality to remove event handlers in bot loader for events that
  only fire once

### Fixed
- Typos, invalid links and display issues in README files

## [0.5.2] - 2017-07-05
### Fixed
- Credential loading issue in parent bot-loader.js

## [0.5.1] - 2017-06-06
### Changed
- Copyrights and Amazon software license

## [0.5.0] - 2017-06-05
### Added
- Ability to deploy a sample bot based on the OrderFlowers sample
 from the Lex [Create an Amazon Lex Bot (Console)](http://docs.aws.amazon.com/lex/latest/dg/gs-bp-create-bot.html)
 documentation.
- Added npm 5 package-lock.json file for more deterministic builds
- Copyrights and Apache license

### Changed
- Bumped dependency versions
- Default bot name using prefix
- Changed name of Lambda handler of CloudFormation custom resource for
  CodeBuild starter

### Fix
- Response Card rendering and sizing issues

## [0.4.1] - 2017-06-01
### Added
- Copyrights and Apache license
- Ability to provide Lex bot alias in config
- Added an event dispatcher to bot-loader.js to relay state from
  the chatbot ui to parent page
- Beefed up sample parent page

### Changed
- Bumped dependency versions
- Added an audio analyser to improve silence and interrupt detection
- Mute auto detection now defaults to false
- Changed default bot to OrderFlowers

### Fix
- General cleanup of docs and code

## [0.4.0] - 2017-05-26
### Added
- Support of response cards for postContent using
  sessionAttributes.appContext
- Ability to automatically change urls to links in bot message
  responses. This feature is controlled with the
  `ui.convertUrlToLinksInBotMessages` config field.
- Ability to automatically strip out tags (e.g. SSML or HTML) from
  bot responses. This can be controlled with the
  `ui.stripTagsFromBotMessages` config field.

### Changed
- Bumped dependency versions
- Using vuex getter mapper to reduce function clutter
- Moved message text to its own component MessageText
- Upgraded the vuetify library which changed the style of various
  components and adjusted the styling to make the UI work with the version.
- Made page wide scrollbar hidden

### Removed
- Got rid of the experimental playback controls for bot audio
- Removed work-around for mobile scrolling as the new vuetify library
  doesn't need it

### Fixed
- Improved bot playback interrupt async handlers. Now has visibility of audio
  duration.
- Fixed build-time config script to use the right bot name field and to
  incorporate other config fields

## [0.3.0] - 2017-05-12
### Added
- S3 bucket cleanup CloudFormation custom resource to optionally delete
  buckets created for the pipeline and to host the web application
- Support of Lex [Response Cards](http://docs.aws.amazon.com/lex/latest/dg/ex-resp-card.html)
- Console logging of processing time
- [Experimental] interruption of bot response playback by speaking over it
- [Experimental] playback controls for bot audio

### Changed
- Use of newly launched Cognito CloudFormation resources instead of Lambda
  based custom resources
- Bumped dependency versions

### Removed
- Removed Lambda python files used in Cognito CloudFormation custom resources

### Fixed
- Improved interruption of bot speech conversation when switching to text by
  avoiding Lex service conflicts (postText text while postContent processing)
- Mute autodetection config issue

## [0.2.0] - 2017-04-28
### Added
- Support to obtain dynamic config from URL query param or postMessage from
  parent iframe
- Config option to disable microphone echo cancellation in recorder
- Config option to disable recorder automatic mute detection
- Config options to control trimming silence in recorder/encoder
- Config option to reinitialize session attributes after bot is done
- Config option to control if initialText message should be pushed after bot
  is done
- Recorder config presets to optimize based on speech recognition or low latency
- Support to automatically increase the minimum recording time based on
  consecutive silent recordings

### Changed
- Improved recorder automatic mute detection
- Bumped dependency versions
- Moved page wide elements (e.g. title and fav icon) to Page component
- Consolidated config so that it is only imported by store

### Fixed
- Issue passing boolean options to recorder
- Rendering issue on mobile where it was needed to scroll down [WORKAROUND]

## [0.1.0] - 2017-04-14
### Added
- initial
