---
title: "Рекомендуется использовать XML-теги для комментариев документации (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlDocComment"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "комментарии, рекомендуемые XML-теги"
  - "теги, XML"
  - "XML-комментарии, рекомендуемые теги [Visual Basic]"
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Рекомендуется использовать XML-теги для комментариев документации (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Компилятор [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] может обрабатывать документацию комментариев в коде в XML\-файл.  Можно использовать дополнительные средства для обработки XML\-файла в документации.  
  
 Комментарии XML разрешены в конструкциях кода, таких как типы и члены типов.  Для разделяемых типов только одна часть типа может содержать комментарии XML, однако нет никаких ограничений на комментирование его членов.  
  
> [!NOTE]
>  Комментарии документации не могут быть применены к пространству имен.  Причина в том, что одно пространство имен может охватывать несколько сборок, и не все сборки должны быть загружена в то же время.  
  
 Компилятор обрабатывает любой тег, который является допустимым тегом XML.  Следующие теги предоставляют часто используемые возможности в пользовательской документации.  
  
||||  
|-|-|-|  
|[\<c\>](../../../visual-basic/language-reference/xmldoc/c.md)|[\<code\>](../../../visual-basic/language-reference/xmldoc/code.md)|[\<example\>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<exception\>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<include\>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list\>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para\>](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param\>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref\>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<permission\>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<remarks\>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<returns\>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<see\>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|[\<seealso\>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<summary\>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|[\<typeparam\>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<value\>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 \(<sup>1</sup> Синтаксис проверяется компилятором.\)  
  
> [!NOTE]
>  Чтобы вставить угловые скобки в текст комментария документации, используйте `<` и `>`.  Например, строка `"<text in angle brackets>"` будет выглядеть как `<text in angle` `brackets>`.  
  
## См. также  
 [Документирование кода с помощью XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)   
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)   
 [Практическое руководство. Создание XML\-документации](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)