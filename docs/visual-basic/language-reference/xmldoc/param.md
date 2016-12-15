---
title: "&lt;param&gt; (Visual Basic) | Microsoft Docs"
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
  - "<param> - XML-тег"
  - "param - XML-тег"
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;param&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Определяет имя параметра и описание.  
  
## Синтаксис  
  
```  
<param name="name">description</param>  
```  
  
#### Параметры  
 `name`  
 Имя параметра метода.  Заключите имя в двойные кавычки \(" "\).  
  
 `description`  
 Описание для параметра.  
  
## Заметки  
 Тег `<param>` должен использоваться в комментариях объявления метода для описания его параметров.  
  
 Текст тега `<param>` будет отображаться в следующих расположений:  
  
-   Сведения о параметрах IntelliSense.  Дополнительные сведения см. в разделе [Использование технологии IntelliSense](/visual-studio/ide/using-intellisense).  
  
-   Обозреватель объектов.  Дополнительные сведения см. в разделе [Просмотр структуры кода](/visual-studio/ide/viewing-the-structure-of-code).  
  
 Чтобы выделить документирующие комментарии в отдельный файл, необходимо использовать при компиляции параметр [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## Пример  
 В этом примере тег `<param>` используется для описания параметра `id`.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## См. также  
 [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)