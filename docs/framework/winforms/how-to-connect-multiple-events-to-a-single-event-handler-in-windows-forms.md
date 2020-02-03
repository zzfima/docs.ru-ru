---
title: Как подключить несколько событий к одному обработчику событий
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
ms.openlocfilehash: 0591291522ab1da04fef90bf1c0a73cf33ba0518
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739604"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a><span data-ttu-id="95dfd-102">Практическое руководство. Подключение несколько событий к одному обработчику в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="95dfd-102">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>
<span data-ttu-id="95dfd-103">В структуре приложения может оказаться необходимым использовать один обработчик событий для нескольких событий или несколько событий выполняют одну и ту же процедуру.</span><span class="sxs-lookup"><span data-stu-id="95dfd-103">In your application design, you may find it necessary to use a single event handler for multiple events or have multiple events perform the same procedure.</span></span> <span data-ttu-id="95dfd-104">Например, зачастую очень мощная временная заставка для того, чтобы команда меню вызывала то же самое событие, что и кнопка в форме, если они предоставляют те же функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="95dfd-104">For example, it is often a powerful time-saver to have a menu command raise the same event as a button on your form does if they expose the same functionality.</span></span> <span data-ttu-id="95dfd-105">Это можно сделать с помощью представления событий окно свойств в C# или с `Handles` помощью раскрывающихся списков **имя класса** и **имя метода** в Visual Basic редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="95dfd-105">You can do this by using the Events view of the Properties window in C# or using the `Handles` keyword and the **Class Name** and **Method Name** drop-down boxes in the Visual Basic Code Editor.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a><span data-ttu-id="95dfd-106">Подключение нескольких событий к одному обработчику событий в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="95dfd-106">To connect multiple events to a single event handler in Visual Basic</span></span>  
  
1. <span data-ttu-id="95dfd-107">Щелкните форму правой кнопкой мыши и выберите команду **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="95dfd-107">Right-click the form and choose **View Code**.</span></span>  
  
2. <span data-ttu-id="95dfd-108">В раскрывающемся списке **имя класса** выберите один из элементов управления, для которых требуется дескриптор обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="95dfd-108">From the **Class Name** drop-down box, select one of the controls that you want to have the event handler handle.</span></span>  
  
3. <span data-ttu-id="95dfd-109">В раскрывающемся списке **имя метода** выберите одно из событий, которое должен обработать обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="95dfd-109">From the **Method Name** drop-down box, select one of the events that you want the event handler to handle.</span></span>  
  
4. <span data-ttu-id="95dfd-110">Редактор кода вставляет соответствующий обработчик событий и размещает точку вставки в методе.</span><span class="sxs-lookup"><span data-stu-id="95dfd-110">The Code Editor inserts the appropriate event handler and positions the insertion point within the method.</span></span> <span data-ttu-id="95dfd-111">В приведенном ниже примере это событие <xref:System.Windows.Forms.Control.Click> для элемента управления <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="95dfd-111">In the example below, it is the <xref:System.Windows.Forms.Control.Click> event for the <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. <span data-ttu-id="95dfd-112">Добавьте другие события, которые вы хотите обработать, в предложение `Handles`.</span><span class="sxs-lookup"><span data-stu-id="95dfd-112">Append the other events you would like handled to the `Handles` clause.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. <span data-ttu-id="95dfd-113">Добавьте соответствующий код в обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="95dfd-113">Add the appropriate code to the event handler.</span></span>  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a><span data-ttu-id="95dfd-114">Подключение нескольких событий к одному обработчику событий в C\#</span><span class="sxs-lookup"><span data-stu-id="95dfd-114">To connect multiple events to a single event handler in C\#</span></span>
  
1. <span data-ttu-id="95dfd-115">Выберите элемент управления, к которому необходимо подключить обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="95dfd-115">Select the control to which you want to connect an event handler.</span></span>  
  
2. <span data-ttu-id="95dfd-116">В окно свойств нажмите кнопку **события** (![кнопка события](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span><span class="sxs-lookup"><span data-stu-id="95dfd-116">In the Properties window, click the **Events** button (![Events Button](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).</span></span>  
  
3. <span data-ttu-id="95dfd-117">Щелкните имя события, которое требуется обработать.</span><span class="sxs-lookup"><span data-stu-id="95dfd-117">Click the name of the event that you want to handle.</span></span>  
  
4. <span data-ttu-id="95dfd-118">В разделе значение рядом с именем события нажмите кнопку раскрывающегося списка, чтобы отобразить список существующих обработчиков событий, соответствующих сигнатуре метода события, которое требуется обработать.</span><span class="sxs-lookup"><span data-stu-id="95dfd-118">In the value section next to the event name, click the drop-down button to display a list of existing event handlers that match the method signature of the event you want to handle.</span></span>  
  
5. <span data-ttu-id="95dfd-119">Выберите из списка соответствующий обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="95dfd-119">Select the appropriate event handler from the list.</span></span>  
  
     <span data-ttu-id="95dfd-120">Код будет добавлен в форму для привязки события к существующему обработчику событий.</span><span class="sxs-lookup"><span data-stu-id="95dfd-120">Code will be added to the form to bind the event to the existing event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95dfd-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="95dfd-121">See also</span></span>

- [<span data-ttu-id="95dfd-122">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="95dfd-122">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="95dfd-123">Общие сведения об обработчиках событий</span><span class="sxs-lookup"><span data-stu-id="95dfd-123">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
