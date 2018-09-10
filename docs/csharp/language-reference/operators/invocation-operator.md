---
title: Оператор () (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 29097dc4aa0bf712b9b2beda4450820a66472ba7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/09/2018
ms.locfileid: "44179675"
---
# <a name="-operator-c-reference"></a>Оператор () (Справочник по C#)
Помимо использования для указания порядка операций в выражении круглые скобки используются для выполнения следующих задач:  
  
1.  Задание операций приведения или преобразования типов.  
  
     [!code-csharp[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  Вызов методов или делегатов.  
  
     [!code-csharp[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## <a name="remarks"></a>Примечания  
 Приведение явно вызывает оператор преобразования из одного типа в другой. Если такой оператор преобразования не определен, приведение завершается сбоем. Сведения об определении оператора преобразования см. в разделах [explicit](../../../csharp/language-reference/keywords/explicit.md) и [implicit](../../../csharp/language-reference/keywords/implicit.md).  
  
 Оператор `()` перегрузить нельзя.  
  
 Дополнительные сведения см. в разделе [Приведение и преобразование типов](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
 Дополнительные сведения о вызове методов см. в разделе [Методы](../../../csharp/programming-guide/classes-and-structs/methods.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
