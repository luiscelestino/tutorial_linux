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

### env
- Lista variaveis de ambiente e seus valores correspondentes.
```sh
env
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

### lshw
- Exibe detalhes do hardware da maquina.
```sh
sudo lshw
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
