---
title: 'Material-uiのmakestyleにて、複数のクラスを動的に指定する方法'
date: 2019-10-14T15:28:36+09:00
tags: [React, Front, CSS]
draft: false
archives: '2019'
author: Amatsuki
---

## TL;DR

1. class データを string 配列として持つ
2. `配列.join(' ')`を該当の`className={}`の中に記述する

## 概要

最近、React についての勉強を行っていたところ、`class`の指定に手間取ってしまったのでメモ。
方法としては、探したところ、以下 2 つがあるみたい。

1. class 名の配列を作成して、最後に join で配列の間に``を入れて出力
2. `className`の中で、２つの class 名を呼び出す。

汎用性があるのは方法 1 のほうだと思われます。

面倒くさいのでソースベタ貼りしてます。  
`Box`は`Material-ui`の Util-component です。

## 最後に各クラスを join でくっつける方法

```tsx
return (
  <Box
    display="flex"
    alignItems="center"
    justifyContent="center"
    className={classes.block}
  >
    {(() => {
      const discClass: string[] = [classes.disc];

      if (props.discStatus === DiscStatus.White) {
        discClass.push(classes.discWhite);
      } else if (props.discStatus === DiscStatus.Black) {
        discClass.push(classes.discBlack);
      }
      return (
        <Box
          component="div"
          onClick={handleOnClickDisc}
          className={discClass.join(' ')}
        ></Box>
      );
    })()}
  </Box>
);
```

## className に２つの class 名を直接入れる方法

```tsx
return (
  <Box
    display="flex"
    alignItems="center"
    justifyContent="center"
    className={classes.block}
  >
    {(() => {
      if (props.discStatus === DiscStatus.White) {
        return (
          <Box
            component="div"
            className={`${classes.disc} ${classes.discWhite}`}
          ></Box>
        );
      } else if (props.discStatus === DiscStatus.Black) {
        return (
          <Box
            component="div"
            className={`${classes.disc} ${classes.discBlack}`}
          ></Box>
        );
      } else if (props.discStatus === DiscStatus.Empty) {
        return <Box component="div" className={classes.disc}></Box>;
      }
    })()}
  </Box>
);
```

## 参考

https://material-ui.com/styles/basics/
