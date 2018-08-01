# bnbServer

## bnb backend using nodejs & socket.io
   Front-end using cocos-creator: [https://github.com/leviscar/bnb](https://github.com/leviscar/bnb)

## example

//统一通信接口
socket.on(msg,function(data){

});

```js
// 创建房间和加入房间成功后均返回roomInfo信息 传入信息为{name: room1, userInfo: {nickName:a, avataUrl:'xxx', gender:1}}
msg = "roomInfo"
data = {
   code:1,
   data:{
      uuid：asdkjf2123131,
      userInfos:[{
         uuid:asdkjf2123131,
         nickName:'XXX',
         avatarUrl: '123.jpg',
         gender:1,
         isMaster:true
      },{
         uuid:jlkjlo123,
         nickName:'XXX',
         avatarUrl: '123.jpg',
         gender:1
      }]
   }
}
        
// 服务端按FPS向客户端发送游戏当前信息
msg = "roleInfo"
data = [{
            roleIndex:0，
            uuid:asdkjf2123131,
            nickName:'XXX'
            position:{
                x:32,
                y:32
            },
            gameTime:60,
            score:100
        },
        {
            roleIndex:0，
            uuid:asdkjf2123131,
            nickName:'XXX'
            position:{
                x:128,
                y:128
            },
            gameTime:60,
            score:100
        }] 

// 服务端向客户端返回新放泡泡信息
msg = "paopaoCreated"
data = {
    uuid:asdkjf2123131,
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
        {x:1,y:1,uuid:asdkjf2123131,itemCode:101}
}

//服务端向客户端返回小怪物信息
msg = "monsterInfo"
data =  [{
            monsterIndex: 0,
            name:monster0,
            position:{
                x:64,
                y:64
            },
        },
        {
            monsterIndex: 1,
            name:monster1,
            position:{
                x:128,
                y:128
            },
        }

//服务端向客户端返回游戏结束信息
msg = "end"
data = {
         {winner.nickName + ' 获胜!'}
}

//服务端向客户端返回人物被炸信息
msg = "roleBoom"
data = {
        {x:1, y:1, uuid:asdkjf2123131}
}

```
