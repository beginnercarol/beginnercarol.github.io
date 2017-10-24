---
layout: post
title: webpack 使用 css-modules
date: 2017-10-24 22:44:00.000000000 +09:00
tags: js 
---

***

# Webpack css-module
将分散的 css 文件组合到一起

+ 打开 css-modules 模块

```
//package.json
var webpack = require('webpack');

module.exports={
    entry:['./src/script/main.js'],
    output:{
        path:__dirname + '/dist/js',
        filename:'bundle.js'
    },
    devServer:{
        inline:true,
        port:3002
    },
    module:{
        loaders:[
            {
                test:/\.js$/,
                exclude:/node_modules/,
                loader:'babel-loader',
                query:{
                    presets:['react','latest']
                }
            },
            {
                test:/\.css$/,
                loader:'style-loader!css-loader?modules’,//打开 css-modules模块
            }
        ]
    }
}

```


+ 在 js 文件中引入 css

```
//xx.js
import React from 'react';
import CarouselIndicator from './carousel-indicator';
import CarouselItems from './carousel-items';
import style from '../../css/carousel.css';


class Carousel extends React.Component {
    render(){
        //let {count,items} = this.props;
        console.log(this.props.items);
        let items  =this.props.items;
        let count  =items.length;
        const width = 100*count +"%";
        return (
            <div className={style.carousel} >//注意要加{}
                <CarouselItems items = {items} count = {count} style={{width:width}}/>
                <CarouselIndicator count = {count} />
            </div>    
        );
    }
}

export default Carousel;

```















