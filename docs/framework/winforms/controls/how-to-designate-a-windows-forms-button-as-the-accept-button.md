---
title: Обозначите кнопку как кнопку «Принять»
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
ms.openlocfilehash: ca5f691fb26db5c4adcb48405c9600b54827104c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142151"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a><span data-ttu-id="e0855-102">Практическое руководство. Назначение кнопок принятия в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0855-102">How to: Designate a Windows Forms Button as the Accept Button</span></span>
<span data-ttu-id="e0855-103">В любой форме Windows <xref:System.Windows.Forms.Button> можно назначить элемент управления как кнопку «принять», также известную как кнопка «По умолчанию».</span><span class="sxs-lookup"><span data-stu-id="e0855-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="e0855-104">Всякий раз, когда пользователь нажимает на ключ ENTER, кнопка по умолчанию нажимается независимо от того, какой другой элемент управления в форме имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="e0855-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0855-105">Исключением является, когда управление с фокусом является еще одной кнопкой - в этом случае, кнопка с фокусом будет нажата - или многолинейный текстовый ящик, или пользовательский контроль, который ловушки enter ключ.</span><span class="sxs-lookup"><span data-stu-id="e0855-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="e0855-106">Обозначить кнопку «Принять»</span><span class="sxs-lookup"><span data-stu-id="e0855-106">To designate the accept button</span></span>  
  
1. <span data-ttu-id="e0855-107">Установите свойство <xref:System.Windows.Forms.Form.AcceptButton%2A> формы на <xref:System.Windows.Forms.Button> соответствующий контроль.</span><span class="sxs-lookup"><span data-stu-id="e0855-107">Set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e0855-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e0855-108">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="e0855-109">Общие сведения об элементе управления Button</span><span class="sxs-lookup"><span data-stu-id="e0855-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="e0855-110">Способы активации элемента управления Button в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0855-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="e0855-111">Практическое руководство. Обработка события нажатия кнопки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0855-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="e0855-112">Практическое руководство. Создание кнопки "Отмена" в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0855-112">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [<span data-ttu-id="e0855-113">Элемент управления Button</span><span class="sxs-lookup"><span data-stu-id="e0855-113">Button Control</span></span>](button-control-windows-forms.md)
