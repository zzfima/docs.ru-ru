---
title: "Оператор [] (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '[]_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 20
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
ms.openlocfilehash: b49d41af0dd4dc34b1b74c62ce8779aa31d69f77
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="-operator-c-reference"></a>Оператор [] (Справочник по C#)
Квадратные скобки (`[]`) используются для массивов, индексаторов и атрибутов. Кроме того, их можно использовать с указателями.  
  
## <a name="remarks"></a>Примечания  
 Тип массива указывается перед оператором `[]`:  
  
 [!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]  
  
 Для доступа к элементу массива его индекс необходимо заключить в скобки:  
  
 [!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]  
  
 Если индекс массива выходит за границы диапазона, создается исключение.  
  
 Перегрузка оператора индексирования массива невозможна. Однако типы могут определять индексаторы и свойства, принимающие один или несколько параметров. Параметры индексатора заключаются в квадратные скобки, как и индексы массива, но, в отличие от индексов массива, которые должны быть целочисленными, эти параметры могут быть любого типа.  
  
 Например, в платформе .NET Framework определен тип `Hashtable`, связывающий ключи и значения произвольного типа.  
  
 [!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]  
  
 Кроме того, квадратные скобки используются для определения [атрибутов](../../../csharp/programming-guide/concepts/attributes/index.md):  
  
 [!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]  
  
 Квадратные скобки можно использовать для создания индекса на основе указателя:  
  
 [!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]  
  
 Проверка границ не выполняется.  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Индексаторы](../../../csharp/programming-guide/indexers/index.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)

