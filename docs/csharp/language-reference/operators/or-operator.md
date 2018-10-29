---
title: Оператор | (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- '|_CSharpKeyword'
helpviewer_keywords:
- bitwise OR operator [C#]
- '| operator [C#]'
- binary operator (|) [C#]
ms.assetid: 82d6bb78-54c8-40bf-b679-531180ddaf70
ms.openlocfilehash: 999df9db0819a5f33e21a29b892de0a8854dd5d8
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48028182"
---
# <a name="-operator-c-reference"></a>Оператор | (Справочник по C#)
Бинарные операторы `|` предварительно определены для целочисленных типов и типа `bool`. Для целочисленных типов оператор `|` выполняет побитовую операцию ИЛИ для всех своих операндов. Для операндов `bool` оператор `|` выполняет логическую операцию ИЛИ для всех своих операндов. Таким образом, значение `false` возвращается только тогда, когда оба операнда имеют значение `false`.  
  
## <a name="remarks"></a>Примечания  
 Бинарный оператор `|` вычисляет оба операнда независимо от значения первого из них, в отличие от [условного оператора OR](conditional-or-operator.md)`||`.
 
 Определяемые пользователем типы могут вызвать перегрузку оператора `|` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) .  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#31](../../../csharp/language-reference/operators/codesnippet/CSharp/or-operator_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
