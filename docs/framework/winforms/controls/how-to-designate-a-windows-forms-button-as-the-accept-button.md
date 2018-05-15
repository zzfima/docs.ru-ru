---
title: Практическое руководство. Назначение кнопок принятия в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
ms.openlocfilehash: a69964b83e9948a844483725616a150234a38c97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a><span data-ttu-id="6a96b-102">Практическое руководство. Назначение кнопок принятия в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6a96b-102">How to: Designate a Windows Forms Button as the Accept Button</span></span>
<span data-ttu-id="6a96b-103">В любой форме Windows Forms можно назначить <xref:System.Windows.Forms.Button> отображения элемента управления «принять», также известные как кнопка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6a96b-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="6a96b-104">Каждый раз, когда пользователь нажимает клавишу ВВОД, нажатии кнопки по умолчанию независимо от других элементов управления в форме имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="6a96b-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6a96b-105">Исключение составляют при другой кнопки элемента управления с фокусом — в этом случае будет нажата кнопка с фокусом, многострочное текстовое поле, или пользовательский элемент управления, который перехватывает клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="6a96b-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="6a96b-106">Чтобы создать кнопку «принять»</span><span class="sxs-lookup"><span data-stu-id="6a96b-106">To designate the accept button</span></span>  
  
1.  <span data-ttu-id="6a96b-107">Формы задайте <xref:System.Windows.Forms.Form.AcceptButton%2A> свойство к соответствующему <xref:System.Windows.Forms.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6a96b-107">Set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn   
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6a96b-108">См. также</span><span class="sxs-lookup"><span data-stu-id="6a96b-108">See Also</span></span>  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [<span data-ttu-id="6a96b-109">Общие сведения об элементе управления Button</span><span class="sxs-lookup"><span data-stu-id="6a96b-109">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="6a96b-110">Способы активации элемента управления Button в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6a96b-110">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="6a96b-111">Практическое руководство. Обработка события нажатия кнопки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6a96b-111">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="6a96b-112">Практическое руководство. Создание кнопки отмены в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6a96b-112">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-cancel-button.md)  
 [<span data-ttu-id="6a96b-113">Элемент управления Button</span><span class="sxs-lookup"><span data-stu-id="6a96b-113">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
