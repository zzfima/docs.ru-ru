---
title: Оператор % (Справочник по C#)
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 796b4a40347fc5881db27a8a8a28404c7c4e8c5b
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a>Оператор % (Справочник по C#)
Оператор остатка (`%`) вычисляет остаток от деления первого операнда на второй. Все числовые типы имеют предопределенные операторы вычисления остатка. 
  
## <a name="remarks"></a>Примечания  
 Формула `a % b` всегда возвращает значение в диапазоне `(-b, b)`, исключая границы (она не может вернуть значение `b` или `-b`), с сохранением знака делимого. При целочисленном делении для оператора остатка соблюдается правило `a % b = a - (a / b) * b`.
  
 Эту операцию не следует путать с получением канонического модуля, которое следует тому же правилу, но округление производится к меньшему и возвращаются значения в диапазоне `[0, b)`. В C# нет оператора для получения канонического модуля. Однако для положительного делимого результат будет аналогичным.
  
 Определяемые пользователем типы могут вызвать перегрузку оператора `%` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) . При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/remainder-operator_1.cs)]  
  
## <a name="comments"></a>Комментарии  
 Обратите внимание на ошибки округления, связанные с использованием типа double.  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
