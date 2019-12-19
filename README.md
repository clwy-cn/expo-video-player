# Basic info
Video component for Expo built on default Video component. Inspired by [expo/videoplayer](https://github.com/expo/videoplayer) _(already deprecated)_ 

The package has lot of configuration options to fix your needs. Only `source` and `inFullscreen` are required. See the props table below. The `Video` component also supports phones, which screen ratio is not standard.

For compatibility information check <a href='#compatibility'>Compatibility</a>


## Installation
- Expo video player
`yarn add expo-video-player` _or_ `npm install expo-video-player`
- Dependencies
You may also need `expo-av` and `@react-native-community/netinfo`. Install them with `expo-cli` (`expo install expo-av @react-native-community/netinfo`)


## Usage
Example app can be found in the folder [example-app](https://github.com/ihmpavel/expo-video-player/tree/master/example-app).

```
import { Video } from 'expo-av'
import VideoPlayer from 'expo-video-player'

<VideoPlayer
  videoProps={{
    shouldPlay: true,
    resizeMode: Video.RESIZE_MODE_CONTAIN,
    source: {
      uri: 'http://commondatastorage.googleapis.com/gtv-videos-bucket/sample/BigBuckBunny.mp4',
    },
  }}
  inFullscreen={true}
/>
```


## Props

prop | type | default | required | description
---- | :-------: | :-------: | :-------: | -----------
**debug** | `boolean` | `false` | :x: | Write internal logs to console
_VIDEO PROPS_ |
**videoProps** | [`VideoProps`](https://docs.expo.io/versions/latest/sdk/video/#props) | `{}` | :heavy_check_mark: | [Video props](https://docs.expo.io/versions/latest/sdk/video/#props) to Expo component (at least source is required)
**inFullscreen** | `boolean` |  | :heavy_check_mark: | Specify if video is inFullscreen (show enter/leave fullscreen icons)
**width** | `number` | `Dimensions.get('window').width` | :x: | Specify width of the video (automatically set height based on screen ratio)
**height** | `number` | `Dimensions.get('window').height` | :x: | Specify height (automatically set width based on screen ratio)
_ANIMATIONS_ |
**fadeInDuration** | `number` | `200` | :x: | How long should the fadeIn animation for the controls run? (in milliseconds)
**fadeOutDuration** | `number` | `1000` | :x: | How long should the fadeOut animation run? (in milliseconds)
**hideControlsTimerDuration** | `number` | `4000` | :x: | If the user has not interacted with the controls, how long should the controls stay visible? (in milliseconds) Default value is 4000.
**quickFadeOutDuration** | `number` | `200` | :x: | How long should the fadeOut animation run when the screen is tapped when the controls are visible?
_ICONS_ |
**fullscreenEnterIcon** | `JSX.Element` | `FullscreenEnterIcon` | :x: | Default icon for entering fullscreen video
**fullscreenExitIcon** | `JSX.Element` | `FullscreenExitIcon` | :x: | Default icon for exiting fullscreen video
**playIcon** | `JSX.Element` | `PlayIcon` | :x: | Default icon for playing the video
**pauseIcon** | `JSX.Element` | `PauseIcon` | :x: | Default icon for pausing the video
**replayIcon** | `JSX.Element` | `ReplayIcon` | :x: | Default icon for replaying the video
**spinner** | `JSX.Element` | `ReplayIcon` | :x: | Default icon for pausing the video
**showFullscreenButton** | `boolean` | `true` | :x: | Boolean indicating whether fullscreen icon should be visible
_APPEARANCE_ |
**iosThumbImage** | `source` | [`image`](https://github.com/ihmpavel/expo-video-player/tree/master/lib/assets/thumb.png) | :x: | iOS [thumbImage](https://facebook.github.io/react-native/docs/slider#thumbimage)
**iosTrackImage** | `source` | [`image`](https://github.com/ihmpavel/expo-video-player/tree/master/lib/assets/track.png) | :x: | iOS [trackImage](https://facebook.github.io/react-native/docs/slider#trackimage)
**showControlsOnLoad** | `boolean` | `false` | :x: | Boolean indicating whether controls should be visible on load
**sliderColor** | `color` | `#009485` | :x: | Color for ANDROID [thumbTintColor](https://facebook.github.io/react-native/docs/slider#thumbtintcolor) and iOS [minimumTrackImage](https://facebook.github.io/react-native/docs/slider#thumbtintcolor)
**textStyle** | `TextStyle` | `{color: '#FFF', fontSize: 12}` | :x: | Default styling for text (eg. errors)
**videoBackground** | `color` | `#000` | :x: | Default background around video
_CALLBACKS_ |
**errorCallback** | `function` | `error => console.error('Error: ', error.message, error.type, error.obj)` | :x: | Function when an error occurs
**playbackCallback** | `function` | `callback => {}` | :x: | Function when playing changes (buffering/seeking/...)
**switchToPortrait** | `function` | `() => console.warn('Pass in this function 'switchToPortrait' in props to enable fullscreening')` | :x: | Pass your function to make something on click (eg. rotate phone)
**switchToLandscape** | `function` | `() => console.warn('Pass in this function 'switchToLandscape' in props to enable fullscreening')` | :x: | Pass your function to make something on click (eg. rotate phone)


## Compatibility
Library version | Expo SDK version
---- | -------
1.5.x | >= SDK 34 
1.4.x | >= SDK 34 
1.3.x | >= SDK 34 
1.2.x | >= SDK 33
1.1.x | >= SDK 32
1.x.x | >= SDK 32


### CHANGELOG
Changelog added in version 1.3.0
Read [CHANGELOG.md](https://github.com/ihmpavel/expo-video-player/tree/master/CHANGELOG.md)


### TODO
- [ ] make better example app
- [ ] make tests


#### Some articles 
 - [Creating a typescript module](https://codeburst.io/https-chidume-nnamdi-com-npm-module-in-typescript-12b3b22f0724)
 - [Creating a component for React](https://medium.com/@BrodaNoel/how-to-create-a-react-component-and-publish-it-in-npm-668ad7d363ce)
