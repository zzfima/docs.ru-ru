---
title: Справочник по C#. Оператор *=
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: f8604cdadeda14a5761bc923bd966186fd258a6d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245354"
---
# <a name="-operator-c-reference"></a>Оператор *= (Справочник по C#)
Бинарный оператор присваивания умножения.  
  
## <a name="remarks"></a>Примечания  
 Выражение, использующее оператор присваивания `*=`, такое как  
  
```csharp  
x *= y  
```  
  
 эквивалентно  
  
```csharp  
x = x * y  
```  
  
 за исключением того, что `x` вычисляется только один раз. Для числовых типов [оператор *](../../../csharp/language-reference/operators/multiplication-operator.md) используется для выполнения операций умножения.  
  
 Оператор `*=` нельзя перегружать напрямую, однако пользовательские типы могут перегружать [оператор *](../../../csharp/language-reference/operators/multiplication-operator.md) (см. раздел [оператор](../../../csharp/language-reference/keywords/operator.md)).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
