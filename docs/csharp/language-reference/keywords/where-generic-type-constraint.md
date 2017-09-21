---
title: "where (ограничение универсального типа) (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8e81640ee56ed672bb09242a070fdf167740874b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="where-generic-type-constraint-c-reference"></a>where (ограничение универсального типа) (справочник по C#)
В определении универсального типа предложение `where` позволяет задать ограничения для типов, которые можно использовать как аргументы для параметра типа, определенных в универсальном объявлении. Например, можно объявить универсальный класс `MyGenericClass` так, чтобы параметр типа `T` реализовывал интерфейс <xref:System.IComparable%601>:  
  
```csharp  
public class MyGenericClass<T> where T:IComparable { }  
```  
  
> [!NOTE]
>  Дополнительные сведения о предложении where в выражении запроса см. в разделе [Предложение where](../../../csharp/language-reference/keywords/where-clause.md).  
  
 Наряду с ограничениями интерфейса предложение `where` может включать ограничение базового класса, согласно которому тип должен иметь указанный класс как базовый (либо быть таким классом) — только в этом случае его можно будет использовать как аргумент типа для соответствующего универсального типа. Если такое ограничение используется, оно должно быть указано перед любыми другими ограничениями данного параметра типа.  
  
 [!code-cs[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]  
  
 Предложение `where` также может включать ограничение конструктора. С помощью оператора new можно создать экземпляр параметра типа, однако для этого параметр типа должен ограничиваться ограничением конструктора `new()`. [Ограничение new()](../../../csharp/language-reference/keywords/new-constraint.md) сообщает компилятору о том, что все предоставленные аргументы типа должны иметь доступный конструктор без параметров (или конструктор по умолчанию). Пример:  
  
 [!code-cs[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]  
  
 Ограничение `new()` отображается в предложении `where` последним.  
  
 Если параметров типа несколько, для каждого из них необходимо использовать по одному предложению `where`, например:  
  
 [!code-cs[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]  
  
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

