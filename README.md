# qrpague

Projeto para a padronização de código QR entre as instituições financeiras brasileiras para permitir uma melhor experiência de seus usuários de mobile banking. A solução, toda baseada na padronização de APIs entre os participantes do ecossistema financeiro nacional, permitirá uma nova experiência no varejo, comércio eletrônico, mobile commerce, transferência digital, pagamento de taxas e tributos. Por meio da sua adoção espera-se manter a posição brasileira de nação com sistema financeiro moderno e forte.

<p align="center">
  <img src="https://raw.githubusercontent.com/qrpague/qrpague/master/imagens/QRPague-Pagamento.png" width="400" title="Escopo da solução">
</p>

## Escopo

O padrão QRPAGUE poderá ser utilizado para os mais diferentes propósitos. Da transferência interbancária ao pagamento de tributos. Por meio do mobile banking da sua instituição financeira, seus usuários poderão realizar transferências, pagar contas no comércio, pagar tributos, comprar pela internet de seu desktop ou celular de forma simplificada.

## Funcionamento

<p align="center">
  <img src="https://raw.githubusercontent.com/qrpague/qrpague/master/imagens/QRPague-Funcionamento.png" width="500" title="Fluxo simplificado.">
</p>

Por meio da padronização de APIs entre as instituições financeiras espera-se viabilizar a possibilidade de popularização e populariação  deste padrão.

## Segurança

Ao abordar a questão de segurança, no que tange a segurança das API's RESFTful o padrão QRPAGUE busca trabalhar dentro das principais recomendações da OWASP. Uma das primeiras recomendações é a utilização de HTTPS, visando proteger as informações senssíveis de acesso não autorizado através do uso de SSL/TLS. Também vislumbra a utilização de headers de segurança, validações de content-type e autenticação utilizando fluxos do OAuth 2.0.

Complementar ao descrito àcima, a comunicação só poderá ocorrer entre instituições financeiras autorizadas. As chaves públicas dessas instituições estarão disponíveis entre elas com a finalidade de permitir verificar a integridade das informações assinadas que são trocadas nas operações financeiras. 

## Content-type

(..) "application/qrpague"
