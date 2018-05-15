---
title: Практическое руководство. Подключение несколько событий к одному обработчику в Windows Forms
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
ms.openlocfilehash: 527a76376a4c1d5ad051f4768ca2bd42c3548b3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="ef213-102">Практическое руководство. Подключение несколько событий к одному обработчику в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef213-102">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="ef213-103">При разработке приложения может оказаться необходимо использовать один обработчик событий для нескольких событий или несколькими событиями выполните ту же процедуру.</span><span class="sxs-lookup"><span data-stu-id="ef213-103">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="ef213-104">Например часто бывает мощные время заставки иметь команды меню вызова того же события, как кнопки на форме, если они предоставляют те же функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="ef213-104">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="ef213-105">Это можно сделать с помощью представления событий окна свойств в C# или `Handles` ключевое слово и **имя класса** и **имя метода** раскрывающихся списков в редакторе кода Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ef213-105">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="ef213-106">Чтобы подключить несколько событий к одному обработчику в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ef213-106">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1.  <span data-ttu-id="ef213-107">Щелкните форму правой кнопкой мыши и выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="ef213-107">Right-click the form and choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="ef213-108">Из **имя класса** раскрывающегося списка, выберите один из элементов управления, которые требуется обработка обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="ef213-108">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3.  <span data-ttu-id="ef213-109">Из **имя метода** раскрывающегося списка, выберите одно из событий, которые вы хотите обработчик событий для обработки.</span><span class="sxs-lookup"><span data-stu-id="ef213-109">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4.  <span data-ttu-id="ef213-110">Редактор кода вставляет соответствующий обработчик событий и помещает курсор в методе.</span><span class="sxs-lookup"><span data-stu-id="ef213-110">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="ef213-111">В приведенном ниже примере это <xref:System.Windows.Forms.Control.Click> событий для <xref:System.Windows.Forms.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ef213-111">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  <span data-ttu-id="ef213-112">Добавьте другие события, необходимо обработать для `Handles` предложения.</span><span class="sxs-lookup"><span data-stu-id="ef213-112">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  <span data-ttu-id="ef213-113">Добавьте соответствующий код в обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="ef213-113">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="ef213-114">Чтобы подключить несколько событий к одному обработчику событий в C#</span><span class="sxs-lookup"><span data-stu-id="ef213-114">To connect multiple events to a single event handler in C#</span></span>  
  
1.  <span data-ttu-id="ef213-115">Выберите элемент управления, к которому требуется подключить обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="ef213-115">Select the control to which you want to connect an event handler.</span></span>  
  
2.  <span data-ttu-id="ef213-116">В окне «Свойства» щелкните **событий** кнопки (![кнопка событий](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span><span class="sxs-lookup"><span data-stu-id="ef213-116">In the Properties window, click the **Events** button (![Events Button](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3.  <span data-ttu-id="ef213-117">Щелкните имя события, которое необходимо обработать.</span><span class="sxs-lookup"><span data-stu-id="ef213-117">Click the name of the event that you want to handle.</span></span>  
  
4.  <span data-ttu-id="ef213-118">В разделе значений рядом с именем события нажмите кнопку раскрывающегося списка для отображения списка существующих обработчиков событий, которые соответствуют сигнатуре метода события, которое необходимо обработать.</span><span class="sxs-lookup"><span data-stu-id="ef213-118">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5.  <span data-ttu-id="ef213-119">Выберите соответствующий обработчик событий из списка.</span><span class="sxs-lookup"><span data-stu-id="ef213-119">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="ef213-120">Для привязки события в существующий обработчик событий в форму будет добавлен код.</span><span class="sxs-lookup"><span data-stu-id="ef213-120">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef213-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ef213-121">See Also</span></span>  
 [<span data-ttu-id="ef213-122">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ef213-122">Creating Event Handlers in Windows Forms</span></span>](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [<span data-ttu-id="ef213-123">Общие сведения об обработчиках событий</span><span class="sxs-lookup"><span data-stu-id="ef213-123">Event Handlers Overview</span></span>](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)
