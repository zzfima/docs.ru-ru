---
title: Оператор -- (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 615b100447233856ab3740d075d69e3ae19285fd
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45648786"
---
# <a name="---operator-c-reference"></a>Оператор -- (Справочник по C#)
Оператор декремента (`--`) уменьшает операнд на 1. Оператор декремента может находиться перед своим операндом или после него: `--variable` и `variable--`. Первый случай — это операция префиксного декремента. Результатом операции является значение операнда после его уменьшения. Второй случай — это операция постфиксного декремента. Результатом операции является значение операнда до его уменьшения.  
  
## <a name="remarks"></a>Примечания  
 Числовые типы и типы перечислений имеют предварительно определенные операторы декремента.  
  
 Определяемые пользователем типы могут вызвать перегрузку оператора `--` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) . Операции с целыми типами обычно разрешены и для перечислений.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
