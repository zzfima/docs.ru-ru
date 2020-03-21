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
ms.openlocfilehash: ffec8a9f8e080dec78152e62e00e2dceefbdaab0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141696"
---
# <a name="event-handlers-overview-windows-forms"></a><span data-ttu-id="7ee6c-102">Обзор обработчиков событий (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="7ee6c-102">Event Handlers Overview (Windows Forms)</span></span>
<span data-ttu-id="7ee6c-103">Обработчик событий — это метод, связанный с событием.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-103">An event handler is a method that is bound to an event.</span></span> <span data-ttu-id="7ee6c-104">При поднятии события выполняется код в обработчике события.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-104">When the event is raised, the code within the event handler is executed.</span></span> <span data-ttu-id="7ee6c-105">Каждый обработчик событий предоставляет два параметра, которые позволяют правильно обрабатывать событие.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-105">Each event handler provides two parameters that allow you to handle the event properly.</span></span> <span data-ttu-id="7ee6c-106">В следующем примере отображается <xref:System.Windows.Forms.Button> обработчик события для события элемента <xref:System.Windows.Forms.Control.Click> управления.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-106">The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
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
  
 <span data-ttu-id="7ee6c-107">Первый параметр,`sender`обеспечивает ссылку на объект, который поднял событие.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-107">The first parameter,`sender`, provides a reference to the object that raised the event.</span></span> <span data-ttu-id="7ee6c-108">Второй параметр, `e`в приведенном выше примере, передает объект, специфичный для обрабатываемого события.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-108">The second parameter, `e`, in the example above, passes an object specific to the event that is being handled.</span></span> <span data-ttu-id="7ee6c-109">Ссылаясь на свойства объекта (а иногда и его методы), можно получить информацию, такую как расположение мыши для событий мыши или данные, передаваемые в событиях перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-109">By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.</span></span>  
  
 <span data-ttu-id="7ee6c-110">Обычно каждое событие производит обработчик событий с другим типом объекта события для второго параметра.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-110">Typically each event produces an event handler with a different event-object type for the second parameter.</span></span> <span data-ttu-id="7ee6c-111">Некоторые обработчики событий, <xref:System.Windows.Forms.Control.MouseDown> например для событий и <xref:System.Windows.Forms.Control.MouseUp> событий, имеют один и тот же тип объекта для второго параметра.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-111">Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter.</span></span> <span data-ttu-id="7ee6c-112">Для этих типов событий можно использовать один и тот же обработчик событий для обработки обоих событий.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-112">For these types of events, you can use the same event handler to handle both events.</span></span>  
  
 <span data-ttu-id="7ee6c-113">Вы также можете использовать один и тот же обработчик событий для обработки одного и того же события для различных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-113">You can also use the same event handler to handle the same event for different controls.</span></span> <span data-ttu-id="7ee6c-114">Например, если у вас <xref:System.Windows.Forms.RadioButton> есть группа элементов управления в форме, <xref:System.Windows.Forms.Control.Click> можно создать один <xref:System.Windows.Forms.Control.Click> обработчик событий и привязывать событие каждого элемента управления к одному обработчику событий.</span><span class="sxs-lookup"><span data-stu-id="7ee6c-114">For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event and have each control's <xref:System.Windows.Forms.Control.Click> event bound to the single event handler.</span></span> <span data-ttu-id="7ee6c-115">Для получения дополнительной информации [см. Как: Подключите несколько событий к обработчику одного события в формах Windows.](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="7ee6c-115">For more information, see [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee6c-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7ee6c-116">See also</span></span>

- [<span data-ttu-id="7ee6c-117">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ee6c-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="7ee6c-118">Общие сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="7ee6c-118">Events Overview</span></span>](events-overview-windows-forms.md)
