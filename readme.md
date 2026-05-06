<p align="center">
  <img src="imagens/logo_uems.png" alt="Logo da UEMS" width="180">
</p>

# Template de Monografia UEMS em LaTeX

Este projeto é um modelo de monografia em LaTeX para a Universidade Estadual de Mato Grosso do Sul (UEMS), Unidade de Nova Andradina. Ele utiliza a classe `abntex2` e já vem configurado com elementos pré-textuais, capítulos, referências, anexos, apêndices, listas e formatação compatível com trabalhos acadêmicos no padrão ABNT.

Além da estrutura pronta para compilação, o projeto contém orientações de escrita ao longo dos capítulos. Esses textos servem como guia para a produção da monografia e podem ser substituídos pelo conteúdo final do trabalho.

## Estrutura do projeto

- `Monografia_config.tex`: arquivo principal do projeto. Nele estão as configurações gerais, os pacotes utilizados e as chamadas dos arquivos que formam a monografia.
- `edicoes.sty`: arquivo onde devem ser alteradas as informações principais do trabalho, como título, subtítulo, autor, orientador, coorientador, mês e ano.
- `Capitulos/`: pasta com os capítulos textuais da monografia, como introdução, referencial teórico, metodologia, resultados e conclusões.
- `Pre_textual/`: pasta com os elementos pré-textuais, como capa, folha de rosto, resumo, abstract, agradecimentos e listas.
- `Pos_textual/`: pasta com apêndices e anexos.
- `referencias.bib`: arquivo de referências bibliográficas usado pelas citações no texto.
- `imagens/`: pasta para armazenar figuras utilizadas no trabalho.
- `fichaCatalografica/` e `folhaAprovacao/`: pastas destinadas aos PDFs da ficha catalográfica e da folha de aprovação.
- `fontes/`: pasta para arquivos de código-fonte usados como exemplo ou listagem no trabalho.

## Como utilizar

1. Edite os dados do trabalho em `edicoes.sty`.

   Altere os campos:

   ```tex
   \titulo{TÍTULO DO TRABALHO}
   \subtitulo{SUBTÍTULO (SE HOUVER)}
   \autor{INSIRA SEU NOME AQUI}
   \orientador{Prof. Título. Nome completo do Orientador}
   \coorientador{Prof. Título. Nome Completo do Coorientador}
   \mes{MARÇO}
   \ano{2026}
   ```

   Caso não haja subtítulo ou coorientador, comente a linha correspondente usando `%`.

2. Escreva o conteúdo da monografia nos arquivos da pasta `Capitulos/`.

   Os capítulos já possuem textos explicativos sobre o que deve ser escrito em cada parte. Use essas informações como orientação e substitua os trechos de exemplo pelo conteúdo da sua pesquisa.

3. Edite os elementos pré-textuais em `Pre_textual/`.

   Atualize arquivos como:

   - `Resumo.tex`
   - `Abstract.tex`
   - `Agradecimentos.tex`
   - `ListaSiglas.tex`
   - `Dedicatoria.tex`, se for utilizada
   - `Epigrafe.tex`, se for utilizada

4. Adicione imagens na pasta `imagens/`.

   O arquivo principal já define essa pasta como caminho padrão para figuras:

   ```tex
   \graphicspath{ {imagens/} }
   ```

   Assim, uma imagem pode ser chamada no texto apenas pelo nome do arquivo.

5. Cadastre as referências em `referencias.bib`.

   As referências devem ser inseridas em formato BibTeX. O projeto utiliza `abntex2cite`, então as citações podem ser feitas com comandos como:

   ```tex
   \cite{chave}
   \citeonline{chave}
   ```

6. Ative ou desative partes da monografia em `Monografia_config.tex`.

   Alguns elementos estão comentados porque são usados apenas em versões finais, como ficha catalográfica, folha de aprovação, dedicatória, epígrafe, lista de quadros e cronograma. Para incluir um desses arquivos, remova o `%` da linha correspondente.

   Exemplo:

   ```tex
   % \input{Pre_textual/Dedicatoria}
   ```

   Para ativar:

   ```tex
   \input{Pre_textual/Dedicatoria}
   ```

## Como compilar

O arquivo principal para compilação é:

```text
Monografia_config.tex
```

No Overleaf, basta abrir esse arquivo como documento principal e compilar.

Em uma instalação local do LaTeX, uma forma simples é usar:

```bash
latexmk -pdf Monografia_config.tex
```

O PDF gerado será `Monografia_config.pdf`.

## Inserindo novos capítulos

Para criar um novo capítulo:

1. Crie um novo arquivo `.tex` dentro da pasta `Capitulos/`.
2. Inicie o arquivo com `\chapter{Nome do Capítulo}`.
3. Inclua o arquivo em `Monografia_config.tex`, na área de elementos textuais.

Exemplo:

```tex
\input{Capitulos/Cap01-Introducao}
\input{Capitulos/Cap02-Referencial}
\input{Capitulos/Cap03-Metodologia}
\input{Capitulos/Cap04-Resultados}
\input{Capitulos/Cap05-Conclusoes}
\input{Capitulos/NovoCapitulo}
```

Evite renomear arquivos já chamados no arquivo principal sem atualizar também o respectivo comando `\input`.

## Observações importantes

- Não apague comandos LaTeX ou blocos de configuração sem entender sua função, pois eles controlam a formatação do documento.
- Leia os comentários presentes nos arquivos `.tex`; eles indicam quais partes podem ser editadas.
- Os capítulos incluem informações de escrita e exemplos de estrutura textual para orientar a produção da monografia.
- A ficha catalográfica e a folha de aprovação normalmente são inseridas apenas na versão final, após a defesa.
- Caso utilize o cronograma, verifique o nome do arquivo existente em `Capitulos/` e a chamada correspondente em `Monografia_config.tex`.

<p align="center">
  Feito com <span style="color:#0057B8;">&#10084;</span> por Prof. Me. Jemison Santos para uso nas disciplinas de estágio obrigatório.
</p>
