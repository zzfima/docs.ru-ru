---
title: Обзор обработчиков событий (Windows Forms)
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
ms.openlocfilehash: 05acbfaf427060d015c2445360a7d73ebe97d070
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966839"
---
# <a name="event-handlers-overview-windows-forms"></a><span data-ttu-id="78321-102">Обзор обработчиков событий (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="78321-102">Event Handlers Overview (Windows Forms)</span></span>
<span data-ttu-id="78321-103">Обработчик событий — метод, связанный с событием.</span><span class="sxs-lookup"><span data-stu-id="78321-103">An event handler is a method that is bound to an event.</span></span> <span data-ttu-id="78321-104">При возникновении события выполняется код в обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="78321-104">When the event is raised, the code within the event handler is executed.</span></span> <span data-ttu-id="78321-105">Каждый обработчик событий предоставляет два параметра, которые дают возможность обрабатывать событие должным образом.</span><span class="sxs-lookup"><span data-stu-id="78321-105">Each event handler provides two parameters that allow you to handle the event properly.</span></span> <span data-ttu-id="78321-106">В примере показан обработчик событий для <xref:System.Windows.Forms.Button> элемента управления <xref:System.Windows.Forms.Control.Click> событий.</span><span class="sxs-lookup"><span data-stu-id="78321-106">The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
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
  
 <span data-ttu-id="78321-107">Первый параметр,`sender`, предоставляющий ссылку на объект, который вызвал событие.</span><span class="sxs-lookup"><span data-stu-id="78321-107">The first parameter,`sender`, provides a reference to the object that raised the event.</span></span> <span data-ttu-id="78321-108">Второй параметр, `e`, в приведенном выше примере передает объект события, которое обрабатывается.</span><span class="sxs-lookup"><span data-stu-id="78321-108">The second parameter, `e`, in the example above, passes an object specific to the event that is being handled.</span></span> <span data-ttu-id="78321-109">Ссылаясь на свойства объекта (и в некоторых случаях его методы), можно получить сведения, такие как расположение для события мыши или данных, передаваемых в событиях и перетащите указатель мыши.</span><span class="sxs-lookup"><span data-stu-id="78321-109">By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.</span></span>  
  
 <span data-ttu-id="78321-110">Обычно каждое событие создает обработчик событий с типом другой объект события для второго параметра.</span><span class="sxs-lookup"><span data-stu-id="78321-110">Typically each event produces an event handler with a different event-object type for the second parameter.</span></span> <span data-ttu-id="78321-111">Некоторые обработчики событий, например, для <xref:System.Windows.Forms.Control.MouseDown> и <xref:System.Windows.Forms.Control.MouseUp> события, имеют один и тот же тип объекта для второго параметра.</span><span class="sxs-lookup"><span data-stu-id="78321-111">Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter.</span></span> <span data-ttu-id="78321-112">Для этих типов событий можно использовать один и тот же обработчик событий для обработки обоих событий.</span><span class="sxs-lookup"><span data-stu-id="78321-112">For these types of events, you can use the same event handler to handle both events.</span></span>  
  
 <span data-ttu-id="78321-113">Можно также использовать тот же обработчик событий для обработки того же события для различных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="78321-113">You can also use the same event handler to handle the same event for different controls.</span></span> <span data-ttu-id="78321-114">Например, если у вас есть группы <xref:System.Windows.Forms.RadioButton> элементы управления формы, можно создать один обработчик событий для <xref:System.Windows.Forms.Control.Click> событий и каждого элемента управления <xref:System.Windows.Forms.Control.Click> привязки событий к одному обработчику событий.</span><span class="sxs-lookup"><span data-stu-id="78321-114">For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event and have each control's <xref:System.Windows.Forms.Control.Click> event bound to the single event handler.</span></span> <span data-ttu-id="78321-115">Дополнительные сведения см. в разделе [Как Подключение нескольких событий к одному обработчику в Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="78321-115">For more information, see [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78321-116">См. также</span><span class="sxs-lookup"><span data-stu-id="78321-116">See also</span></span>

- [<span data-ttu-id="78321-117">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="78321-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="78321-118">Общие сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="78321-118">Events Overview</span></span>](events-overview-windows-forms.md)
