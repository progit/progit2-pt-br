# Contribuindo com o Pro Git em português brasileiro

Obrigado por ajudar a tornar o Pro Git mais claro e útil para quem lê em português.

## Licença e créditos

Ao abrir um pull request, você concorda em fornecer seu trabalho sob a [licença do projeto](LICENSE.asc).
Você também concede a [Ben Straub](https://github.com/ben) e [Scott Chacon](https://github.com/schacon) a licença necessária para eventuais edições impressas.
As contribuições incorporadas são reconhecidas na [lista de colaboradores](book/contributors.asc), gerada a partir do histórico Git.

## Antes de começar

Procure uma issue ou um pull request que já trate do mesmo trecho.
Para uma tradução extensa ou uma decisão de terminologia que afete várias seções, abra primeiro uma issue para combinar o trabalho.

A estrutura da tradução acompanha a edição inglesa em `progit/progit2`.
Não renomeie arquivos, mova capítulos nem altere o build em um pull request de tradução.
Quando a fonte inglesa mudar, a sincronização estrutural será feita separadamente pelos mantenedores.

## Preparando seu fork

Crie um fork de `progit/progit2-pt-br`, clone-o e adicione o repositório canônico como remoto:

```console
git clone git@github.com:SEU_USUARIO/progit2-pt-br.git
cd progit2-pt-br
git remote add upstream https://github.com/progit/progit2-pt-br.git
git fetch upstream
git switch master
git merge --ff-only upstream/master
git switch -c traduzir-nome-da-secao
```

Depois de criar seus commits, envie o branch ao fork e abra um pull request contra `progit/progit2-pt-br:master`:

```console
git push -u origin traduzir-nome-da-secao
```

## Escopo dos pull requests

Prefira um pull request por seção ou por bloco coerente.
Um PR pequeno torna mais simples revisar o idioma, comparar com a fonte inglesa e reaproveitar a tradução quando a estrutura mudar.

Em um PR de tradução:

- traduza e revise a prosa, títulos, legendas e textos explicativos;
- preserve IDs de âncoras, referências cruzadas, diretivas AsciiDoc, caminhos e nomes de arquivos;
- não traduza comandos, opções, saídas de terminal, nomes de API ou código, salvo quando o próprio exemplo exigir texto localizado;
- atualize apenas a porcentagem correspondente em `status.json`;
- evite alterações de infraestrutura, imagens ou formatação sem relação com o trecho traduzido.

Ferramentas de tradução automática ou IA podem ser usadas como apoio.
Quem envia a contribuição continua responsável por revisar integralmente o resultado, conferir o sentido técnico e entregar português natural; traduções automáticas sem revisão não devem ser enviadas.

## Título e descrição do pull request

Escreva o título e a descrição principal em português.
Ao final, inclua uma seção `English summary` com duas ou três frases para que administradores que não leem português entendam o escopo.

Informe:

- a seção ou os arquivos traduzidos;
- o commit ou trecho inglês usado como referência;
- as decisões terminológicas relevantes;
- os comandos de validação executados.

## Validação

Antes de enviar, execute ao menos o build HTML:

```console
bundle install
bundle exec rake book:build_html
```

Quando o ambiente permitir, execute o build completo:

```console
bundle exec rake book:build
```

Consulte o [README](README.asc) para os formatos disponíveis e as versões de ferramentas usadas pela CI.

## Correções no texto original

Se o problema também existir na edição inglesa, abra uma issue ou um pull request em [`progit/progit2`](https://github.com/progit/progit2).
Depois que a correção for aceita lá, ela poderá ser sincronizada com esta tradução.
