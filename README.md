# affly.js

> Controlador de cookies para implementação de pixels de afiliados

## Por que?
Implementar pixels de afiliados não deveria ser algo difícil e além de não ter um monte de passos o mesmo deveria ser algo padrão entre todos os afiliados, hoje cada afiliado trata a implementação de pixels nos parceiros de uma maneira diferente e alguns na maioria das vezes ainda deixa na responsabilidade do cliente o controle de disparo do pixel.

Por isso criamos o Affly, um controlador de cookies que baseado na origem do acesso, marca a o navegador para o futuro disparo na hora da aquisição por parte do usuário.

## Instalação

Para realizar a instalação e configuração do mesmo será necessário a utilização do [Google Tag Manager](googletagmanager.com), caso você não esteja familiarizado com o google tag manager a [métricas boss](http://metricasboss.com.br/google-tag-manager/) tem diversos posts em português falando sobre o assunto.

Após estar com o seu google tag manager criado e instalado, será necessário criar uma tag customizada para implementação do script abaixo, segue o passo a passo.


### 1.  Abra o seu google tag manager e na tela inicial de seu container clique em "adicionar uma nova tag"
!()[]

### 2.  Clique no botão configuração da tag
!()[]

### 3.  Selecione o item HTML customizado
!()[]

### 4.  No campo HTML copie e cole o script abaixo
!()[]

``` html
<script>
!function(e,n){var r={windowConversion:n||30,cookieName:e||"affly_origin"},o=function(){var e={};window.location.href.replace(/[?&]+([^=&]+)=([^&]*)/gi,function(n,r,o){e[r]=o});return e},t=o(),i=function(){if(t.utm_source){var e=new Date;e.setTime(e.getTime()+24*r.windowConversion*60*60*1e3);var n="expires="+e.toUTCString();return document.cookie="affly_origin="+t.utm_source+";"+n+";path=/"}return!1},u=function(){return document.cookie="affly_origin=;expires=Thu, 01 Jan 1970 00:00:01 GMT;"},c=function(){for(var e=document.cookie.split(";"),n=0;n<e.length;n++){for(var o=e[n];" "==o.charAt(0);)o=o.substring(1);if(0==o.indexOf(r.cookieName))return o.substring(name.length,o.length)}return!1},f=function(){var e=document.referrer,n=new RegExp("(https|http)://www.google.com.br");return!!n.test(e)&&!!("google"===t.utm_source&&"cpc"===t.utm_medium||t.gclid)},a=function(){c()?f()&&u():i()};return a()}();
</script>
```

### 5. Clique no botão acionamento
!()[]

### 6. Seleciona a opção All pages
!()[]

### 7. Clique no botão salvar
!()[]

### 8. Adicione um nome a sua tag e pronto xD

## Instalação para os preguiçosos ;)
Caso voce já esteja familiarizado com o Google Tag Manager, você já sabe que é possível importar um container via json, então só copiar o código e exportar no GTM.

``` json
{
    "exportFormatVersion": 2,
    "exportTime": "2016-11-21 16:32:41",
    "containerVersion": {
        "path": "accounts/922909217/containers/6040521/versions/1",
        "accountId": "922909217",
        "containerId": "6040521",
        "containerVersionId": "1",
        "name": "Instalando tag affly",
        "container": {
            "path": "accounts/922909217/containers/6040521",
            "accountId": "922909217",
            "containerId": "6040521",
            "name": "affly.com.br",
            "publicId": "GTM-MC32K4F",
            "usageContext": [
                "WEB"
            ],
            "fingerprint": "1479745869163",
            "tagManagerUrl": "localhost:9001/#/container/accounts/922909217/containers/6040521/workspaces?apiLink=container"
        },
        "tag": [
            {
                "accountId": "922909217",
                "containerId": "6040521",
                "tagId": "1",
                "name": "CUSTOM - AFFLY",
                "type": "html",
                "parameter": [
                    {
                        "type": "TEMPLATE",
                        "key": "html",
                        "value": "<script>\n!function(e,n){var r={windowConversion:n||30,cookieName:e||\"affly_origin\"},o=function(){var e={};window.location.href.replace(/[?&]+([^=&]+)=([^&]*)/gi,function(n,r,o){e[r]=o});return e},t=o(),i=function(){if(t.utm_source){var e=new Date;e.setTime(e.getTime()+24*r.windowConversion*60*60*1e3);var n=\"expires=\"+e.toUTCString();return document.cookie=\"affly_origin=\"+t.utm_source+\";\"+n+\";path=/\"}return!1},u=function(){return document.cookie=\"affly_origin=;expires=Thu, 01 Jan 1970 00:00:01 GMT;\"},c=function(){for(var e=document.cookie.split(\";\"),n=0;n<e.length;n++){for(var o=e[n];\" \"==o.charAt(0);)o=o.substring(1);if(0==o.indexOf(r.cookieName))return o.substring(name.length,o.length)}return!1},f=function(){var e=document.referrer,n=new RegExp(\"(https|http)://www.google.com.br\");return!!n.test(e)&&!!(\"google\"===t.utm_source&&\"cpc\"===t.utm_medium||t.gclid)},a=function(){c()?f()&&u():i()};return a()}();\n</script>\n"
                    },
                    {
                        "type": "BOOLEAN",
                        "key": "supportDocumentWrite",
                        "value": "false"
                    }
                ],
                "fingerprint": "1479745869163",
                "firingTriggerId": [
                    "2147479553"
                ],
                "tagFiringOption": "ONCE_PER_EVENT"
            }
        ],
        "builtInVariable": [
            {
                "accountId": "922909217",
                "containerId": "6040521",
                "type": "PAGE_URL",
                "name": "Page URL"
            },
            {
                "accountId": "922909217",
                "containerId": "6040521",
                "type": "PAGE_HOSTNAME",
                "name": "Page Hostname"
            },
            {
                "accountId": "922909217",
                "containerId": "6040521",
                "type": "PAGE_PATH",
                "name": "Page Path"
            },
            {
                "accountId": "922909217",
                "containerId": "6040521",
                "type": "REFERRER",
                "name": "Referrer"
            },
            {
                "accountId": "922909217",
                "containerId": "6040521",
                "type": "EVENT",
                "name": "Event"
            }
        ],
        "fingerprint": "1479745926609",
        "tagManagerUrl": "localhost:9001/#/versions/accounts/922909217/containers/6040521/versions/1?apiLink=version"
    }
}
```
