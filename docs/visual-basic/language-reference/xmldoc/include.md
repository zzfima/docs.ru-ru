---
title: "&lt;include&gt;(Visual Basic) | Microsoft Docs"
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
  - "<include> - XML- тэг"
  - "include - XML- тэг"
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;include&gt;(Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ссылается на другой файл, описывающий типы и элементы в исходном коде.  
  
## Синтаксис  
  
```  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### Параметры  
 `filename`  
 Обязательный.  Имя файла, содержащего документацию.  Имя файла может быть дополнено путем.  Заключите `filename` в двойные кавычки \(" "\).  
  
 `tagpath`  
 Обязательный.  Путь тегов в `filename`, который приводит к тегу `name`.  Заключите путь в двойные кавычки \(" "\).  
  
 `name`  
 Обязательный.  Спецификатор имени в теге, который предшествует комментариям.  `Name` будет иметь `id`.  
  
 `id`  
 Обязательный.  Идентификатор для тега, который предшествует комментариям.  Заключите идентификатор в одинарные кавычки \(' '\).  
  
## Заметки  
 Используйте тег `<include>` для ссылок на комментарии в другом файле, описывающем типы и элементы в вашем исходном коде.  Это является альтернативой помещению комментариев документации непосредственно в файле исходного кода.  
  
 Тег `<include>` использует W3C XML Path Language \(XPath\) Version 1.0 Recommendation.  Дополнительные сведения о способах настройки использования `<include>` доступны на http:\/\/www.w3.org\/TR\/xpath.  
  
## Пример  
 Этот пример использует тег `<include>` для импорта комментариев документации элемента из файла с именем `commentFile.xml`.  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 Формат `commentFile.xml` представлен ниже.  
  
```  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## См. также  
 [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)