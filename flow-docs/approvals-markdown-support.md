---
title: Usar redução para formatar Microsoft Flow aprovações | Microsoft Docs
description: Aprenda a usar a redução para formatar Microsoft Flow solicitações de aprovação.
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
ms.openlocfilehash: b82ac7c53c8c018b5e61011e4c1d8b9cdabe9747
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545310"
---
# <a name="use-markdown-in-microsoft-flow-approval-requests"></a>Use a redução em Microsoft Flow solicitações de aprovação
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Este artigo ensina como usar a sintaxe de [redução](https://en.wikipedia.org/wiki/Markdown) para adicionar formatação e tabelas ricas às suas solicitações de aprovação.

## <a name="headers"></a>Conector

Estruture seus comentários usando cabeçalhos. Os cabeçalhos segmentam comentários mais longos, tornando-os mais fáceis de ler.

Inicie uma linha com um caractere de hash `#` para definir um título. Organize seus comentários com subtítulos iniciando uma linha com caracteres de hash adicionais, por exemplo `####`. Há suporte para até seis níveis de títulos.

**Exemplo**

```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**Disso**

![Fluxo de exportação](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>Parágrafos e quebras de linha

Facilite a leitura do texto dividindo-o com parágrafos ou quebras de linha. Insira dois espaços antes da quebra de linha para iniciar um novo parágrafo ou insira duas quebras de linha consecutivamente para iniciar um novo parágrafo.   
   
**Exemplo**

Adicione linhas entre o texto com a tecla Enter.
Isso deixa o texto melhor e facilita a leitura.

**Resultado:**    
Adicione linhas entre o texto com a tecla Enter.      
Isso deixa o texto melhor e facilita a leitura.


**Exemplo 2**

Adicione dois espaços antes do final da linha. (espaço, espaço)     
Isso adiciona espaço entre parágrafos.

**Disso**  
Adicione dois espaços antes do final da linha.   

Isso adiciona espaço entre parágrafos.
  

## <a name="lists"></a>Lista

Organizar itens relacionados com listas. Você pode adicionar listas ordenadas com números ou listas não ordenadas com apenas marcadores.

As listas ordenadas começam com um número seguido de um período para cada item de lista. As listas não ordenadas começam com um `*`. Iniciar cada item de lista em uma nova linha. Em um arquivo ou widget de redução, insira dois espaços antes da quebra de linha para iniciar um novo parágrafo ou insira duas quebras de linha consecutivamente para iniciar um novo parágrafo.   

### <a name="ordered-or-numbered-lists"></a>Listas ordenadas ou numeradas

**Exemplo**

```Markdown
0. First item.
0. Second item.
0. Third item.
```

**Disso**

1. Primeiro item.
2. Segundo item.
3. Terceiro item.

### <a name="bullet-lists"></a>Listas de marcadores

**Exemplo**

<pre>

- Item 1
- Item 2
- Item 3

</pre>

**Disso**

- Item 1
- Item 2
- Item 3

### <a name="nested-lists"></a>Listas aninhadas

**Exemplo**
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

**Disso**  

1. Primeiro item.

    - Item 1
    - Item 2
    - Item 3
2. Segundo item.
    - Item aninhado 1
    - Item aninhado 2
    - Item aninhado 3


## <a name="links"></a>Vincule

As URLs HTTP e HTTPS são formatadas automaticamente como links. 

Você pode definir hiperlinks de texto para sua URL usando a sintaxe de link de redução padrão:

```Markdown
[Link Text](Link URL)
```

**Exemplo**
<pre>
&#91;Microsoft Flow](https://flow.microsoft.com)
</pre>

**Disso**

[Microsoft Flow](https://flow.microsoft.com)

### <a name="anchor-links"></a>Links de âncora

As IDs de âncora são atribuídas a todos os títulos quando renderizadas como HTML. A ID é o texto do título, com os espaços substituídos por traços (-) e todas as letras minúsculas.

**Exemplo**

<pre>
###Link to a heading in the page
</pre>

<br/>

**Disso**

A sintaxe de um link de âncora para uma seção...

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre> 
<br/>
A ID é todas as letras minúsculas e o link diferencia maiúsculas de minúsculas, portanto, certifique-se de usar letras minúsculas, mesmo que o próprio título use maiúsculas e minúsculas.


## <a name="tables"></a>Tabelas

Organize dados estruturados com tabelas. 

- Coloque cada linha da tabela em sua própria linha 
- Separar células de tabela usando o caractere de barra `|` 
- As duas primeiras linhas de uma tabela definem os cabeçalhos de coluna e o alinhamento dos elementos na tabela
- Use dois-pontos (`:`) ao dividir o cabeçalho e o corpo de tabelas para especificar o alinhamento da coluna (esquerda, centro, direita) 
- Para iniciar uma nova linha, use a marca de quebra de HTML (`<br/>`) (funciona em um wiki, mas não em outro lugar)  
- Certifique-se de finalizar cada linha com uma CR ou LF. 

**Exemplo**

```
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
```




**Disso**  

| Título 1 | Título 2 | Título 3 |  
|-----------|:---------:|-----------:|  
| Célula a1 | Célula A2 | Célula a3 |  
| Célula B1 | Célula B2 | Célula B3<br/>segunda linha de texto |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>Ênfase (negrito, itálico, tachado)  

Você pode enfatizar o texto aplicando negrito, itálico ou tachado a caracteres: 
- Para aplicar itálico: Coloque o texto com um asterisco `*` ou sublinhado `_`   
- Para aplicar negrito: Coloque o texto com asteriscos duplos `**`.    
- Para aplicar tachado: Coloque o texto com caracteres de til duplo `~~`.   

Combine esses elementos para aplicar várias ênfase ao texto.    

**Exemplo**

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

<br/>

**Disso**

Use _ênfase_ em comentários para expressar opiniões **fortes** e destacar as <s>correções</s>   
**_Texto em negrito e em itálico_**    
**~~Texto em negrito e tachado~~**  


## <a name="special-characters"></a>Caracteres especiais

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">Sintaxe</th>
<th width="350px">Exemplo/observações</th>
</tr>



<tr>
<td>
<p>Para inserir um dos seguintes caracteres, coloque um prefixo com uma barra invertida:</p>

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
