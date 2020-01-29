---
title: Реагирование на нажатия кнопок
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], responding to Click events
- events [Windows Forms], Click events
- Click event [Windows Forms], Button control
- MouseDown event
- Button control [Windows Forms], click response
- double-clicks
- examples [Windows Forms], controls
- Click event [Windows Forms], responding to
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
ms.openlocfilehash: dd6cf75a316257c86a23b44a818422336c12aa67
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735713"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="744a7-102">Практическое руководство. Обработка события нажатия кнопки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="744a7-102">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="744a7-103">Наиболее базовым использованием элемента управления Windows Forms <xref:System.Windows.Forms.Button> является выполнение некоторого кода при нажатии кнопки.</span><span class="sxs-lookup"><span data-stu-id="744a7-103">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="744a7-104">При щелчке элемента управления <xref:System.Windows.Forms.Button> также создается ряд других событий, таких как <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>и события <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="744a7-104">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="744a7-105">Если вы планируете присоединить обработчики событий для этих связанных событий, убедитесь, что их действия не конфликтуют.</span><span class="sxs-lookup"><span data-stu-id="744a7-105">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="744a7-106">Например, если нажать кнопку, чтобы очистить сведения, введенные пользователем в текстовое поле, при наведении указателя мыши на кнопку не должно отображаться всплывающая подсказка с несуществующими сведениями.</span><span class="sxs-lookup"><span data-stu-id="744a7-106">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="744a7-107">Если пользователь пытается дважды щелкнуть элемент управления <xref:System.Windows.Forms.Button>, каждый щелчок будет обрабатываться отдельно. то есть элемент управления не поддерживает событие двойного щелчка.</span><span class="sxs-lookup"><span data-stu-id="744a7-107">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="744a7-108">Реагирование на нажатие кнопки</span><span class="sxs-lookup"><span data-stu-id="744a7-108">To respond to a button click</span></span>  
  
- <span data-ttu-id="744a7-109">В `Click` кнопки <xref:System.EventHandler> записать код для выполнения.</span><span class="sxs-lookup"><span data-stu-id="744a7-109">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> <span data-ttu-id="744a7-110">`Button1_Click` должны быть привязаны к элементу управления.</span><span class="sxs-lookup"><span data-stu-id="744a7-110">`Button1_Click` must be bound to the control.</span></span> <span data-ttu-id="744a7-111">Дополнительные сведения см. [в разделе инструкции. Создание обработчиков событий во время выполнения для Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="744a7-111">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="744a7-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="744a7-112">See also</span></span>

- [<span data-ttu-id="744a7-113">Общие сведения об элементе управления Button</span><span class="sxs-lookup"><span data-stu-id="744a7-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="744a7-114">Способы активации элемента управления Button в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="744a7-114">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="744a7-115">Элемент управления Button</span><span class="sxs-lookup"><span data-stu-id="744a7-115">Button Control</span></span>](button-control-windows-forms.md)
