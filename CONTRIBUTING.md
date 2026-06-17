# Guia de Contribuição

Este documento define o padrão de contribuição para os repositórios da equipe de robótica.

## Fluxo de trabalho

1. Toda alteração deve ser feita em uma branch separada.
2. A branch deve ter um nome claro e seguir o padrão da equipe.
3. O commit deve seguir o padrão definido neste documento.
4. A alteração deve ser enviada por Pull Request.
5. O Pull Request deve ser revisado antes do merge na branch principal.

## Organização dos repositórios

A nomenclatura dos repositórios ativos deve seguir a seguinte estrutura:

```txt
{Categoria}_{Nome do robô}_{Função do repositório}
```

Exemplos:

```txt
Home_UDH1_navigation
Home_UDH1_vision
Home_UDH1_firmware
```

Os repositórios de desenvolvimento devem permanecer privados enquanto estiverem em andamento, sendo utilizados internamente pela equipe para testes, implementação, documentação e evolução dos projetos.

Para evitar excesso de repositórios ao longo dos anos, a identificação por competição não deve ser aplicada diretamente aos repositórios internos de desenvolvimento. Esses repositórios devem manter nomes fixos e representar os módulos ativos do projeto.

Após cada competição, quando houver necessidade de divulgação pública, poderá ser criado um repositório específico para a versão final apresentada, seguindo o padrão:

```txt
{Competição}{Ano}_{Nome do robô}
```

Exemplo:

```txt
OBR2026_UDH1
```

Esse repositório público deve reunir os arquivos finais, códigos, documentações e materiais necessários para consulta externa. Após a publicação, ele poderá ser arquivado para preservar o histórico técnico da equipe sem interferir nos repositórios ativos de desenvolvimento.

Documentações gerais e materiais de apoio que não pertencem a um robô específico poderão utilizar uma nomenclatura simplificada:

```txt
Docs_team_guidelines
Docs_competition_rules
Support_training_materials
```

Dessa forma, a organização separa claramente:

* repositórios privados em desenvolvimento;
* repositórios públicos pós-competição;
* repositórios de documentação e materiais de apoio;
* repositórios arquivados para histórico técnico.

## Padrão de branches

Utilize nomes claros, objetivos e padronizados para as branches.

```txt
feature/nome-da-funcao
fix/nome-da-correcao
docs/nome-da-documentacao
refactor/nome-da-melhoria
chore/nome-da-manutencao
test/nome-do-teste
```

Exemplos:

```txt
feature/calibracao-qtr
fix/correcao-leitura-sensor
docs/guia-montagem
refactor/organiza-codigo-principal
chore/organiza-estrutura-repositorio
test/teste-sensor-qtr
```

## Padrão de commits

Os commits devem seguir o seguinte padrão:

```txt
tipo: descrição objetiva da alteração
```

Tipos principais:

```txt
feat     = quando adicionar uma nova função
fix      = quando corrigir um erro
docs     = quando alterar documentação
refactor = quando reorganizar ou melhorar o código sem mudar sua função
chore    = configuração, manutenção ou estrutura
test     = criação ou alteração de testes
```

Exemplos:

```txt
feat: adiciona calibração do sensor QTR
fix: corrige leitura incorreta do sensor
docs: atualiza README do projeto
refactor: organiza funções do código principal
chore: reorganiza estrutura de pastas
test: adiciona teste de leitura dos sensores
```

## Pull Requests

Toda alteração deve ser enviada por Pull Request antes de ser adicionada à branch principal.

O Pull Request deve conter:

- descrição clara do que foi alterado;
- tipo de alteração realizada;
- testes realizados;
- issues relacionadas, se houver;
- observações importantes para revisão.

## Boas práticas

Antes de abrir um Pull Request, verifique se:

- [ ] A branch foi criada a partir da branch principal atualizada.
- [ ] O código ou documento foi revisado antes do envio.
- [ ] O commit segue o padrão da equipe.
- [ ] A documentação foi atualizada, se necessário.
- [ ] Arquivos desnecessários não foram enviados.

## Arquivos que não devem ser enviados

Evite enviar arquivos temporários, cache, builds e arquivos gerados automaticamente.

Exemplos:

```txt
build/
install/
log/
__pycache__/
.venv/
.cache/
node_modules/
```

## Organização da branch principal

A branch principal deve conter apenas versões revisadas, organizadas e funcionais do projeto.

Alterações incompletas, testes experimentais ou códigos em desenvolvimento devem permanecer em branches separadas até serem revisados e aprovados.

## Regra principal

Organização, clareza e rastreabilidade são prioridades nos repositórios da equipe.