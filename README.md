
### Canvas öğreticisi

•```fillText();``` yazı yazmanıza yarar.

•```fillStyle = 'renk';``` yazının rengini belirler. bazı kardeşlerim türkçe yazıyor yanlış olur :) ve tamamen büyğk harf `WHITE` gibi

•```registerFont('comicsans.ttf', { family: 'Comic Sans' });``` fontu belirler.

•```beginPath();``` Parantez gibi düşünebilirsin işlem aralığı açar.

•```closePath();``` Az önce açtığımız parantezi kapatır. yani işlemi bitirir.

•```rotate();``` metni veya belirlenen şeyi yamultur.

•```measureText('metin');``` Yazılan metnin uzunluğunu ölçer.

•```lineTo();``` Çizgi çekmeye yarar. Parantezin içinr kordinstlstı girmeyi unutmayın.

•```drawImage(tanım, 0, 0, 0, 0);```  Belirlenen resmi çizer yani resime ekler. 0ları kendi kordinatlarınıza gmre değiştirin.

•toBuffer(),

    "ornek.png"

    

resmin uzantısını belirledik bunu d.js de şöyle kullanırız:

```js

     const attachment = new Discord.MessageAttachment(

              canvas.toBuffer(),

              "ornek.png"

            );

            

            message.channel.send(attachment)

```

peki ben bu canvası nasıl tanımlıyacağım

şöyle:

```js

const { createCanvas, loadImage } = require('canvas')

const canvas = createCanvas(200, 200)

const ctx = canvas.getContext('2d')

```

burdaki ctx i toBuffer hariç tüm hepsinde kullanırız yani ```ctx.fillText``` veya ```ctx.lineTo``` gibi 

hepsini telefondan halledtim oazartesi gününr kadar sabredin .D eksiğim veya yanlışım varsa discorddd üzerinden bildirebilirsiniz

Discord:```seyit#6652```

Devamı yarın gelicek telde yaptım hepsini 
```js
const { createCanvas, loadImage } = require('canvas')

const canvas = createCanvas(200, 200)

const ctx = canvas.getContext('2d')

const discord = require('discord.js');

exports.run = async (client, message, args) => {

// muhteşem yazdıralım

ctx.font = '30px Impact'//fontu belirttik

ctx.rotate(0.1)

ctx.fillText('muhteşem!', 50, 100)//burda muhteşemi yazdırması için kordinatları belirttik photshop vs kullanarak dsha basit bir şekilde kordinst belirtebilirsiniz.

ctx.fillStyle = 'WHITE';//renk belirttik

//Şimdi yazımızın altına çizgi çekelim

var seyit = ctx.measureText('muhteşem!')//metnimizin uzunluğunu ölçtük

ctx.strokeStyle = 'rgba(0,0,0,0.5)'

ctx.beginPath()//path açtık

ctx.lineTo(50, 102)//50 den 102ye kadar çizgi 

ctx.lineTo(50 + seyit.width, 102)//metin uzunluğu alıp uzunluğu boyunca çizgi çektik 

ctx.stroke()

//bir resim yükleyelim

loadImage('https://cdn.discordapp.com/attachments/825378546347802634/827925630632460338/hand-painted-watercolor-background-with-sky-clouds-shape_24972-1095.jpg').then((seyitcik) => {//şu kısımda resim yazsakda olurdu çalan piçler var kusurbakmayın

  ctx.drawImage(seyitcik, 50, 0, 70, 70)

           const attachment = new Discord.MessageAttachment(

              canvas.toBuffer(),

              "ornek.png"

            );

            

            message.channel.send(attachment)

})

}

exports.conf = {

  enabled: true,

  guildOnly: false,

  aliases: [],

  permLevel: 0

};

exports.help = {

  name: "merhaba",

  description: "canvas örnek",

  usage: "!merhaba"

};
```

 
