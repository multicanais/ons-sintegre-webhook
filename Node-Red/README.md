Exemplo webhook Node-RED
=============

Fluxo de exemplo de um webhook em Node-RED para receber notificações do [SINtegre](https://sintegre.ons.org.br).

## Pré-requisito

Instalar o NodeJS, localmente ou em uma das opções disponíveis em https://nodered.org/docs/getting-started/

## Como executar

```
sudo npm install -g --unsafe-perm node-red
node-red
```

## Exemplo

Importar o arquivo flow-sintegre.json no console do Node-RED e configurar o webhook para o endereço: http://IPEXTERNO:1880/recebesintegre

```json
[{"id":"1bfeaebb.4885b1","type":"tab","label":"Flow 1","disabled":false,"info":""},{"id":"45b51334.5fa73c","type":"http in","z":"1bfeaebb.4885b1","name":"[POST] SINtegre WebHook","url":"/recebesintegre","method":"post","upload":false,"swaggerDoc":"","x":370,"y":240,"wires":[["142bc5cf.d3b40a","e70944fb.676958"]]},{"id":"a45ab284.6b2ad","type":"http response","z":"1bfeaebb.4885b1","name":"[Resp] http","statusCode":"","headers":{},"x":890,"y":240,"wires":[]},{"id":"142bc5cf.d3b40a","type":"debug","z":"1bfeaebb.4885b1","name":"","active":true,"tosidebar":true,"console":false,"tostatus":false,"complete":"payload","targetType":"msg","x":630,"y":340,"wires":[]},{"id":"e70944fb.676958","type":"change","z":"1bfeaebb.4885b1","name":"Resp OK","rules":[{"t":"set","p":"payload","pt":"msg","to":"{ \"codigo\":\"200\", \"msg\":\"Ok\"}","tot":"json"}],"action":"","property":"","from":"","to":"","reg":false,"x":640,"y":160,"wires":[["a45ab284.6b2ad"]]}]
```
