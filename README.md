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

### find

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

### less
- Exibe arquivo paginado. <br>
  Navegaçao com as setas. <br>
  q: sair
```sh
less /<arquivo>
```

### more
- Exibe arquivo paginado. <br>
  space: proxima pagina <br>
  enter: proxima linha <br>
  b: pagina anterior <br>
  q: sair
```sh
more /<arquivo>
```

### mv
- Mover arquivos.

### tail
- Exibir final de um arquivo enquanto esta sendo escrito.
```sh
tail -f /<arquivo>
```
