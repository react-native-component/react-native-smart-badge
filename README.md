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

or

```
npm install @react-native-component/react-native-smart-badge --save
```



## Usage

Install the button from npm with `npm install @react-native-component/react-native-smart-badge --save`.
Then, require it from your app's JavaScript files with `import Button from '@react-native-component/react-native-smart-badge'`.

```js
export default class NumberBadge extends Component {

  // 构造
    constructor(props) {
      super(props);
      // 初始状态
      this.state = {
         num1: 2,
         num2: 15,
         num3: 328,
      };
    }

  render() {
    return (
      <View style={{marginTop: 20 + 44, flex: 1, justifyContent: 'center', alignItems: 'center', }}>
          <Badge textStyle={{color: '#fff',}}>
            {this.state.num1}
          </Badge>
          <Badge textStyle={{color: '#fff',}} style={{marginTop: 10,}}>
            {this.state.num2}
          </Badge>
          <Badge textStyle={{color: '#fff',}} style={{marginTop: 10,}}>
            {this.state.num3}
          </Badge>

          <Text style={{marginTop: 10, padding: 3,}} onPress={this._addNum}>click to add num(点击增加数字)</Text>
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

[1]: http://cyqresig.github.io/img/react-native-smart-badge-preview-ios-v1.0.2.gif
[2]: https://facebook.github.io/react-native/docs/style.html
[3]: https://facebook.github.io/react-native/docs/text.html#style
[4]: http://cyqresig.github.io/img/react-native-smart-badge-preview-android-v1.0.2.gif
