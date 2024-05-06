## Search String PII
Esta extensão para o Burp Suite permite pesquisar padrões numéricos e strings sensíveis em solicitações e respostas HTTP, identificando potencialmente informações pessoais identificáveis (PII) como CPFs (Cadastro de Pessoas Físicas) no tráfego de rede – Request/Response

## Funcionalidades Principais
- Pesquisa passiva por strings sensíveis em respostas HTTP.
- Interface de usuário para adicionar, salvar e exportar strings sensíveis como Wordlist.
- Integração com o Burp Suite para análise de segurança de aplicativos web.

## Como instalar
**1. Instalação:**
- Download Jython Standalone 2.7.3
- Configurar o apontamento Jython em Settings > Extensions > Python environment Location
- Download do SearchStringPII.py 
- Add extensão dentro do Burp Suit in Burp Extensions, add
- Extension Details > Extension Type -> Python & Select archive. 
- Certifique-se de que a extensão esteja ativada.

**2. Configuração:**
- Na guia "Settings", adicione as strings sensíveis que deseja pesquisar ou upload da wordlist de sua preferência.
- Clique em "Save" para salvar as strings sensíveis adicionadas.
- Recarregue o SearchStringPII.py, clicando no boxe em Burp Extensions

**3. Execução:**
A extensão realizará automaticamente a busca por strings sensíveis durante as verificações passivas do Burp Suite.
Se uma correspondência for encontrada, um alerta será gerado no Burp Suite.

**Exportação de Strings Sensíveis:**
Você pode exportar as strings sensíveis adicionadas para um arquivo JSON clicando em "Export" na guia "Settings".

## Classe Principal
BurpExtender: Classe principal que estende as interfaces IBurpExtender, IScannerCheck e ITab, registrando a extensão no Burp Suite, definindo a lógica de verificação passiva e configurando a interface de usuário.

## Classes Auxiliares
CustomScanIssue: Implementa a interface IScanIssue, representando um problema de segurança identificado pela extensão, como a presença de uma string sensível em uma resposta HTTP.

## Métodos Principais
registerExtenderCallbacks: Método chamado ao registrar a extensão no Burp Suite, inicializando a interface de usuário e carregando as strings sensíveis adicionadas anteriormente.
doPassiveScan: Método que executa a verificação passiva em uma solicitação e resposta HTTP, procurando por strings sensíveis adicionadas pelo usuário.

## Interface de Usuário
- Settings Tab: Permite ao usuário adicionar, salvar e exportar strings sensíveis e wordlist de sua preferência
- Adicione as palavras de cunho sensível: Campo de texto para adicionar as strings sensíveis.
- Save: Botão para salvar as strings sensíveis adicionadas.
- Import: Botão para importar strings sensíveis de um arquivo JSON.
- Export: Botão para exportar as strings sensíveis adicionadas para um arquivo JSON.

## Considerações sobre o Código
- O código foi escrito para ser facilmente compreensível e extensível.
- As strings sensíveis são salvas e carregadas a partir das configurações da extensão.
- A verificação passiva é realizada iterando sobre as strings sensíveis e procurando por correspondências nas respostas HTTP.

Esta documentação fornece uma visão geral do funcionamento da extensão e como ela pode ser usada para identificar strings sensíveis em solicitações e respostas HTTP.
