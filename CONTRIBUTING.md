# Guia de Contribuição

Este documento define os padrões de organização e contribuição para os repositórios da **UnipDroidians Robotics Team**.

## Fluxo de trabalho

Toda alteração deve seguir este processo:

1. Atualizar a branch `main`.
2. Criar uma branch separada.
3. Realizar e revisar as alterações.
4. Criar um commit seguindo o padrão da equipe.
5. Enviar a branch para o GitHub.
6. Abrir um Pull Request.
7. Aguardar a revisão antes do merge.
8. Excluir a branch após a conclusão.

Não faça alterações diretamente na branch `main`.

## Idioma oficial

Para padronizar os repositórios e facilitar a colaboração com equipes, instituições e desenvolvedores externos, o inglês será o idioma oficial utilizado nos elementos técnicos do GitHub.

Devem ser escritos em inglês:

* nomes de repositórios;
* nomes de branches;
* mensagens de commit;
* títulos e descrições de Pull Requests;
* títulos e descrições de issues;
* nomes de tags e releases;
* nomes técnicos de arquivos, pastas, funções e variáveis, quando aplicável.

Exemplos:

```text
home-UDH1-navigation
feature/add-qtr-calibration
fix/correct-sensor-reading
docs/update-installation-guide
```

```text
feat: add QTR sensor calibration
fix: correct sensor reading
docs: update installation guide
```

Não misture português e inglês no mesmo nome ou mensagem.

Documentações internas destinadas ao treinamento dos integrantes poderão permanecer em português quando isso facilitar a compreensão da equipe.

## Organização dos repositórios

### Repositórios ativos

Os repositórios de desenvolvimento devem seguir o padrão:

```text
{categoria}-{NOME-DO-ROBO}-{funcao}
```

Regras:

* categoria em letras minúsculas;
* nome do robô em letras maiúsculas;
* função em letras minúsculas;
* palavras separadas por hífens;
* sem espaços, acentos ou underscores.

Exemplos:

```text
home-UDH1-navigation
home-UDH1-vision
home-UDH1-firmware
home-UDH1-description
home-UDH1-bringup
home-UDH1-interaction
home-UDH1-guide
```

Os repositórios ativos de desenvolvimento devem permanecer privados enquanto estiverem em andamento.

A identificação de competição ou ano não deve ser adicionada aos repositórios internos. Esses repositórios devem manter nomes fixos e representar os módulos ativos de cada robô.

### Repositórios públicos de competição

Após uma competição, poderá ser criado um repositório público para registrar a versão final apresentada.

O padrão será:

```text
{COMPETICAO}{ANO}-{NOME-DO-ROBO}
```

Exemplos:

```text
OBR2026-UDH1
```

Esse repositório deve reunir os códigos, documentos e arquivos finais autorizados para consulta externa.

Após a publicação, ele poderá ser arquivado para preservar o histórico técnico da equipe.

### Documentações e materiais gerais

Repositórios que não pertencem a um robô específico podem utilizar nomes simplificados:

```text
docs-team-guidelines
docs-competition-rules
support-training-materials
```

Utilize letras minúsculas e hífens como separadores.

## Padrão de branches

Toda alteração deve ser realizada em uma branch separada.

O padrão será:

```text
tipo/descricao-curta
```

Tipos oficiais:

```text
feature/      nova funcionalidade
fix/          correção de erro
docs/         alteração de documentação
refactor/     reorganização ou melhoria interna
chore/        manutenção, configuração ou estrutura
test/         criação ou alteração de testes
integration/  integração de alterações maiores ou externas
```

Exemplos:

```text
feature/add-qtr-calibration
fix/correct-sensor-reading
docs/add-assembly-guide
refactor/organize-main-code
chore/organize-repository-structure
test/test-qtr-sensor
integration/ricardo-update
```

Utilize letras minúsculas, sem espaços ou acentos, e separe as palavras com hífens.

## Criando uma branch

