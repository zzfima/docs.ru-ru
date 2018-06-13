---
title: Практическое руководство. Объединение делегатов (многоадресные делегаты) (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: e1214a4d281dbcb9d8186770b68510d3d9a4b15f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33327399"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a>Практическое руководство. Объединение делегатов (многоадресные делегаты) (Руководство по программированию в C#)
В этом примере показано создание многоадресных делегатов. Объекты [делегатов](../../../csharp/language-reference/keywords/delegate.md) обладают полезным свойством, благодаря которому одному экземпляру делегата с помощью оператора `+` можно присвоить несколько объектов. Многоадресный делегат содержит список присвоенных ему делегатов. При вызове многоадресного делегата поочередно вызываются представленные в его списке делегаты. Объединять можно только делегаты одного типа.  
  
 С помощью оператора `-` можно удалить делегат, входящий в состав многоадресного делегата.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.MulticastDelegate>  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [События](../../../csharp/programming-guide/events/index.md)
