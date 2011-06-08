Introdução
================
O Pagpress será um plugin desenvolvido para Wordpress 3.0, que viabilizará as vendas dos Guias Conexão Paris. Já existe um plugin operando atualmente no site atual. No entanto, este sistema não está operando corretamente devido aos problemas de cálculo de frete efetuado pelo Pagseguro. Desta forma, será usado o Moip, que oferece uma API completa e que suporte as necessidades do cliente.

Funcionamento
================
O Pagpress vai ser instalado no novo site que será lançado do Conexão Paris. Ele terá que se adaptar as necessidades do site, de usabilidade e experiência dos usuários já analisados pela Voel. Os fluxos básicos constam na proposta. O Plugin será flexível e irá oferecer opções de personalização de acordo com a necessidade do processo de compra.
Soluções existentes
O plugin será o primeiro a atender uma deficiência de não existir uma solução satisfatória de integrar o Wordpress com um sistema básico de compras online, para isto, foram analisadas as seguintes soluções:

Plugin de Wordpress oficial do Pagseguro
-----------------------------------------
Esta foi uma solução estudada para o primeiro projeto, que está no ar atualmente, e foi abandonada pelo fato de não atender necessidades básicas e todo o processo é feito fora do Blog, o que possibilita uma experiência ruim e com sensação de insegurança para o usuário. Além disto, o sistema de pagamento pelo pagseguro foi abandonado por não satisfazer as necessidades do produto.

Plugin de Wordpress para o Moip
-----------------------------------
O Plugin de Wordpress para Moip, apesar de usar o módulo de pagamento escolhido que atende as necessidades do cliente, possui uma integração muito precária, sem opções de pagamento e deixa, assim como no plugin do Pagseguro, que o processo todo ocorra externamente ao site.



Release Map
==========

Abaixo listadas plano de lançamento para a primeira versão:
Cada versão poderá ser acompanhada, pois haverá atualizações constantes na área de testes.

* Versão 0.1
  * Script de deploy
* Versão 0.2
  * Criação de um no tipo de entidade no sistema - O produto
  * Personalização da criação do produto com as possibilidades existentes no worpress
  * Personalização da criação do produto com criação de atributos
* Versão 0.3
  * Integrar API do Moip
  * Utilizar API do Moip para notificar mudanças no status da transação
  * Página de listagem das compras realizadas com os status da transação
* Versão 0.4
  * Oferecer opções de pagamento
  * Integrar opções de pagamento a API
* Versão 0.5
  * Template da lista de produtos
* Versão 0.6
  * Widget da barra lateral
* Versão 0.7
  * Template de detalhe de produto
* Versão 0.8
  * Lightbox para exibir imagem do produto ampliada 
* Versão 0.9
  * Criar página de opções do plugin
* Versão 1.0
  * Gerenciamento do status dos usuários na adminstração do Wordpress

Licença
========
O desenvolvimento do plugin será feito de acordo com a licença GPL2 (http://www.gnu.org/licenses/gpl-2.0.html ), recomendada para o desenvolvimento do plugins do Wordpress.
Este programa é um software livre.
O plugin será publicado no diretório de plugins para wordpress e poderá ser melhorado de forma colaborativa, sem custo algum ao cliente. Além de facilitar a detecção de erros por parte do feedback dos usuários. 

Considerações importantes
============================
A interface de adminstração do wordpress irá respeitar teu padrão e seus elementos de layout
Haverá documentação completa de uso do plugin que estará disponível para consulta no diretório de plugins para wordpress

Uso do Moip
============================
O Moip possui diferentes formas de integração. Desde integrações simples a integrações em que o usuário não necessite deixar o site para fazer o gerenciamento e todo o poder de gerenciamento fica no lado do cliente. No entanto, para se ter a forma mais avançada é necessário no mínimo 6 meses de uso. Isto é uma exigência do serviço. Isto é por motivo de segurança e também possui requisitos que necessitam de um investimento maior para ser colocado em prática, como o certificado da Verisign (http://www.verisign.com.br/ ). Primeiramente, vamos usar uma integração intermediária para futuramente oferecer todos os recursos da API do Moip para tornar o sistema de vendas mais completo.
O que o sistema não irá fazer
Algumas funcionalidades que o Moip oferece e que um sistema de pagamento infere-se a ter, não estarão disponíveis para esta primeira versão, mas poderá ser planejadas para serem usadas em versões posteriores.
Autorizar e cancelar pagamentos
“A ferramenta de Autorizar e Cancelar pagamento lhe possibilita ter um maior controle sobre as transações passadas em sua loja, dessa forma você pode definir quais as transações dever ser canceladas ou quais transações devem ser autorizadas sem a necessidade de passar pela analise do MoIP, a ferramenta perfeita para sistemas de clube de compras e para promoções especiais com base em meta de conversão.
Para uso dessa ferramenta, há a necessidade de um contato especial com o MoIP (api@moip.com.br), em que será configurado que todas as transações permaneçam com o stats de “Em Análise”, cabendo ao vendedor a decisão sobre essas transações acumuladas: Autorizar ou Cancelar.”

Para implementar esta forma de pagamento, é necessário ter um sistema próprio de análise do cartão, para evitar fraudes. Inicialmente iremos utilizar a verifica

Pagamento único
-------------------------------
“Seu sistema irá enviar a instrução para o servidor do MoIP e irá receber uma resposta do processamento. Esta resposta será acompanhada por uma chave TOKEN, que é representada pela própria instrução em si. Ao redirecionar o comprador/pagador ao MoIP juntamente com o TOKEN, o mesmo irá visualizar o pagamento predefinido com as informações que você enviou através do código XML.
Se você enviar todos os dados do comprador, incluindo as informações obrigatórias (nome, e-mail, CEP, logradouro, no, bairro, cidade, estado e telefone fixo), o cliente não irá visualizar a página de checkout para inseri-las novamente. Ele visualizará a página já com as formas de pagamento, pulando uma etapa do processo de checkout.”

Inicialmente o processo de preenchimento dos dados ficarão no Moip. O plugin irá enviar os dados da compra, como o guia e a quantidade. O processo de preenchimento de dados do usuário ficará fora do site.