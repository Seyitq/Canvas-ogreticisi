# Canvas-ogreticisi
**Canvas öğreticisi**

Basit bir örnekle başlayalım.

loadImage('link') resim yükler.

fillText(merhaba, 30, 60) x30 y60 kordinatına merhaba yazdırdık kısacası fillText yazı yazmaya yarar.

measureText('metin') metnin uzunluğunu ölçtük.



fillStlye = 'BLACK' anladığınız gibi rengi ayarladık :)

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

loadImage('https://cdn.discordapp.com/attachments/825378546347802634/827925630632460338/hand-painted-watercolor-background-with-sky-clouds-shape_24972-1095.jpg').then((calaninanasinisikim) => {//şu kısımda resim yazsakda olurdu çalan piçler var kusurbakmayın

  ctx.drawImage(calaninanasinisikim, 50, 0, 70, 70)

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

 
