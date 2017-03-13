---
title: "object (справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "object_CSharpKeyword"
  - "object"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "object - ключевое слово [C#]"
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# object (справочник по C#)
Тип `object` представляет собой псевдоним для <xref:System.Object> в платформе .NET Framework.  В унифицированной системе типов C\# все типы, предопределенные и пользовательские, ссылочные типы и типы значений, наследуют непосредственно или косвенно от <xref:System.Object>.  Переменным типа `object` можно назначать значения любых типов.  Когда переменная типа значения преобразуется в объект, говорят, что она *упаковывается*.  Когда переменная типа object преобразуется в тип значения, говорят, что она *распаковывается*.  Дополнительные сведения см. в разделе [Упаковка–преобразование и распаковка–преобразование](../../../csharp/programming-guide/types/boxing-and-unboxing.md).  
  
## Пример  
 В следующем примере показывается, как переменные типа `object` могут принимать значения любого типа данных, а также как переменные типа `object` могут использовать методы для <xref:System.Object> из платформы .NET Framework.  
  
 [!code-cs[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md)   
 [Типы значений](../../../csharp/language-reference/keywords/value-types.md)