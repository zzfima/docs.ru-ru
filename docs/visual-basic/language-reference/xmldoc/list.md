---
title: "&lt;list&gt; (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "<description> - XML-тег"
  - "<item> - XML-тег"
  - "<list> - XML-тег"
  - "<listheader> - XML-тег"
  - "<term> - XML-тег"
  - "description - XML-тег"
  - "item - XML-тег"
  - "list - XML-тег"
  - "listheader - XML-тег"
  - "term - XML-тег"
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;list&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Определяет список или таблицу.  
  
## Синтаксис  
  
```  
<list type="type">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
#### Параметры  
 `type`  
 Тип списка.  Должен иметь значение "bullet" для маркированного списка, "number" для нумерованного списка или "table" для таблицы с двумя столбцами.  
  
 `term`  
 Используется только в том случае, когда типом `type` является "table". Термин для определения, который определен в теге описания.  
  
 `description`  
 Если тип `type` — "bullet" или "number", то `description` — это элемент списка. Если `type` — "table", то `description` — это определение `term`.  
  
## Заметки  
 Блок `<listheader>` задает заголовок таблицы или списка определений.  При определении таблицы достаточно указать запись для `term` в заголовке.  
  
 Каждый элемент в списке указывается в блоке `<item>`.  При создании списка определений необходимо указать и `term`, и `description`.  Однако для таблицы, маркированного или нумерованного списка достаточно указать `description`.  
  
 Список или таблица может иметь столько блоков `<item>`, сколько необходимо.  
  
 Чтобы выделить документирующие комментарии в отдельный файл, необходимо использовать при компиляции параметр [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## Пример  
 В этом примере тег `<list>` используется для создания маркированного списка в разделе примечаний.  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## См. также  
 [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)