---
title: "void (справочник по C#) | Microsoft Docs"
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
  - "void_CSharpKeyword"
  - "void"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "void - ключевое слово [C#]"
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# void (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

При использовании в качестве типа возвращаемого значения для метода, `void` указывает, что метод не возвращает значение.  
  
 `void` не разрешается в списке параметров метода.  Не принимающий параметров и возвращающий значений метод объявляется следующим образом:  
  
```  
public void SampleMethod()  
{  
    // Body of the method.  
}  
  
```  
  
 Ключевое слово `void` также используется в небезопасном контексте для объявления указателя на неизвестный тип.  Для получения дополнительной информации см. [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).  
  
 Ключевое слово `void` является псевдонимом типа <xref:System.Void?displayProperty=fullName> платформы .NET Framework.  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md)   
 [Типы значений](../../../csharp/language-reference/keywords/value-types.md)   
 [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)