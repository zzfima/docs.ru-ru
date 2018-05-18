---
title: Практическое руководство. Реализация пользовательских методов доступа к событиям (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
ms.openlocfilehash: 6d0181a93831fa054d7ba1a740bafe1f228bfc15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a>Практическое руководство. Реализация пользовательских методов доступа к событиям (Руководство по программированию в C#)
Событие представляет собой особый вид многоадресного делегата, который можно вызвать только из класса, где он объявлен. В клиентском коде создается подписка на событие. Для этого предоставляется ссылка на метод, который должен вызываться при возникновении этого события. Эти методы добавляются в список вызова делегата с помощью методов доступа к событиям, которые схожи с методами доступа к свойствам и отличаются только именами (`add` и `remove`). В большинстве случаев реализовывать настраиваемые методы доступа к событиям не требуется. Если в коде отсутствуют настраиваемые методы доступа к событиям, компилятор добавляет их автоматически. Тем не менее в некоторых случаях требуется реализовать настраиваемое поведение. Один из таких сценариев показан в разделе [Практическое руководство. Реализация событий интерфейса](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как реализовать настраиваемые методы доступа add и remove для события. При необходимости вы можете заменять любой код в методах доступа, однако мы рекомендуем заблокировать событие, прежде чем добавлять или удалять новый метод обработчика событий.  
  
```csharp
event EventHandler IDrawingObject.OnDraw  
{  
    add  
    {  
        lock (PreDrawEvent)  
        {  
            PreDrawEvent += value;  
        }  
    }  
    remove  
    {  
        lock (PreDrawEvent)  
        {  
            PreDrawEvent -= value;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>См. также  
 [События](../../../csharp/programming-guide/events/index.md)  
 [event](../../../csharp/language-reference/keywords/event.md)