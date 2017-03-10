---
title: "#else (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#else"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#else - директива [C#]"
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# #else (Справочник по C#)
`#else` позволяет создать сложную условную директиву, так чтобы при отсутствии выражений в предшествующих директивах[\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) или \(необязательно\) [\#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) со значением `true`, компилятор анализировал весь код между `#else` и последующей директивой `#endif`.  
  
## Заметки  
 [\#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) должна быть следующей директивой препроцессора после `#else`.  Пример использования `#else` см. в разделе [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Директивы препроцессора C\#](../../../csharp/language-reference/preprocessor-directives/index.md)