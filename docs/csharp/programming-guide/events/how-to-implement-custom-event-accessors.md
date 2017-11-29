---
title: "Практическое руководство. Реализация пользовательских методов доступа к событиям (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- accessors [C#], event accessors
- add accessor [C#]
- events [C#], add accessor
- events [C#], remove accessor
- remove accessor [C#]
ms.assetid: bf903abf-03a4-4f7b-ab6b-b7e59bc2ee1e
caps.latest.revision: "7"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3ff5fedeeaa427bb62991f9b406c167647dc376d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-custom-event-accessors-c-programming-guide"></a><span data-ttu-id="3ef40-102">Практическое руководство. Реализация пользовательских методов доступа к событиям (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="3ef40-102">How to: Implement Custom Event Accessors (C# Programming Guide)</span></span>
<span data-ttu-id="3ef40-103">Событие представляет собой особый вид многоадресного делегата, который можно вызвать только из класса, где он объявлен.</span><span class="sxs-lookup"><span data-stu-id="3ef40-103">An event is a special kind of multicast delegate that can only be invoked from within the class that  it is declared in.</span></span> <span data-ttu-id="3ef40-104">В клиентском коде создается подписка на событие. Для этого предоставляется ссылка на метод, который должен вызываться при возникновении этого события.</span><span class="sxs-lookup"><span data-stu-id="3ef40-104">Client code subscribes to the event by providing a reference to a method that should be invoked when the event is fired.</span></span> <span data-ttu-id="3ef40-105">Эти методы добавляются в список вызова делегата с помощью методов доступа к событиям, которые схожи с методами доступа к свойствам и отличаются только именами (`add` и `remove`).</span><span class="sxs-lookup"><span data-stu-id="3ef40-105">These methods are added to the delegate's invocation list through event accessors, which resemble property accessors, except that event accessors are named `add` and `remove`.</span></span> <span data-ttu-id="3ef40-106">В большинстве случаев реализовывать настраиваемые методы доступа к событиям не требуется.</span><span class="sxs-lookup"><span data-stu-id="3ef40-106">In most cases, you do not have to supply custom event accessors.</span></span> <span data-ttu-id="3ef40-107">Если в коде отсутствуют настраиваемые методы доступа к событиям, компилятор добавляет их автоматически.</span><span class="sxs-lookup"><span data-stu-id="3ef40-107">When no custom event accessors are supplied in your code, the compiler will add them automatically.</span></span> <span data-ttu-id="3ef40-108">Тем не менее в некоторых случаях требуется реализовать настраиваемое поведение.</span><span class="sxs-lookup"><span data-stu-id="3ef40-108">However, in some cases you may have to provide custom behavior.</span></span> <span data-ttu-id="3ef40-109">Один из таких сценариев показан в разделе [Практическое руководство. Реализация событий интерфейса](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).</span><span class="sxs-lookup"><span data-stu-id="3ef40-109">One such case is shown in the topic [How to:  Implement Interface Events](../../../csharp/programming-guide/events/how-to-implement-interface-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ef40-110">Пример</span><span class="sxs-lookup"><span data-stu-id="3ef40-110">Example</span></span>  
 <span data-ttu-id="3ef40-111">В следующем примере показано, как реализовать настраиваемые методы доступа add и remove для события.</span><span class="sxs-lookup"><span data-stu-id="3ef40-111">The following example shows how to implement custom add and remove event accessors.</span></span> <span data-ttu-id="3ef40-112">При необходимости вы можете заменять любой код в методах доступа, однако мы рекомендуем заблокировать событие, прежде чем добавлять или удалять новый метод обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="3ef40-112">Although you can substitute any code inside the accessors, we recommend that you lock the event before you add or remove a new event handler method.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3ef40-113">См. также</span><span class="sxs-lookup"><span data-stu-id="3ef40-113">See Also</span></span>  
 [<span data-ttu-id="3ef40-114">События</span><span class="sxs-lookup"><span data-stu-id="3ef40-114">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="3ef40-115">event</span><span class="sxs-lookup"><span data-stu-id="3ef40-115">event</span></span>](../../../csharp/language-reference/keywords/event.md)
