---
title: "delegate (Справочник по C#) | Microsoft Docs"
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
  - "delegate_CSharpKeyword"
  - "delegate"
  - "CS0123"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "delegate - ключевое слово [C#]"
  - "указатели функций [C#]"
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# delegate (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Объявление типа делегата аналогично сигнатуре метода.  Оно имеет возвращаемое значение и некоторое число параметров какого\-либо типа:  
  
```  
public delegate void TestDelegate(string message);  
public delegate int TestDelegate(MyType m, long num);  
```  
  
 Ключевое слово `delegate` используется для объявления ссылочного типа, который может быть использован для инкапсуляции именованного или анонимного метода.  Делегаты аналогичны используемым в языке C\+\+ указателям на функции, но являются типобезопасными и безопасными.  Сведения о применении делегатов см. в разделах [Делегаты](../../../csharp/programming-guide/delegates/index.md) и [Универсальные методы\-делегаты](../../../csharp/programming-guide/generics/generic-delegates.md).  
  
## Заметки  
 Делегаты являются основой [событий](../../../csharp/programming-guide/events/index.md).  
  
 Экземпляры делегата могут создаваться путем его связывания с именованным или анонимным методом.  Дополнительные сведения см. в разделах [Именованные методы](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) и [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).  
  
 Делегат должен быть создан при помощи метода или лямбда\-выражения, имеющего совместимые возвращаемый тип и входные параметры.  Дополнительные сведения о допустимой степени вариации сигнатур методов см. в разделе [Вариативность в делегатах](../Topic/Variance%20in%20Delegates%20\(C%23%20and%20Visual%20Basic\).md).  Для использования с анонимными методами делегат и код, который должен быть связан с ним, должны быть объявлены вместе.  В этом разделе рассматриваются оба способа создания экземпляров делегатов.  
  
## Пример  
 [!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md)   
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)   
 [События](../../../csharp/programming-guide/events/index.md)   
 [Делегаты с именованными методами и делегаты с анонимными методами](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)   
 [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)