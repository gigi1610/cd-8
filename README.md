Faça um servidor web para responder requisições com diferentes status HTTP, os quais devem estar de acordo com os parâmetros enviados pelo placeholder nas requisições. Exemplo: a rota “/listar/50” vai retornar o HTTP 404; a rota /listar/10 vai retornar o HTTP 200 com alguma string.

Trabalhe esse código em seu IDE, suba ele para sua conta no GitHub e compartilhe o link desse projeto no campo ao lado para que outros desenvolvedores possa const express = require('express');
const app = express();
const port = 8080;

app.get('/', (req, res) => {
    res.send('GET request to the home page');
});

app.get('/about', (req, res) => {
    res.send('GET request to the about page');
});

app.post('/create', (req, res) => {
    res.send('POST request to create a new item');
});

app.put('/update/:id', (req, res) => {
    res.send(`PUT request to update the item with id ${req.params.id}`);
});

app.delete('/delete/:id', (req, res) => {
    res.send(`DELETE request to delete the item with id ${req.params.id}`);
});

app.listen(port, () => {
    console.log(`Servidor rodando na porta ${port}`);
});
