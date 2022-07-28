# React-Native-Lottie-Animations
Adobe After Effects animations produced as json with Bodymovin are parsed and rendered natively on mobile devices by Lottie, a mobile library for Web, iOS, and Android. Which means Scalability never reduces quality of animations

# Demo 

![ReactNativeLottieAnimations](https://user-images.githubusercontent.com/86215353/181404321-fe2217ff-ae9d-4a8e-b141-0bf658a72cb6.gif)


# Lottie React Native

Adobe After Effects animations produced as json with Bodymovin are parsed and rendered natively on mobile devices by Lottie, a mobile library for Web, iOS, and Android. Which means Scalability never reduces quality of animations

Designers can now produce and deliver stunning animations without having an engineer painstakingly recreate them by hand.
Since a picture is worth a thousand words, there are 13,000 of them.

Lottie component for React Native ([iOS](https://github.com/airbnb/lottie-ios), [Android](https://github.com/airbnb/lottie-android), and [Windows](https://github.com/CommunityToolkit/Lottie-Windows))

## Installing

### iOS and Android
Install `lottie-react-native` (latest) and `lottie-ios` (3.2.3):

```
yarn add lottie-react-native lottie-ios@3.2.3
```

or

```
npm i --save lottie-react-native lottie-ios@3.2.3
```

Go to your ios folder and run:

```
pod install
```
## Usage

Lottie can be used in a declarative way:

```jsx
import React from 'react';
import Lottie from 'lottie-react-native';

export default function Animation() {
  return (
    <Lottie source={require('./animation.json')} autoPlay loop />
  );
}
```

Additionally, there is an imperative API which is sometimes simpler.

```jsx
import React, { useEffect, useRef } from 'react';
import Lottie from 'lottie-react-native';

export default function AnimationWithImperativeApi() {
  const animationRef = useRef<Lottie>(null)

  useEffect(() => {
    animationRef.current?.play()

    // Or set a specific startFrame and endFrame with:
    animationRef.current?.play(30, 120);
  }, [])

  return (
    <Lottie
      ref={animationRef}
      source={require('../path/to/animation.json')}
    />
  );
}
```

Lottie's animation progress can be controlled with an `Animated` value:

```jsx
import React, { useEffect } from 'react';
import { Animated, Easing } from 'react-native';
import Lottie from 'lottie-react-native';

export default function ControllingAnimationProgress() {
  const animationProgress = useRef(new Animated.Value(0))

  useEffect(() => {
    Animated.timing(animationProgress.current, {
      toValue: 1,
      duration: 5000,
      easing: Easing.linear,
      useNativeDriver: false
    }).start();
  }, [])

  return (
     <Lottie
      source={require('../path/to/animation.json')}
      progress={animationProgress.current}
    />
  );
}
```

Changing color of layers:

```jsx
import React from 'react';
import Lottie from 'lottie-react-native';

export default function ChangingColorOfLayers() {
  return (
    <Lottie
      source={require('../path/to/animation.json')}
      colorFilters={[
        {
          keypath: 'button',
          color: '#F00000',
        },
        {
          keypath: 'Sending Loader',
          color: '#F00000',
        },
      ]}
      autoPlay
      loop
    />
  );
}
```

## API

You can find the full list of props and methods available in Lottie's [API document](https://github.com/airbnb/lottie-react-native/blob/master/docs/api.md). These are the most common ones:

| Prop               | Description                                                                                                                                                                                                                                                                     | Default                                                                                                             |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| **`source`**       | **Mandatory** - The source of animation. Can be referenced as a local asset by a string, or remotely with an object with a `uri` property, or it can be an actual JS object of an animation, obtained (for example) with something like `require('../path/to/animation.json')`. | _None_                                                                                                              |
| **`style`**        | Style attributes for the view, as expected in a standard [`View`](https://facebook.github.io/react-native/docs/layout-props.html).                                                                                                                                              | The `aspectRatio` exported by Bodymovin will be set. Also the `width` if you haven't provided a `width` or `height` |
| **`loop`**         | A boolean flag indicating whether or not the animation should loop.                                                                                                                                                                                                             | `true`                                                                                                              |
| **`autoPlay`**     | A boolean flag indicating whether or not the animation should start automatically when mounted. This only affects the imperative API.                                                                                                                                           | `false`                                                                                                             |
| **`colorFilters`** | An array of objects denoting layers by KeyPath and a new color filter value (as hex string).                                                                                                                                                                                    | `[]`                                                                                                                |

[More...](https://github.com/airbnb/lottie-react-native/blob/master/docs/api.md)

## More

View more documentation, FAQ, help, examples, and more at [airbnb.io/lottie](https://airbnb.io/lottie/)

![Example1](https://res.cloudinary.com/dh6l45sly/image/upload/v1656138853/awereactnative/react-native-lottie-animations/LottieLogo1_iu9hw9.gif)

## Preview

![Example2](https://res.cloudinary.com/dh6l45sly/image/upload/v1656138853/awereactnative/react-native-lottie-animations/LottieLogo1_iu9hw9.gif)

![Example3](https://res.cloudinary.com/dh6l45sly/image/upload/v1656138854/awereactnative/react-native-lottie-animations/ShowcaseGoogleHomeA_jowtya.gif)

![Community](https://res.cloudinary.com/dh6l45sly/image/upload/v1656138854/awereactnative/react-native-lottie-animations/LottieWalkthrough_e3dyho.gif)

![Example4](https://res.cloudinary.com/dh6l45sly/image/upload/v1656138854/awereactnative/react-native-lottie-animations/ReactNativeLottieAnimations_q14gtb.gif)
