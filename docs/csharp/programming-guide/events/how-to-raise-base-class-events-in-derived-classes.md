---
title: "Практическое руководство. Создание событий базового класса в производных классах (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 548409d3f632213f3ff1de0a27a70b9f42b18332
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a><span data-ttu-id="0bf6d-102">Практическое руководство. Создание событий базового класса в производных классах (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="0bf6d-102">How to: Raise Base Class Events in Derived Classes (C# Programming Guide)</span></span>
<span data-ttu-id="0bf6d-103">В следующем простом примере показан стандартный способ объявления событий в базовом классе, позволяющий вызывать их из производных классов.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-103">The following simple example shows the standard way to declare events in a base class so that they can also be raised from derived classes.</span></span> <span data-ttu-id="0bf6d-104">Этот шаблон активно применяется в классах Windows Forms в библиотеке классов [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0bf6d-104">This pattern is used extensively in Windows Forms classes in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library.</span></span>  
  
 <span data-ttu-id="0bf6d-105">При создании класса, который можно использовать в качестве базового для других классов, следует учитывать тот факт, что события представляют собой особый тип делегатов, который может вызываться только в том классе, который их объявил.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-105">When you create a class that can be used as a base class for other classes, you should consider the fact that events are a special type of delegate that can only be invoked from within the class that declared them.</span></span> <span data-ttu-id="0bf6d-106">Производные классы не могут создавать события, объявленные в базовом классе, напрямую.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-106">Derived classes cannot directly invoke events that are declared within the base class.</span></span> <span data-ttu-id="0bf6d-107">Несмотря на то, что в некоторых обстоятельствах вам может потребоваться событие, вызываемое только базовым классом, в большинстве случаев рекомендуется разрешать производному классу вызывать события базового класса.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-107">Although sometimes you may want an event that can only be raised by the base class, most of the time, you should enable the derived class to invoke base class events.</span></span> <span data-ttu-id="0bf6d-108">Для этого следует создать в базовом классе защищенный метод, предоставляющий оболочку для события.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-108">To do this, you can create a protected invoking method in the base class that wraps the event.</span></span> <span data-ttu-id="0bf6d-109">Вызывая или перезаписывая вызывающий метод, производные классы могут вызывать событие косвенно.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-109">By calling or overriding this invoking method, derived classes can invoke the event indirectly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bf6d-110">Не объявляйте виртуальные события в базовом классе и не переопределяйте их в производном классе.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-110">Do not declare virtual events in a base class and override them in a derived class.</span></span> <span data-ttu-id="0bf6d-111">Компилятор c# не обрабатывает их корректно, поэтому сложно сказать, будет ли подписчик производного события на самом деле подписываться на событие базового класса.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-111">The C# compiler does not handle these correctly and it is unpredictable whether a subscriber to the derived event will actually be subscribing to the base class event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bf6d-112">Пример</span><span class="sxs-lookup"><span data-stu-id="0bf6d-112">Example</span></span>  
 [!code-csharp[csProgGuideEvents#1](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-raise-base-class-events-in-derived-classes_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0bf6d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="0bf6d-113">See Also</span></span>  
 [<span data-ttu-id="0bf6d-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0bf6d-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0bf6d-115">События</span><span class="sxs-lookup"><span data-stu-id="0bf6d-115">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="0bf6d-116">Делегаты</span><span class="sxs-lookup"><span data-stu-id="0bf6d-116">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="0bf6d-117">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="0bf6d-117">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="0bf6d-118">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0bf6d-118">Creating Event Handlers in Windows Forms</span></span>](https://msdn.microsoft.com/library/dacysss4.aspx)
