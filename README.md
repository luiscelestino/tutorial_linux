# Tutorial linux

## Comandos

### cat
- Exibe conteudo de um arquivo.

### cd
- Mudar diretorio.

### chmod
- Mudar permissoes.

### cp
- Copiar arquivos.

### cut
- Corta colunas de um texto. <br>
  -d: delimitador
```sh
cat logs | cut -d " " f1
```

### find
-Procurando arquivos no sistema com a terminaçao .conf.
```sh
sudo find / -name *.conf
```

-Procurando arquivos no sistema com a terminaçao .conf e indicando a profundidade maxima.
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
- Procurando recursivamente em todos os arquivos as linhas que contém a palavra HTTP. <br>
  Exibe no formato \<arquivo>:\<linha>.
```sh
grep -r HTTP *
```

- Procurando recursivamente em todos os arquivos as linhas que contém a palavra HTTP ignorando o case. <br>
  Exibe no formato \<arquivo>:\<linha>.
```sh
grep -ir HTTP *
```

- Procurando recursivamente em todos os arquivos as linhas que contém a palavra HTTP. <br>
  Exibe no formato \<arquivo>.
```sh
grep -rl HTTP *
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