Atualize a `main`:

```bash
git switch main
git pull
```

Crie a nova branch:

```bash
git switch -c tipo/nome-da-alteracao
```

Exemplo:

```bash
git switch -c docs/atualiza-guia-instalacao
```

## Padrão de commits

Os commits devem seguir o padrão:

```text
tipo: descricao objetiva da alteracao
```

Tipos oficiais:

```text
feat      nova funcionalidade
fix       correção de erro
docs      alteração de documentação
refactor  reorganização sem mudança de função
chore     manutenção, configuração ou estrutura
test      criação ou alteração de testes
```

> Para branches, utilize `feature/`. Para commits, utilize `feat:`.

Exemplos:

```text
feat: adiciona calibracao do sensor QTR
fix: corrige leitura incorreta do sensor
docs: atualiza README do projeto
refactor: organiza funcoes do codigo principal
chore: reorganiza estrutura de pastas
test: adiciona teste de leitura dos sensores
```

Evite mensagens genéricas como:

```text
alteracoes
atualizacao
teste
corrigido
```

## Criando e enviando um commit

Verifique as alterações:

```bash
git status
```

Adicione os arquivos:

```bash
git add -A
```

Confira novamente:

```bash
git status
```

Crie o commit:

```bash
git commit -m "tipo: descricao objetiva da alteracao"
```

Envie a branch:

```bash
git push -u origin nome-da-branch
```

## Pull Requests

Toda alteração deve ser enviada por Pull Request antes de entrar na branch `main`.

O Pull Request deve informar:

* o que foi alterado;
* o motivo da alteração;
* os testes ou verificações realizados;
* as issues relacionadas, quando houver;
* observações importantes;
* os integrantes responsáveis, quando aplicável.

Antes do merge, revise a aba **Files changed** e confirme que apenas os arquivos necessários estão sendo alterados.

A branch `main` deve ser protegida para impedir alterações diretas e exigir Pull Request antes do merge.

## Boas práticas

Antes de abrir um Pull Request, confirme:

* [ ] A branch foi criada a partir da `main` atualizada.
* [ ] A branch segue o padrão da equipe.
* [ ] Os commits seguem o padrão definido.
* [ ] O código ou documento foi revisado.
* [ ] Os testes necessários foram realizados.
* [ ] A documentação foi atualizada, quando necessário.
* [ ] Arquivos temporários ou desnecessários não foram enviados.
* [ ] A aba **Files changed** foi revisada.

## Arquivos que não devem ser enviados

Não envie arquivos temporários, caches, ambientes locais ou arquivos gerados automaticamente.

Exemplos:

```text
build/
install/
log/
__pycache__/
.venv/
.cache/
node_modules/
```

Esses itens devem ser adicionados ao `.gitignore` quando forem aplicáveis ao projeto.

A pasta `.vscode/` deve ser ignorada quando contiver apenas configurações pessoais. Ela só deve ser versionada quando suas configurações forem úteis e aprovadas para toda a equipe.

Nunca copie a pasta `.git/` de um repositório para outro.

## Organização da branch principal

A branch `main` deve conter apenas versões:

* revisadas;
* organizadas;
* documentadas;
* funcionais;
* aprovadas pela equipe.

Alterações incompletas ou experimentais devem permanecer em branches separadas.

## Após o merge

Depois que o Pull Request for aprovado e mesclado, atualize a `main` local:

```bash
git switch main
git pull
```

Exclua a branch local:

```bash
git branch -d nome-da-branch
```

Caso a branch remota ainda exista:

```bash
git push origin --delete nome-da-branch
```

Atualize as referências remotas:

```bash
git fetch --prune
```

## Regra principal

Organização, clareza, segurança e rastreabilidade são prioridades nos repositórios da equipe.

```text
A main representa a versão oficial.
As branches são utilizadas para desenvolvimento.
Os Pull Requests são utilizados para revisão.
O merge representa a aprovação da alteração.
```