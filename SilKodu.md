# Discord-Bot-Sil-Komudu

```javascript
module.exports = {
    name: 'sil',
    description: '',
    execute(message, args){
        if(!message.member.hasPermission('MANAGE_MESSAGES')) return message.channel.send('Mesajları Yönet Yetkisine Sahip Değilsin.')
        message.delete()
        if(!args[0]) return message.channel.send('Lütfen 1 İla 100 Arası Bir Sayı Giriniz.')
        if(args[0] > 100) return message.channel.send('100 Sayısından Büyük Bir Değer Girmeye Çalıştınız.')
        if(isNaN(args[0])) return message.channel.send('Lütfen Geçerli Bir Sayı giriniz')
        message.channel.bulkDelete(args[0]);
        message.channel.send(`${args[0]} Tane Mesaj Silindi.`).then(msg => msg.delete({timeout: 10000}));
    }
}
```
