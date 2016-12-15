---
title: "&lt;summary&gt; (Visual Basic) | Microsoft Docs"
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
  - "<summary> - XML-тег"
  - "summary - XML-тег"
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;summary&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Задает сводку элемента.  
  
## Синтаксис  
  
```  
<summary>description</summary>  
```  
  
#### Параметры  
 `description`  
 Сводка объекта.  
  
## Заметки  
 Используйте тег `<summary>` для описания типа или члена типа.  Используйте [\<remarks\>](../../../visual-basic/language-reference/xmldoc/remarks.md), чтобы добавить вспомогательную информацию в описание типа.  
  
 Текст тега `<summary>` единственный источник информации о типе в технологии IntelliSense, а также отображается в обозревателе объектов.  Дополнительные сведения об обозревателе объектов см. в разделе [Просмотр структуры кода](/visual-studio/ide/viewing-the-structure-of-code).  
  
 Чтобы выделить документирующие комментарии в отдельный файл, необходимо использовать при компиляции параметр [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## Пример  
 В этом примере используется тег `<summary>` для описания метода `ResetCounter` и свойства `Counter`.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]  
  
## См. также  
 [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)