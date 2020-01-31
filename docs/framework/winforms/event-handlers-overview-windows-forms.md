---
title: Общие сведения об обработчиках событий
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
ms.openlocfilehash: 10ba458197973ede35849a86fec35003f139b8d2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743497"
---
# <a name="event-handlers-overview-windows-forms"></a><span data-ttu-id="164d8-102">Обзор обработчиков событий (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="164d8-102">Event Handlers Overview (Windows Forms)</span></span>
<span data-ttu-id="164d8-103">Обработчик событий — это метод, привязанный к событию.</span><span class="sxs-lookup"><span data-stu-id="164d8-103">An event handler is a method that is bound to an event.</span></span> <span data-ttu-id="164d8-104">При возникновении события выполняется код в обработчике событий.</span><span class="sxs-lookup"><span data-stu-id="164d8-104">When the event is raised, the code within the event handler is executed.</span></span> <span data-ttu-id="164d8-105">Каждый обработчик событий предоставляет два параметра, которые позволяют правильно управлять событием.</span><span class="sxs-lookup"><span data-stu-id="164d8-105">Each event handler provides two parameters that allow you to handle the event properly.</span></span> <span data-ttu-id="164d8-106">В следующем примере показан обработчик событий для <xref:System.Windows.Forms.Control.Click> события элемента управления <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="164d8-106">The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)   
{  
  
}  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 <span data-ttu-id="164d8-107">Первый параметр,`sender`, предоставляет ссылку на объект, который вызвал событие.</span><span class="sxs-lookup"><span data-stu-id="164d8-107">The first parameter,`sender`, provides a reference to the object that raised the event.</span></span> <span data-ttu-id="164d8-108">Второй параметр, `e`, в приведенном выше примере передает объект, относящийся к обрабатываемому событию.</span><span class="sxs-lookup"><span data-stu-id="164d8-108">The second parameter, `e`, in the example above, passes an object specific to the event that is being handled.</span></span> <span data-ttu-id="164d8-109">Ссылаясь на свойства объекта (и иногда его методы), можно получить такие сведения, как расположение мыши для событий мыши или данных, передаваемых в событиях перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="164d8-109">By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.</span></span>  
  
 <span data-ttu-id="164d8-110">Обычно каждое событие создает обработчик событий с другим типом объекта события для второго параметра.</span><span class="sxs-lookup"><span data-stu-id="164d8-110">Typically each event produces an event handler with a different event-object type for the second parameter.</span></span> <span data-ttu-id="164d8-111">Некоторые обработчики событий, например, для событий <xref:System.Windows.Forms.Control.MouseDown> и <xref:System.Windows.Forms.Control.MouseUp>, имеют одинаковый тип объекта для второго параметра.</span><span class="sxs-lookup"><span data-stu-id="164d8-111">Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter.</span></span> <span data-ttu-id="164d8-112">Для этих типов событий можно использовать один и тот же обработчик событий для обработки обоих событий.</span><span class="sxs-lookup"><span data-stu-id="164d8-112">For these types of events, you can use the same event handler to handle both events.</span></span>  
  
 <span data-ttu-id="164d8-113">Можно также использовать один и тот же обработчик событий для обработки одного и того же события для различных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="164d8-113">You can also use the same event handler to handle the same event for different controls.</span></span> <span data-ttu-id="164d8-114">Например, если в форме имеется группа элементов управления <xref:System.Windows.Forms.RadioButton>, можно создать один обработчик событий для <xref:System.Windows.Forms.Control.Click> события и связать событие <xref:System.Windows.Forms.Control.Click> каждого элемента управления с одним обработчиком событий.</span><span class="sxs-lookup"><span data-stu-id="164d8-114">For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event and have each control's <xref:System.Windows.Forms.Control.Click> event bound to the single event handler.</span></span> <span data-ttu-id="164d8-115">Дополнительные сведения см. [в разделе руководство. Подключение нескольких событий к одному обработчику событий в Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="164d8-115">For more information, see [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="164d8-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="164d8-116">See also</span></span>

- [<span data-ttu-id="164d8-117">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="164d8-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="164d8-118">Общие сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="164d8-118">Events Overview</span></span>](events-overview-windows-forms.md)
