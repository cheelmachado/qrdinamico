const express = require('express');
const app = express();

app.get('/', (req, res) => {
    const userAgent = req.headers['user-agent'].toLowerCase();
    if (userAgent.includes('android')) {
        res.redirect('https://play.google.com/store/search?q=Muvi&c=apps&hl=pt_BR');
    } else if (userAgent.includes('iphone') || userAgent.includes('ipad')) {
        res.redirect('https://apps.apple.com/br/app/muvi/id6673881917');
    } else {
        res.redirect('https://seuwebsite.com'); // Página genérica caso o SO não seja identificado
    }
});

app.listen(3000, () => console.log('Servidor rodando na porta 3000'));
