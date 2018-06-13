---
title: Оператор ++ (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: 0fe1150ca7267d02feeab33168eab7f79734c2a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275068"
---
# <a name="-operator-c-reference"></a>Оператор ++ (справочник по C#)
Оператор инкремента (`++`) увеличивает операнд на 1. Оператор инкремента может находиться перед своим операндом или после него: `++variable` и `variable++`.  
  
## <a name="remarks"></a>Примечания  
 Первый случай — это операция префиксного инкремента. Результатом операции является значение операнда после его увеличения.  
  
 Второй случай — это операция постфиксного инкремента. Результатом операции является значение операнда до его увеличения.  
  
 Числовые типы и типы перечислений имеют предварительно определенные операторы инкремента. Определяемые пользователем типы могут перегружать оператор `++` . Операции с целыми типами обычно разрешены и для перечислений.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
