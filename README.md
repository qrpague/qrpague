# Padrão QRPague

Projeto para a padronização de código QR entre as instituições financeiras brasileiras para permitir uma melhor experiência de seus usuários de mobile banking. A solução, toda baseada na padronização de APIs entre os participantes do ecossistema financeiro nacional, permitirá uma nova experiência no varejo, comércio eletrônico, mobile commerce, transferência digital, pagamento de taxas e tributos. Por meio da sua adoção, espera-se manter a posição brasileira de nação com sistema financeiro moderno e forte.

<p align="center">
  <img src="https://raw.githubusercontent.com/qrpague/qrpague/master/imagens/QRPague-Pagamento.png" width="400" title="Escopo da solução">
</p>

## Escopo

O padrão QRPAGUE poderá ser utilizado para os mais diferentes propósitos: da transferência interbancária ao pagamento de tributos. Por meio do mobile banking da sua instituição financeira, seus usuários poderão realizar transferências, pagar contas no comércio, pagar tributos, comprar pela internet de seu desktop ou celular, de forma simplificada.

## Funcionamento

<p align="center">
  <img src="https://raw.githubusercontent.com/qrpague/qrpague/master/imagens/QRPague-Funcionamento.png" width="500" title="Fluxo simplificado.">
</p>

Usando APIs padronizadas, as instituições financeiras poderão emitir operações para beneficiários e receber de terceiros, operações estas que poderão ser de diferentes naturezas. Como as APIs serão as mesmas entre as instituições, interconectando seus servidores, as operações poderão ser liquidadas automaticamente, tornando o processo seguro, simples e transparente.

## Segurança

No que se refere à segurança das API's RESFTful, o padrão QRPAGUE busca trabalhar dentro das principais recomendações da OWASP. A primeira recomendação é a utilização de canais HTTPS entre servidores e clientres, visando proteger as informações sensíveis de acesso não autorizado, através do uso de SSL/TLS. Também vislumbra a utilização de headers de segurança e validações de content-type.

Complementar ao descrito acima, a comunicação só poderá ocorrer entre instituições financeiras autorizadas numa rede privada com acesso VPN. Para garantir a segurança e a integridade das operações, o padrão QRPague prevê que todos os objetos trafegados na rede sejam assinados e encriptados. Todas as chaves públicas serão disponibilizadas pelos emissores e disponibilizadas na pasta “chaves” deste projeto com a respectiva identificação da instituição. 

## Leitura do QRCode

Um dos objetivos da solução QRPAGUE é que a partir da leitura do QRCode fornecido pela instituição financeira seja possível abrir o aplicativo mobile banking desejado pelo usuário para tratar a operação financeira digital. Para esse objetivo será possível utilizar um content type customizado que permitirá o usuário do mobile selecionar um aplicativo para tratar tal finalidade.

### Content/type

Mesmo que as informações trafegadas sejam objetos JSON, existe a possibilidade de tratá-lo como um content type customizado para que o dispositivo mobile consiga prover para o usuário opções de aplicativos instalados que conseguem efetuar sua leitura. Para tal, os objetos JSON trafegados para as operações financeiras serão vinculadas ao content type "application/qrpague".

## A API RESTful

Os endpoints para tratar as operações de geração dos QRCodes está conforme o conjunto de operações abaixo. A documentação complenta a API pode ser vista [aqui](http://editor.swagger.io?url=https://raw.githubusercontent.com/qrpague/qrpague/master/swagger.yaml).

| Operação |      Endpoint                 |  Descrição                                          |
|:---------|:------------------            |:---------------------------------------------------:|
| POST     | /operacao                     | Endpoit para gerar um QRCode de operação financeira digital através do padrão QRPAGUE. |
| GET      | /operacoes                    | Endpoit para recuperar informações de operações financeiras digitais gerada através do QRPAGUE. |
| GET      | /operacoes/{uuid}             | Endpoit para consultar informações de uma operação financeira digital gerada através do QRPAGUE. |
| POST     | /operacoes/{uuid}/autorizacao | Endpoit para autorizar uma operação financeira digital gerada através do QRPAGUE. |
| POST     | /operacoes/{uuid}/confirmacao | Endpoit para receber a confirmação de execução com sucesso de uma operação financeira digital gerada através do QRPAGUE. |
