---
title: "&lt;see&gt; (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<see>"
  - "see"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<see> - XML-тег C#"
  - "cref [C#], <see> - тег"
  - "перекрестные ссылки [C#]"
  - "see - XML-тег C#"
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &lt;see&gt; (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

## Синтаксис  
  
```  
<see cref="member"/>  
```  
  
#### Параметры  
 cref \= " `member`"  
 Ссылка на член или поле, которое может вызываться из текущей среды компиляции.  Компилятор проверяет, существует ли данный элемент кода и передает ли он `member` имени элемента в выходных XML\-данных.Поместите *член* в двойные кавычки \(" "\).  
  
## Заметки  
 \<Тег увидеть\> позволяет указать ссылку из текста.  Используйте [\<seealso\>](../../../csharp/programming-guide/xmldoc/seealso.md), чтобы указать, что текст должен быть помещен в разделе " см. также ".  Используйте [атрибут cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md), чтобы создать гиперссылки на страницы документации для элементов кода.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  
  
 В следующем примере показан общий тег\> \<" см. в разделе.  
  
 [!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/see_1.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)