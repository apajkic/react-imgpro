# react-imgpro
![status](https://img.shields.io/badge/version-1.0.0-brightgreen.svg)
![status](https://img.shields.io/badge/size-13KB-brightgreen.svg)
![status](https://img.shields.io/badge/status-stable-brightgreen.svg)
![yarn](https://img.shields.io/badge/yarn-0.21.3-blue.svg)
![license](https://img.shields.io/packagist/l/doctrine/orm.svg)

> Image Processing Component for React

<p align="center">
  <img src="./react-impro.png" height="200" width="200">
</p>

## Introduction

`react-imgpro` is a image processing component for React. This component processes an image with filters supplied as props and returns a [base64](https://en.wikipedia.org/wiki/Base64) image. 

**Basic example -**

```jsx
class App extends React.Component {
  state = { src: '', err: null }
  
  render() {
    return (
      <ProcessImage
        image='http://365.unsplash.com/assets/paul-jarvis-9530891001e7f4ccfcef9f3d7a2afecd.jpg'
        colors={{
          mix: {
            color: 'mistyrose',
            amount: 10
          }
        }}
        resize={{ width: 500, height: 500, mode: 'bilinear' }}
        processedImage={(src, err) => this.setState({ src, err, })}
      />     
    )
  }
}
```

<p align="center">
<img src="./introduction.jpg" height="400" width="800">
</p>

## Why ?

<p align="center">
  <img src="https://i.gyazo.com/16f09cba02f9dfeb272cc574f9fbbcff.png">
</p>

I was working on a project last month which involved a lot of image processing and I'd have to rely on third party libraries. But before using them directly, I'd have to learn different concepts in gl (shaders) and then try to implement them in React. The difficult part was not the learning but the verbosity, boilerplate code and redundancy introduced by the libraries in the codebase. It was getting difficult to organise all the things 😞

So I wanted a layer of abstraction which would make it easy to manipulate the colors of the image, applying filters and gl shaders efficiently with ease. And React's component based model was perfect for hiding all the implementation details in a component 😄 

## Demo

<p align="center">
  <img src="http://g.recordit.co/XmhTiP84TD.gif">
</p>

## Install

```
npm install react-imgpro
```

This also depends on `react` so make sure you've installed it.


## Usage

```jsx
import React from 'react';
import ProcessImage from 'react-imgpro';

class App extends React.Component {
  state = {
    src: '',
    err: null
  }
  
  render() {
    return (
      <ProcessImage
        image='http://365.unsplash.com/assets/paul-jarvis-9530891001e7f4ccfcef9f3d7a2afecd.jpg'
        resize={{ width: 500, height: 500 }}
        colors={{
          mix: {
            color: 'mistyrose',
            amount: 20
          }
        }}
        processedImage={(src, err) => this.setState({ src, err})}
      />
    )
  }
}

```

## Documentation

See the detailed documentation [here](./Docs).

## Contributing

[Contributing guide](https://github.com/nitin42/react-imgpro/blob/master/Docs/CONTRIBUTING.MD)

## License

MIT

<a href="https://app.codesponsor.io/link/FCRW65HPiwhNtebDx2tTc53E/nitin42/react-imgpro" rel="nofollow"><img src="https://app.codesponsor.io/embed/FCRW65HPiwhNtebDx2tTc53E/nitin42/react-imgpro.svg" style="width: 888px; height: 68px;" alt="Sponsor" /></a>
