# react-native-instagram-like-picker

Pick the image like instagram and manupulate it.

## Installation

```sh
npm install react-native-instagram-like-picker
```

## Basic Usage

```js
import React from 'react';
import { View } from 'react-native';
import { InstagramLikePicker } from 'react-native-instagram-like-picker';

class UploadFiles extends React.Component {

    constructor(props) {
        super(props);
        this.state = {};
    }

    onSelectImage = (data) => {
        console.log('onSelectImage =>', data);
    }

    onCropped = (data) => {
        console.log('onCropped =>', data);
    }

    onClose = () => {
        console.log('onClose');
    }

    render() {
        return (
            <View style={{ flex: 1, backgroundColor: '#000000' }}>
                <InstagramLikePicker
                    onClose={()=>this.onClose()}
                    onCropped={(croppedUri) => this.onCropped(croppedUri)}
                    onSelectImage={(result) => this.onSelectImage(result)}
                    headerTitle="Last Post"
                />
            </View>
        )
    }
}
```

## Props

| Parameter     | type  | required |  default | description   |
| ------------- | ----- | -------- | -------- | ------------- |
| onClose|function|Yes||this will call onclick of cross icon|
| onCropped|function ```js (selectUrl)=>{}```|No||this function return the cropped image url|
| onSelectImage|function ```js (selectUrl)=>{}```|No||call on changing image selection|
|headerTitle|```string```|No|New Post|Header Title|

## Contributing

See the [contributing guide](CONTRIBUTING.md) to learn how to contribute to the repository and the development workflow.

## License

MIT
