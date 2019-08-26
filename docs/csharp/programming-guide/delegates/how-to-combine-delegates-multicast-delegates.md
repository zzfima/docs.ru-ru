---
title: Практическое руководство. Руководство по программированию на C#. Объединение делегатов (многоадресные делегаты)
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: d9430021e6a9b438822f1a6dc201f64adf4fdb0f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69590667"
---
# <a name="how-to-combine-delegates-multicast-delegatesc-programming-guide"></a>Практическое руководство. Руководство по программированию на C#. Объединение делегатов (многоадресные делегаты)
В этом примере показано создание многоадресных делегатов. Объекты [делегатов](../../language-reference/keywords/delegate.md) обладают полезным свойством, благодаря которому одному экземпляру делегата с помощью оператора `+` можно присвоить несколько объектов. Многоадресный делегат содержит список присвоенных ему делегатов. При вызове многоадресного делегата поочередно вызываются представленные в его списке делегаты. Объединять можно только делегаты одного типа.  
  
 С помощью оператора `-` можно удалить делегат, входящий в состав многоадресного делегата.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a>См. также

- <xref:System.MulticastDelegate>
- [Руководство по программированию на C#](../index.md)
- [События](../events/index.md)
