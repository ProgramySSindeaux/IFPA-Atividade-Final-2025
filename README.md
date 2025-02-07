# Carrinho de Compras - SPA com Vue.js e Supabase

## Identificação do Aluno
- André Felipe Sindeaux Sindeaux

## Descrição do Projeto
Este projeto é uma aplicação de página única (SPA) para simular um "Carrinho de Compras" de um site de comércio eletrônico. A aplicação foi desenvolvida utilizando Vue.js e Supabase, e está organizada conforme o padrão MVVM. O layout foi estilizado com Bootstrap para garantir a responsividade.

## Estrutura do Projeto
A aplicação possui duas áreas principais:
1. **Consulta a Produtos** - Exibe uma lista de produtos obtidos a partir de um serviço REST no Supabase.
2. **Carrinho** - Mostra os produtos adicionados pelo cliente no carrinho, permitindo ações de adicionar e remover itens, e finalizando a compra.

## Funcionalidades
- Adicionar itens ao carrinho
- Remover itens do carrinho
- Calcular subtotais e total da compra
- Consultar produtos a partir de um serviço REST (Supabase)
- Salvar dados do carrinho em uma tabela no Supabase

## Requisitos
- Vue.js (versão 3)
- jQuery (versão 3.4.1 ou superior)
- Bootstrap (versão 4.5.2)
- Conta no Supabase

## Instruções para Rodar o Projeto

### Passo 1: Configuração do Supabase
1. Crie um projeto no Supabase.
2. Configure uma tabela chamada `carrinho` com os seguintes campos:
   - `id` (int) - chave primária
   - `nome` (varchar) - nome do produto
   - `quant` (int) - quantidade do produto

### Passo 2: Configuração do Projeto Vue.js
#### Código 1: carrinho-boot
#Chaves de API do projeto#

1. Foi adicinado no código carrinho-boot o URL do projeto no Supabase que direciona para a tabela carrinho, a tabela carrinho não foi pré-definido igual ao codigo lista-carrinho, definimos a tabela acrescentando o trecho:"co/rest/v1/carrinho". 
    Ocódigo ficará assim: const apiUrlCarrinho = 'https://ldwhghwhxxpvdghugemv.supabase.co/rest/v1/carrinho';

2. Foi adicionado a chave de Segurança (serviece_role /  secret) da API do projeto
const apiKey = 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Imxkd2hnaHdoeHhwdmRnaHVnZW12Iiwicm9sZSI6InNlcnZpY2Vfcm9sZSIsImlhdCI6MTczODg1NDU4MiwiZXhwIjoyMDU0NDMwNTgyfQ.2rAYbIrkdCQDX95bX4-jynvq-5mocKVveirPQDJK_iA';
   
3.Foi adicinionado um botão para acessar a página lista-carrinho pra visualizar a lista de compras
<!--     <button type="button" class="btn btn-info" v-on:click="redirectToPage()">Carrinho</button>  -->

4.No fim do código acrescenta-se a função que chama a página lista-carrinho
    redirectToPage(){
          window.location.href = '/lista-carrinho.html';// Substitua pelo caminho da página de destino
        }

    
#### Código 2: lista-carrinho
#Chaves de API do projeto#

1. Foi adicinado no código lista-carrinho o URL do projeto no Supabase que direciona para o projeto shoppingList(lista de compras), a tabela carrinho foi pré-definho dentro do código vue.js desta forma o trecho:"co/rest/v1/carrinho" é removido.
     Ocódigo ficará assim: supabaseUrl: 'https://ldwhghwhxxpvdghugemv.supabase.co', // Substitua pela URL do seu projeto

2. Foi adicionado a apiKey (anon  /  public) da API do projeto
    supabaseKey: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Imxkd2hnaHdoeHhwdmRnaHVnZW12Iiwicm9sZSI6ImFub24iLCJpYXQiOjE3Mzg4NTQ1ODIsImV4cCI6MjA1NDQzMDU4Mn0.ddKJjbzPJuqbKPzZH3R_5UOwDD9qM9WRd81YF1_72ns', // Substitua pela chave anon do seu projeto
        
