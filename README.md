# Tutorial linux

## Comandos

### awk
- Para manipular textos baseados em padroes.
```sh
awk '/string_procurada/{acao}'
```

- Para imprimir linhas contendo uma string procurada.
```sh
curl -s "https://api.github.com/users/luiscelestino/repos" | awk '/ssh_url/{print}'
```

- Para imprimir a 2a coluna de linhas contendo uma string procurada.
```sh
curl -s "https://api.github.com/users/luiscelestino/repos" | awk '/ssh_url/{print $2}'
```

### cat
- Exibe conteudo de um arquivo.

### cd
- Mudar diretorio.

### chmod
- Mudar permissoes.

### cp
- Copiar arquivos.

### curl
- Para visualizar o codigo de uma url.
```sh
curl <url>
```

- Para visualizar o codigo de uma url de forma silenciada. <br>
  Nao exibe dados sobre o tempo de download.
```sh
curl -s <url>
```

### cut
- Corta coluna de um texto. <br>
  -d: delimitador
```sh
cat logs | cut -d " " f1
```

- Corta uma lista de colunas de um texto. <br>
```sh
cat logs | cut -d " " f6,7,8,9
```

- Corta um range de colunas de um texto. <br>
```sh
cat logs | cut -d " " f6-9
```

- Corta a partir de uma coluna de um texto. <br>
```sh
cat logs | cut -d " " f6-
```

- Corta combiando conjuntos de ranges. <br>
```sh
cat logs | cut -d " " f1-3,6-
```

### find
- Procurando arquivos no sistema com a terminaçao .conf.
```sh
sudo find / -name *.conf
```

- Procurando arquivos no sistema com a terminaçao .conf e indicando a profundidade maxima.
```sh
sudo find / -maxdepth 2 -name *.conf
```

- Procurando arquivos modificados nos ultimos 5 minutos.
```sh
sudo find . -amin 5 *
```

- Procurando arquivos com mais de 100 MB.
```sh
sudo find / -size +100M
```

- Procurando arquivos com mais de 1 GB.
```sh
sudo find / -size +1G
```

### grep
- Procurando recursivamente em todos os arquivos as linhas que contém a palavra 'HTTP'. <br>
  Exibe no formato \<arquivo>:\<linha>.
```sh
grep -r HTTP *
```

- Procurando recursivamente em todos os arquivos as linhas que contém a palavra 'HTTP' ignorando o case. <br>
  Exibe no formato \<arquivo>:\<linha>.
```sh
grep -ir HTTP *
```

- Procurando recursivamente em todos os arquivos as linhas que contém a palavra 'HTTP'. <br>
  Exibe no formato \<arquivo>.
```sh
grep -rl HTTP *
```

- Procurando em um arquivo as linhas que contém a string 'compute'. <br>
  Usando expressoes regulares.
```sh
cat words | grep -E "compute"
```

- Procurando em um arquivo as linhas que começam com a string 'compute'. <br>
  Usando expressoes regulares.
```sh
cat words | grep -E "^compute"
```

- Procurando em um arquivo as linhas que terminam com a string 'compute'. <br>
  Usando expressoes regulares.
```sh
cat words | grep -E "compute$"
```

- Procurando em um arquivo as linhas com exatamente a palavra 'compute'. <br>
  Usando expressoes regulares.
```sh
cat words | grep -E "^compute$"
```

- Procurando em um arquivo as linhas com a palavra 'compute' ou a palavra 'smart'. <br>
  Usando expressoes regulares.
```sh
cat words | grep -E "^compute$|^smart$"
```

- Procurando em um arquivo as linhas que começam com um caracter qualquer seguidos dos caracteres 'oot'. <br>
  Usando expressoes regulares.
```sh
cat words | grep -E "^.oot$"
```

- Procurando em um arquivo as linhas que começam com um caracter 'r' ou 's' seguidos dos caracteres 'oot' e ignorando o case. <br>
  Usando expressoes regulares.
```sh
cat words | grep -iE "^[rs]oot$"
```

- Procurando em um arquivo as linhas que começam com um range de 'r' a 's' seguidos dos caracteres 'oot' e ignorando o case. <br>
  Usando expressoes regulares.
```sh
cat words | grep -iE "^[r-s]oot$"
```

### head
- Mostra as primeiras linhas de um arquivo.

### less
- Exibe arquivo paginado. <br>
  Navegaçao com as setas. <br>
  q: sair
```sh
less <arquivo>
```

### more
- Exibe arquivo paginado. <br>
  space: proxima pagina <br>
  enter: proxima linha <br>
  b: pagina anterior <br>
  q: sair
```sh
more <arquivo>
```

### mv
- Mover arquivos.

### sed
- Para manipular textos.

- Removendo aspas duplas do começo um texto.
```sh
curl -s "https://api.github.com/users/luiscelestino/repos" | awk '/ssh_url/{print $2}' | sed 's/^"//g'
```

- Removendo aspas duplas do começo um texto e aspas duplas com virgula do final de um texto.
```sh
curl -s "https://api.github.com/users/luiscelestino/repos" | awk '/ssh_url/{print $2}' | sed 's/^"//g' | sed 's/",$//g'
```

### sort
- Ordena um texto.

### tail
- Exibir final de um arquivo enquanto esta sendo escrito.
```sh
tail -f <arquivo>
```

- Exibir 3 ultimas linhas de arquivo.
```sh
tail -n 3 <arquivo>
```

### wc
- Contagem de palavras, linhas, caracteres e bytes.

## Vi

### Esc
- Alterna entre o modo texto e o modo linha de comando.

### i(nsert)
- No modo texto, para inserir um texto.

### Sair sem salvar
- No modo linha de comando, usar ':q!'.

### Sair e salvar
- No modo linha de comando, usar ':x'.

### r(eplace)
- No modo texto, para trocar apenas um caracter.

### Salvar arquivo com outro nome sem sair
- No modo linha de comando, usar ':w arquivo2.txt'.

### dd
- No modo texto, para remover ou recortar uma linha.

### 10dd
- No modo texto, para remover ou recortar 10 linhas.

### Salvar sem sair
- No modo linha de comando, usar ':w'.

### Ir para a linha 5
- No modo linha de comando, usar ':5'.

### gg
- No modo texto, para ir para o inicio do arquivo.

### G
- No modo texto, para ir para o final do arquivo.

### Para procurar string no arquivo
- No modo linha de comando, usar ':/string'.

### p
- No modo texto, para colar texto copiado depois da linha selecionada.

### P
- No modo texto, para colar texto copiado antes da linha selecionada.

### u
- No modo texto, para desfazer o ultimo comando.

### yy
- No modo texto, para copiar uma linha.

### 5yy
- No modo texto, para copiar 5 linhas.

### Para substituir a primeira ocorrencia de uma string no arquivo
- No modo linha de comando, usar ':s/antes/depois'.

### Para substituir todas ocorrencias de uma string no arquivo na primeira linha encontrada
- No modo linha de comando, usar ':s/antes/depois/g'.

### Para substituir todas ocorrencias de uma string no arquivo todo
- No modo linha de comando, usar ':%s/antes/depois/g'.
