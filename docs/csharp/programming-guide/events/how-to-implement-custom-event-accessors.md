---
title: "Практическое руководство. Реализация пользовательских методов доступа к событиям (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
caps.latest.revision: 7
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 71e1c16c9c6426ffb95020e4d7211dc1000f6796
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a>Практическое руководство. Реализация пользовательских методов доступа к событиям (Руководство по программированию в C#)
Событие представляет собой особый вид многоадресного делегата, который можно вызвать только из класса, где он объявлен. В клиентском коде создается подписка на событие. Для этого предоставляется ссылка на метод, который должен вызываться при возникновении этого события. Эти методы добавляются в список вызова делегата с помощью методов доступа к событиям, которые схожи с методами доступа к свойствам и отличаются только именами (`add` и `remove`). В большинстве случаев реализовывать настраиваемые методы доступа к событиям не требуется. Если в коде отсутствуют настраиваемые методы доступа к событиям, компилятор добавляет их автоматически. Тем не менее в некоторых случаях требуется реализовать настраиваемое поведение. Один из таких сценариев показан в разделе [Практическое руководство. Реализация событий интерфейса](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как реализовать настраиваемые методы доступа add и remove для события. При необходимости вы можете заменять любой код в методах доступа, однако мы рекомендуем заблокировать событие, прежде чем добавлять или удалять новый метод обработчика событий.  
  
```  
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

