# react-native-smart-badge
A smart autofit badge for react-native apps, written in JS for cross-platform support.
It works on iOS and Android.

This component is compatible with React Native 0.25 and newer.

## Preview

![react-native-smart-badge-preview-ios][1]
![react-native-smart-badge-preview-android][4]

## Installation

```
npm install react-native-smart-badge --save
```

## Full Demo

see [ReactNativeComponentDemos][0]

## Usage

Install the button from npm with `npm install react-native-smart-badge --save`.
Then, require it from your app's JavaScript files with `import Badge from 'react-native-smart-badge'`.

```js
import React, {
  Component,
} from 'react'
import {
  StyleSheet,
  View,
  Text,
} from 'react-native'

import Badge from 'react-native-smart-badge'
import Button from 'react-native-smart-button'

export default class NumberBadge extends Component {

    // 构造
    constructor (props) {
        super(props);
        // 初始状态
        this.state = {
            num1: 2,
            num2: 15,
            num3: 328,
        };
    }

    render () {
        return (
            <View style={{marginTop: 20 + 44, flex: 1, justifyContent: 'center', alignItems: 'center', }}>
                <Badge minWidth={18} minHeight={18} textStyle={{color: '#fff',}}>
                    {this.state.num1}
                </Badge>
                <Badge textStyle={{color: '#fff',}} style={{marginTop: 10,}}>
                    {this.state.num2}
                </Badge>
                <Badge textStyle={{color: '#fff',}} style={{marginTop: 10,}}>
                    {this.state.num3}
                </Badge>

                <Button
                    touchableType={'blur'}
                    style={{marginTop: 10, width: 300, justifyContent: 'center', height: 40, backgroundColor: '#00AAEF', borderRadius: 3, borderWidth: StyleSheet.hairlineWidth, borderColor: '#00AAEF', justifyContent: 'center',}}
                    textStyle={{fontSize: 17,  color: 'white'}}
                    onPress={this._addNum}>
                    click to plus num(点击增加数字)
                </Button>
            </View>
        )
    }

    _addNum = () => {
        this.setState({
            num1: this.state.num1 + 3,
            num2: this.state.num2 + 30,
            num3: this.state.num3 + 300,
        })
    }

}
```

## Props

Prop                   | Type   | Optional | Default   | Description
---------------------- | ------ | -------- | --------- | -----------
extraPaddingHorizontal | number | Yes      | 10        | determines the value of extra horizontal padding when the badge's width is larger than height.
style                  | style  | Yes      |           | see [react-native documents][2]
textStyle              | style  | Yes      |           | see [react-native documents][3]
minHeight              | number | Yes      |           | determines the min-height of badge
minWidth               | number | Yes      |           | determines the min-width of badge

[0]: https://github.com/cyqresig/ReactNativeComponentDemos
[1]: http://cyqresig.github.io/img/react-native-smart-badge-preview-ios-v1.0.7.gif
[2]: https://facebook.github.io/react-native/docs/style.html
[3]: https://facebook.github.io/react-native/docs/text.html#style
[4]: http://cyqresig.github.io/img/react-native-smart-badge-preview-android-v1.0.7.gif
