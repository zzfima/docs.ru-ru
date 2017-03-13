---
title: "&lt;разрешение&gt; (Visual Basic) | Microsoft Docs"
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
  - "<permission> - XML-тег"
  - "permission - XML-тег"
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &lt;разрешение&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Задает требуемое разрешение для члена.  
  
## Синтаксис  
  
```  
<permission cref="member">description</permission>  
```  
  
#### Параметры  
 `member`  
 Ссылка на член или поле, которое может вызываться из текущей среды компиляции.  Компилятор проверяет, существует ли элемент кода и приводит `member` к каноническому имени элемента в выходных XML\-данных.  Заключите `member` в кавычки \(" "\).  
  
 `description`  
 Описание доступа к члену.  
  
## Заметки  
 Используйте тег `<permission>`, чтобы документ получил доступ к члену.  Используйте класс <xref:System.Security.PermissionSet>, чтобы указать доступ к члену.  
  
 Чтобы выделить документирующие комментарии в отдельный файл, необходимо использовать при компиляции параметр [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## Пример  
 В данном примере используется тег `<permission>`, указывающий, что требуется <xref:System.Security.Permissions.FileIOPermission> для метода `ReadFile`.  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## См. также  
 [XML\-теги для комментариев](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)