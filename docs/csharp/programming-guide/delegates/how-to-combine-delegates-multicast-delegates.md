---
title: Объединение делегатов (многоадресные делегаты) (руководство по программированию на C#)
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: 7b5b9ba5c9bf70983fac9f869836b4c8c5449eca
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705383"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a>Практическое руководство. Объединение делегатов (многоадресные делегаты) (руководство по программированию на C#)
В этом примере показано создание многоадресных делегатов. Объекты [делегатов](../../language-reference/builtin-types/reference-types.md) обладают полезным свойством, благодаря которому одному экземпляру делегата с помощью оператора `+` можно присвоить несколько объектов. Многоадресный делегат содержит список присвоенных ему делегатов. При вызове многоадресного делегата поочередно вызываются представленные в его списке делегаты. Объединять можно только делегаты одного типа.  
  
 С помощью оператора `-` можно удалить делегат, входящий в состав многоадресного делегата.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a>См. также

- <xref:System.MulticastDelegate>
- [Руководство по программированию на C#](../index.md)
- [События](../events/index.md)
