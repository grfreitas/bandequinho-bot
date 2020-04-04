# Bot de Cardápios dos Bandecos da USP

O bandequinho bot tem como objetivo informar os cardápios dos bandecos de forma automatizada em diversas plataformas
diferentes. Em primeira instância as publicações serão realizadas no [twitter](https://twitter.com/bandequinhobot), mas
o código está modularizado de maneira a ser possível adicionar outros lugares como o telegram. O bot realiza o scrapping 
deste site [aqui](https://uspdigital.usp.br/rucard/Jsp/cardapioSAS.jsp?codrtn=8) e faz a publicação diariamente às 10h 
para o almoço e às 16h para a janta dos cardápios dos campus USP butantã.

O scrapper é escrito com selenium e as publicações no twitter são feitas o auxílio da biblioteca threader para
realizar as threads. O programa roda num servidor do Hackerspace do Instituto de Física da USP através de cronjob. 

---

### Instalação:

- Instalação de ambiente virtual
```bash
virtualenv -p /usr/bin/python3.7 venv
```

- Configurações de variáveis de ambiente

```bash
source venv/bin/activate
```

```bash
pip install -r requirements.txt
```
 
```bash
export API_KEY=<API_KEY>
export API_SECRET_KEY=<API_SECRET_KEY>
export ACCESS_TOKEN=<ACCESS_TOKEN>
export ACCESS_TOKEN_SECRET=<ACCESS_TOKEN_SECRET>
```

- Configuração do Cronjob:

`00 10 * * * /path/to/script/run.sh`
`20 16 * * * /path/to/script/run.sh`
