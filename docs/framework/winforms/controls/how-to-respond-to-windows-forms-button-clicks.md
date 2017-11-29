---
title: "Практическое руководство. Обработка события нажатия кнопки в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 923eb7d1b1b5b442ce897619253a958019b239a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a><span data-ttu-id="6f04a-102">Практическое руководство. Обработка события нажатия кнопки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f04a-102">How to: Respond to Windows Forms Button Clicks</span></span>
<span data-ttu-id="6f04a-103">Чаще всего в Windows Forms <xref:System.Windows.Forms.Button> элемент управления должен выполнять определенный код, при нажатии кнопки.</span><span class="sxs-lookup"><span data-stu-id="6f04a-103">The most basic use of a Windows Forms <xref:System.Windows.Forms.Button> control is to run some code when the button is clicked.</span></span>  
  
 <span data-ttu-id="6f04a-104">Щелкнув <xref:System.Windows.Forms.Button> управления также создает ряд других событий, таких как <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, и <xref:System.Windows.Forms.Control.MouseUp> события.</span><span class="sxs-lookup"><span data-stu-id="6f04a-104">Clicking a <xref:System.Windows.Forms.Button> control also generates a number of other events, such as the <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, and <xref:System.Windows.Forms.Control.MouseUp> events.</span></span> <span data-ttu-id="6f04a-105">Если вы собираетесь добавить обработчики событий для этих связанных событий, убедитесь, что их действия не конфликтуют.</span><span class="sxs-lookup"><span data-stu-id="6f04a-105">If you intend to attach event handlers for these related events, be sure that their actions do not conflict.</span></span> <span data-ttu-id="6f04a-106">Например если нажатие кнопки удаляет данные, данные, введенные пользователем в текстовое поле, при наведении указателя мыши на кнопку не должно отображать подсказки с несуществующими сведениями.</span><span class="sxs-lookup"><span data-stu-id="6f04a-106">For example, if clicking the button clears information that the user has typed in a text box, pausing the mouse pointer over the button should not display a tool tip with that now-nonexistent information.</span></span>  
  
 <span data-ttu-id="6f04a-107">Если пользователь пытается дважды щелкните <xref:System.Windows.Forms.Button> элемента управления, каждый щелчок будет обрабатываться отдельно; то есть элемент управления не поддерживает событие двойного щелчка.</span><span class="sxs-lookup"><span data-stu-id="6f04a-107">If the user attempts to double-click the <xref:System.Windows.Forms.Button> control, each click will be processed separately; that is, the control does not support the double-click event.</span></span>  
  
### <a name="to-respond-to-a-button-click"></a><span data-ttu-id="6f04a-108">Ответ на нажатие кнопки</span><span class="sxs-lookup"><span data-stu-id="6f04a-108">To respond to a button click</span></span>  
  
-   <span data-ttu-id="6f04a-109">На кнопке панели `Click` <xref:System.EventHandler> написать код для выполнения.</span><span class="sxs-lookup"><span data-stu-id="6f04a-109">In the button's `Click` <xref:System.EventHandler> write the code to run.</span></span> <span data-ttu-id="6f04a-110">`Button1_Click`должен быть привязан к элементу управления.</span><span class="sxs-lookup"><span data-stu-id="6f04a-110">`Button1_Click` must be bound to the control.</span></span> <span data-ttu-id="6f04a-111">Дополнительные сведения см. в разделе [как: Создание обработчиков событий в запуска времени для Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6f04a-111">For more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6f04a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="6f04a-112">See Also</span></span>  
 [<span data-ttu-id="6f04a-113">Общие сведения об элементе управления Button</span><span class="sxs-lookup"><span data-stu-id="6f04a-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="6f04a-114">Способы активации элемента управления Button в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f04a-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="6f04a-115">Элемент управления Button</span><span class="sxs-lookup"><span data-stu-id="6f04a-115">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
