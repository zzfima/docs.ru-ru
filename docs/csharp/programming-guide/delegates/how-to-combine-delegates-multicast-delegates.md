---
title: Как выполнить Руководство по программированию на C#. Объединение делегатов (многоадресные делегаты)
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d835f9b22fef550d6e73cbd620a283bd71e393ec
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237796"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a>Как выполнить Руководство по программированию на C#. Объединение делегатов (многоадресные делегаты)
В этом примере показано создание многоадресных делегатов. Объекты [делегатов](../../../csharp/language-reference/keywords/delegate.md) обладают полезным свойством, благодаря которому одному экземпляру делегата с помощью оператора `+` можно присвоить несколько объектов. Многоадресный делегат содержит список присвоенных ему делегатов. При вызове многоадресного делегата поочередно вызываются представленные в его списке делегаты. Объединять можно только делегаты одного типа.  
  
 С помощью оператора `-` можно удалить делегат, входящий в состав многоадресного делегата.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## <a name="see-also"></a>См. также

- <xref:System.MulticastDelegate>  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [События](../../../csharp/programming-guide/events/index.md)
