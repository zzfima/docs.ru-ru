---
title: "&lt;значение&gt; (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "<value> - XML-тег"
  - "value - XML-тег"
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# &lt;значение&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Указывает описание свойства.  
  
## Синтаксис  
  
```  
<value>property-description</value>  
```  
  
#### Параметры  
 `property-description`  
 Описание свойства.  
  
## Заметки  
 Используйте тег `<value>` для описания свойства.  Обратите внимание, что при добавлении свойства с помощью мастера создания кода в среде разработки Visual Studio для нового свойства будет добавлен тег [\<summary\>](../../../visual-basic/language-reference/xmldoc/summary.md).  Следует затем вручную добавить тег `<value>` для описания значения, которое представляет свойство.  
  
 Чтобы выделить документирующие комментарии в отдельный файл, необходимо использовать при компиляции параметр [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## Пример  
 В данном примере используется тег `<value>` для описания того, какое значение содержится в свойстве `Counter`.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## См. также  
 [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)