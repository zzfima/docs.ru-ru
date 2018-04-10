---
title: Оператор ++ (справочник по C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6deb2f772fefc93020e7eaaed6be35e48b11df7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
