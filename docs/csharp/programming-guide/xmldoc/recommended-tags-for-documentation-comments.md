---
title: "Рекомендуемые теги для комментариев документации (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "XML [C#], теги"
  - "документация XML [C#], теги"
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Рекомендуемые теги для комментариев документации (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Компилятор C\# обрабатывает комментарии документации в коде и форматирует их как XML\-код в файле, имя которого указано в параметре командной строки **\/doc**.  Для создания конечная документации на основе компилятором созданном файле можно создать пользовательский инструмент или использовать средства, например. [Sandcastle](http://shfb.codeplex.com/)  
  
 Теги обрабатываются в конструкциях кода, таких как типы и члены типов.  
  
> [!NOTE]
>  Комментарии документации не могут быть применены к пространству имен.  
  
 Компилятор обрабатывает любой тег, который является допустимым тегом XML.  Следующие теги предоставляют часто используемые возможности в пользовательской документации.  
  
## Теги  
  
||||  
|-|-|-|  
|[\<c\>](../../../csharp/programming-guide/xmldoc/code-inline.md)|[\<para\>](../../../csharp/programming-guide/xmldoc/para.md)|[\<see\>](../../../csharp/programming-guide/xmldoc/see.md)\*|  
|[\<code\>](../../../csharp/programming-guide/xmldoc/code.md)|[\<param\>](../../../csharp/programming-guide/xmldoc/param.md)\*|[\<seealso\>](../../../csharp/programming-guide/xmldoc/seealso.md)\*|  
|[\<example\>](../../../csharp/programming-guide/xmldoc/example.md)|[\<paramref\>](../../../csharp/programming-guide/xmldoc/paramref.md)|[\<summary\>](../../../csharp/programming-guide/xmldoc/summary.md)|  
|[\<exception\>](../../../csharp/programming-guide/xmldoc/exception.md)\*|[\<permission\>](../../../csharp/programming-guide/xmldoc/permission.md)\*|[\<typeparam\>](../../../csharp/programming-guide/xmldoc/typeparam.md)\*|  
|[\<include\>](../../../csharp/programming-guide/xmldoc/include.md)\*|[\<remarks\>](../../../csharp/programming-guide/xmldoc/remarks.md)|[\<typeparamref\>](../../../csharp/programming-guide/xmldoc/typeparamref.md)|  
|[\<list\>](../../../csharp/programming-guide/xmldoc/list.md)|[\<returns\>](../../../csharp/programming-guide/xmldoc/returns.md)|[\<value\>](../../../csharp/programming-guide/xmldoc/value.md)|  
  
 \(\* обозначает проверку синтаксиса компилятором.\)  
  
 Чтобы вставить угловые скобки в текст комментария документации, используйте `<` и `>`, как показано в следующем примере.  
  
```xml  
/// <summary cref="C < T >">  
/// </summary>  
```  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [\/doc \(Process Documentation Comments\)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [Комментарии к XML\-документации](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)