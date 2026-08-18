# Resumo Facil

Pagina estatica usada no fluxo de autenticacao do Resumo Facil com o TikTok.

Ela nao e a aplicacao principal. Este repositorio serve como uma pagina de callback/verificacao: recebe o `code` enviado pelo TikTok, mostra o codigo na tela e facilita copiar esse valor para continuar a configuracao no terminal.

## O que tem aqui

- `index.html` com leitura dos parametros da URL.
- Tratamento para retorno com `code`.
- Tratamento para retorno com `error`.
- Botao para copiar o codigo de autorizacao.
- Arquivos `.txt` de verificacao de dominio do TikTok.

## Fluxo

1. O TikTok redireciona o usuario para esta pagina.
2. A pagina procura `code` ou `error` nos parametros da URL.
3. Se houver codigo, ele aparece em destaque.
4. O usuario copia o codigo e cola no terminal onde o script de setup esta aguardando.

## Stack

- HTML
- CSS inline
- JavaScript puro

## Rodando localmente

Como e uma pagina estatica, basta abrir:

```txt
index.html
```

Para simular o retorno com codigo:

```txt
index.html?code=CODIGO_DE_TESTE
```

Para simular erro:

```txt
index.html?error=access_denied&error_description=Permissao%20negada
```

## Observacoes

O repositorio existe para resolver uma parte especifica do fluxo OAuth. Ele nao guarda token, nao faz login sozinho e nao substitui o backend/script que troca o codigo por credenciais.
