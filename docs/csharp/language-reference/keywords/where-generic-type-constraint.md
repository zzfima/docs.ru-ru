---
title: "where (ограничение универсального типа) (справочник по C#) | Microsoft Docs"
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
  - "whereconstraint"
  - "whereconstraint_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "where (ограничение универсального типа) [C#]"
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# where (ограничение универсального типа) (справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Предложение `where` используется в определении универсального типа для указания ограничений типов, которые могут использоваться в качестве аргументов параметра типа, определенного в универсальном объявлении.  Например, можно объявить универсальный класс `MyGenericClass`, чтобы параметр типа `T` реализовывал интерфейс <xref:System.IComparable%601>.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
> [!NOTE]
>  Дополнительные сведения о применении предложения "where" в выражении запроса см. в разделе [Предложение where](../../../csharp/language-reference/keywords/where-clause.md).  
  
 Кроме ограничений интерфейса, предложение `where` может включать ограничение базового класса, указывающее, что тип должен обладать указанным классом в качестве базового \(или являться этим классом\), чтобы его можно было использовать как аргумент типа для этого универсального типа.  Если такое ограничение используется, оно должно располагаться перед любыми другими ограничениями данного параметра типа.  
  
 [!code-cs[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]  
  
 Предложение `where` также может включать ограничение конструктора.  Можно создать экземпляр параметра типа с помощью нового оператора, однако для этого оператор типа должен быть ограничен ограничением конструктора `new()`.  Ограничение [new\(\)](../../../csharp/language-reference/keywords/new-constraint.md) указывает компилятору, что у любого типа предоставленных аргументов должен быть доступный конструктор без параметров или по умолчанию.  Примеры.  
  
 [!code-cs[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]  
  
 Ограничение `new()` располагается последним в предложении `where`.  
  
 При работе с несколькими параметрами типа используйте по одному предложению `where` для каждого параметра типа, например:  
  
 [!code-cs[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]  
  
 Также можно прикреплять ограничения к параметрам типа универсальных методов, например:  
  
```  
public bool MyMethod<T>(T t) where T : IMyInterface { }  
```  
  
 Обратите внимание, что синтаксис, описывающий ограничения параметра типа для делегатов, такой же, как и для методов:  
  
```  
delegate T MyDelegate<T>() where T : new()  
```  
  
 Сведения об универсальных методах\-делегатах см. в разделе [Универсальные методы\-делегаты](../../../csharp/programming-guide/generics/generic-delegates.md).  
  
 Дополнительные сведения о синтаксисе и применении ограничений см. в разделе [Ограничения параметров типа](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Ограничение new](../../../csharp/language-reference/keywords/new-constraint.md)   
 [Ограничения параметров типа](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)