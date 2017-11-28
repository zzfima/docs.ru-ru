---
title: "where (ограничение универсального типа) (справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
helpviewer_keywords: where (generic type constraint) [C#]
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f2b7b159689aa771d3f9d59e3b1dd340c85b1d79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="where-generic-type-constraint-c-reference"></a>where (ограничение универсального типа) (справочник по C#)
В определении универсального типа предложение `where` позволяет задать ограничения для типов, которые можно использовать как аргументы для параметра типа, определенных в универсальном объявлении. Например, можно объявить универсальный класс `MyGenericClass` так, чтобы параметр типа `T` реализовывал интерфейс <xref:System.IComparable%601>:  
  
```csharp  
public class MyGenericClass<T> where T:IComparable { }  
```  
  
> [!NOTE]
>  Дополнительные сведения о предложении where в выражении запроса см. в разделе [Предложение where](../../../csharp/language-reference/keywords/where-clause.md).  
  
 Наряду с ограничениями интерфейса предложение `where` может включать ограничение базового класса, согласно которому тип должен иметь указанный класс как базовый (либо быть таким классом) — только в этом случае его можно будет использовать как аргумент типа для соответствующего универсального типа. Если такое ограничение используется, оно должно быть указано перед любыми другими ограничениями данного параметра типа.  
  
 [!code-csharp[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]  
  
 Предложение `where` также может включать ограничение конструктора. С помощью оператора new можно создать экземпляр параметра типа, однако для этого параметр типа должен ограничиваться ограничением конструктора `new()`. [Ограничение new()](../../../csharp/language-reference/keywords/new-constraint.md) сообщает компилятору о том, что все предоставленные аргументы типа должны иметь доступный конструктор без параметров (или конструктор по умолчанию). Пример:  
  
 [!code-csharp[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]  
  
 Ограничение `new()` отображается в предложении `where` последним.  
  
 Если параметров типа несколько, для каждого из них необходимо использовать по одному предложению `where`, например:  
  
 [!code-csharp[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]  
  
 Кроме того, ограничения можно присоединять к параметрам типа универсальных методов следующим образом:  
  
```csharp  
public bool MyMethod<T>(T t) where T : IMyInterface { }  
```  
  
 Обратите внимание на то, что ограничения параметров типа для делегатов имеют такой же синтаксис, как и методы:  
  
```csharp  
delegate T MyDelegate<T>() where T : new()  
```  
  
 Дополнительные сведения об универсальных делегатах см. в разделе [Универсальные делегаты](../../../csharp/programming-guide/generics/generic-delegates.md).  
  
 Дополнительные сведения о синтаксисе и применении ограничений см. в разделе [Ограничения параметров типа](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [Ограничение new](../../../csharp/language-reference/keywords/new-constraint.md)  
 [Ограничения параметров типа](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)
