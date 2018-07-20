# bnbServer

## bnb backend using nodejs & socket.io
   Front-end using cocos-creator: [https://github.com/leviscar/bnb](https://github.com/leviscar/bnb)

## example

//统一通信接口
socket.on(msg,function(data){

});

```js
// 服务端按FPS向客户端发送游戏当前信息
msg = "roleInfo"
data = [{
            name:'master',
            position:{
                x:32,
                y:32
            },
            gameTime:60,
            score:100
        },
        {
            name:'challenger',
            position:{
                x:128,
                y:128
            },
            gameTime:game.gameTime,
            score:role.score
        }] 

// 服务端向客户端返回新放泡泡信息
msg = "paopaoCreated"
data = {
    name:'master',
    position:{
        x:32,
        y:32
    }
}

// 服务端向客户端返回泡泡爆炸信息，包括爆炸范围数组，爆炸箱子坐标数组，爆炸泡泡数组，生成的道具数组
msg = "boomInfo"
data = {
    boomXYArr:[
                {x:1,y:2},
                {x:1,y:3}
            ],
    boomBoxArr:[
                {x:1,y:1},
                {x:1,y:4}
            ],
    boomPaopaoArr:[
        {x:1,y:2}
    ],
    itemArr:[
        {x:1,y:1,itemCode:101},
        {x:1,y:4,itemCode:102}
    ]
}

// 服务端向客户端返回道具被吃信息
msg = "itemEaten"
data = {
        {x:1,y:1,role:'master'}
}
```