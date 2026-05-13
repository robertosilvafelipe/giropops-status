# Capítulo 3 — Edição de Texto (Vim + VS Code Remote)

> **Referência:** _Descomplicando Linux para Cloud Native_, Capítulo 3.
> **Pré-requisitos:** Capítulo 2 concluído — código da aplicação em `/opt/giropops-status/app/`.

## Objetivo da semana

Dominar as duas situações reais do dia a dia:

- **Crise (Vim):** você está logado via SSH, precisa consertar uma linha e sair. Sem mouse, sem GUI, sem saída fácil.
- **Conforto (VS Code Remote):** você vai desenvolver coisa maior e quer o IDE completo editando arquivos no servidor como se fossem locais.

Esta semana você pratica os dois editando o **código real** do Giropops Status.

## O que fazer com o giropops-status nesta semana

### 1. Modo sobrevivência: editar `app.py` com Vim no servidor

Sem sair da conexão SSH da VM:

```bash
cd /opt/giropops-status/app
vim app.py
```

**Exercícios pedagógicos (o livro explica cada um):**

- Modo Normal → Insert → Normal (pratique `i`, `Esc`, `a`, `o`)
- Busca com `/health` (encontre a rota `/health` no código)
- `:set number` para ativar numeração
- Mudar a string de versão no `/version` (ex: `"1.0.1"`)
- Salvar com `:w`, sair com `:wq`
- Voltar com `vim app.py` e desfazer (`u`) até o original
- Criar um `~/.vimrc` básico com as configurações recomendadas no livro

### 2. Modo produtividade: editar `templates/index.html` com VS Code Remote

No seu notebook:

1. Instale a extensão **Remote - SSH** do VS Code
2. Conecte na VM usando o alias do `~/.ssh/config` (cap 1)
3. Abra a pasta `/opt/giropops-status/app/`
4. Edite `templates/index.html` e mude o `<title>` para algo como `"Meu Giropops Status"`
5. Salve — observe que o arquivo no servidor já está atualizado

### 3. Ler sem editar

Pratique os comandos de leitura:

```bash
cat app.py | head -30             # primeiras 30 linhas
tail -20 app.py                   # ultimas 20 linhas
less app.py                       # paginacao (q para sair)
wc -l app.py                      # quantas linhas o arquivo tem
```

### 4. Comparar versões com `diff`

Faça uma cópia, altere algo e compare:

```bash
cp app.py /tmp/app.py.bak
vim app.py    # altere qualquer coisa
diff /tmp/app.py.bak app.py
```

## Novidades do pacote desta semana

Nenhum arquivo novo — o capítulo é sobre **editar o existente**. Mas guarde o que você alterou: a versão customizada do `app.py` e do `index.html` é o artefato desta semana.

## Entrega

- [ ] Mudou a versão exibida em `/version` via Vim (no servidor)
- [ ] Mudou o `<title>` do dashboard via VS Code Remote
- [ ] Tem um `~/.vimrc` próprio no servidor
- [ ] Consegue explicar a diferença entre os modos Normal, Insert e Visual do Vim
- [ ] Consegue usar `tail -f` para acompanhar um arquivo em tempo real

Print do dashboard do Giropops Status mostrando o `<title>` alterado + `cat ~/.vimrc` do servidor. Tag: `#cap-03-entrega`.

## Referências no livro

- **Capítulo 3**, seções "Vim Survival", "Nano Emergency", "VS Code Remote SSH", "cat/less/head/tail/diff".
