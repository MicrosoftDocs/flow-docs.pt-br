---
title: Usar markdown para formatar aprovações do Microsoft Flow | Microsoft Docs
description: Aprenda a usar markdown para formatar as solicitações de aprovação do Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: gcorvera
manager: kfile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/23/2018
ms.author: gcorvera
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 7611ccb8bba9f2647402df46753de284016d7cd4
ms.sourcegitcommit: 014f64bcc4aed27794d5c7efc2eca241d271518e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58656121"
---
# <a name="use-markdown-in-microsoft-flow-approval-requests"></a>Usar markdown em solicitações de aprovação do Microsoft Flow

Este artigo ensina a usar a sintaxe do [Markdown](https://en.wikipedia.org/wiki/Markdown) para adicionar formatação detalhada e tabelas às suas solicitações de aprovação.

## <a name="headers"></a>Cabeçalhos

Estruture seus comentários usando cabeçalhos. Os cabeçalhos segmentam comentários mais longos, tornando-os mais fáceis de ler.

Inicie uma linha com um caractere de hash `#` para definir um cabeçalho. Organize seus comentários com subtítulos iniciando uma linha com caracteres de hash adicionais, por exemplo `####`. Há suporte para até seis níveis de cabeçalhos.

**Exemplo:**

```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**Resultado:**

![Exportar fluxo](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>Parágrafos e quebras de linha

Facilite a leitura do texto dividindo-o com parágrafos ou quebras de linha. Insira dois espaços antes da quebra de linha para começar um novo parágrafo, ou insira duas quebras de linha consecutivas para iniciar um novo parágrafo.   
   
**Exemplo**

Add lines between your text with the Enter key.
This spaces your text better and makes it easier to read.

**Resultado:**   
Add lines between your text with the Enter key.      
This spaces your text better and makes it easier to read.


**Exemplo 2**

Add two spaces prior to the end of the line.(space, space)     
This adds space in between paragraphs.

**Resultado:**  
Add two spaces prior to the end of the line.   

This adds space in between paragraphs.
  

## <a name="lists"></a>Listas

Organize itens relacionados com listas. Adicione listas ordenadas com números, ou listas não ordenadas com marcadores.

As listas ordenada começam com um número seguido por um ponto para cada item da lista. As listas não ordenadas começam com um `*`. Comece cada item de lista em uma nova linha. Em um arquivo de Markdown ou widget, insira dois espaços antes da quebra de linha para começar um novo parágrafo, ou insira duas quebras de linha consecutivas para iniciar um novo parágrafo.   

### <a name="ordered-or-numbered-lists"></a>Lista numerada ou ordenada

**Exemplo:**

```Markdown
0. First item.
0. Second item.
0. Third item.
```

**Resultado:**

1. First item.
2. Second item.
3. Third item.

### <a name="bullet-lists"></a>Listas com marcador

**Exemplo:**

<pre>

- Item 1
- Item 2
- Item 3

</pre>

**Resultado:**

- Item 1
- Item 2
- Item 3

### <a name="nested-lists"></a>Listas aninhadas

**Exemplo:**
<pre>

1. First item.
   - Item 1
   - Item 2
   - Item 3
1. Second item.
   - Nested item 1
   - Nested item 2
   - Nested item 3

</pre>

**Resultado:**  

1. First item.

    - Item 1
    - Item 2
    - Item 3
2. Second item.
    - Nested item 1
    - Nested item 2
    - Nested item 3


## <a name="links"></a>Links

As URLs HTTP e HTTPS são formatadas automaticamente como links. 

Você pode definir hiperlinks de texto para a sua URL usando a sintaxe de link de markdown padrão:

```Markdown
[Link Text](Link URL)
```

**Exemplo:**
<pre>
&#91;Microsoft Flow](https://flow.microsoft.com)
</pre>

**Resultado:**

[Microsoft Flow](https://flow.microsoft.com)

### <a name="anchor-links"></a>Links de âncora

As IDs de âncora são atribuídas a todos os cabeçalhos, quando renderizados como HTML. A ID é o texto do cabeçalho, com os espaços substituído por traços (-) e com todas as letras minúsculas.

**Exemplo:**

<pre>
###Link to a heading in the page
</pre>

<br/>

**Resultado:**

A sintaxe para um link de âncora para uma seção...

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre> 
<br/>
A ID fica toda em letra minúscula, e o link diferencia maiúsculas de minúsculas, portanto, use letras minúsculas, mesmo que o título use letras maiúsculas.


## <a name="tables"></a>Tabelas

Organize dados estruturados com tabelas. 

- Coloque cada linha da tabela em sua própria linha 
- Separe as células da tabela usando o caractere de pipe `|` 
- As duas primeiras linhas de uma tabela definem os cabeçalhos da coluna e o alinhamento dos elementos na tabela
- Use dois-pontos (`:`) ao dividir o cabeçalho e o corpo das tabelas a fim de especificar o alinhamento da coluna (à esquerda, centro, à direita) 
- Para iniciar uma nova linha, use a marca de quebra HTML (`<br/>`) (funciona dentro de um Wiki, mas não em outro lugar)  
- Finalize cada linha com um CR ou LF. 

**Exemplo:**

```
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
```




**Resultado:**  

| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:---------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>Ênfase (negrito, itálico, tachado)  

Você pode enfatizar o texto aplicando negrito, itálico ou tachado aos caracteres: 
- Para aplicar itálico: envolva o texto com um asterisco `*` ou sublinhado `_`   
- Para aplicar negrito: envolva o texto entre dois asteriscos `**`.    
- Para aplicar tachado: envolva o texto com caracteres de duplo til `~~`.   

Combine esses elementos para aplicar várias ênfases ao texto.    

**Exemplo:**

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

<br/>

**Resultado:**

Use _emphasis_ in comments to express **strong** opinions and point out <s>corrections</s>   
**_Bold, italicized text_**   
**~~Bold, strike-through text~~**  


## <a name="special-characters"></a>Caracteres especiais

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">Sintaxe</th>
<th width="350px">Exemplo/observações</th>
</tr>



<tr>
<td>
<p>Para inserir um dos seguintes caracteres, use uma barra invertida como prefixo:</p>

<p style="margin-bottom:2px;">```\   backslash ``` </p>
<p style="margin-bottom:2px;"><code>\`</code>   `backtick`</p>
<p style="margin-bottom:2px;">```_   underscore  ```</p>
<p style="margin-bottom:2px;">```{}  curly braces  ``` </p>
<p style="margin-bottom:2px;">```[]  square brackets ```</p>
<p style="margin-bottom:2px;">```()  parentheses  ```</p>
<p style="margin-bottom:2px;">```#   hash mark  ``` </p>
<p style="margin-bottom:2px;">```+   plus sign  ```</p>
<p style="margin-bottom:2px;">```-   minus sign (hyphen) ```</p>
<p style="margin-bottom:2px;">```.   dot  ``` </p>
<p style="margin-bottom:2px;">```!   exclamation mark ```</p>


</td>
<td>Alguns exemplos de inserção de caracteres especiais
<p>Insira ```\\``` para obter \\ </p>
<p>Insira ```\_``` para obter _ </p>
<p>Insira ```\#``` para obter \# </p>
<p>Insira ```\(``` para obter \( </p>
<p>Insira ```\.``` para obter \. </p>
<p>Insira ```\!``` para obter \! </p>
</td>
</tr>

</tbody>
</table>
