---
title: Назначение кнопки "принять"
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
ms.openlocfilehash: 1063f649768cac2c866390718b261a21e18ec4d3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743267"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a><span data-ttu-id="cc327-102">Практическое руководство. Создание кнопки принятия в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc327-102">How to: Designate a Windows Forms Button as the Accept Button</span></span>
<span data-ttu-id="cc327-103">В любой форме Windows Forms можно назначить элемент управления <xref:System.Windows.Forms.Button>, который будет кнопкой принять, также известный как кнопка по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cc327-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="cc327-104">Когда пользователь нажимает клавишу ВВОД, нажата кнопка по умолчанию независимо от того, какой элемент управления формы имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="cc327-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc327-105">Исключением является то, что элемент управления с фокусом — это еще одна кнопка — в этом случае будет нажата кнопка с фокусом или многострочное текстовое поле или пользовательский элемент управления, который захватывает клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="cc327-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="cc327-106">Назначение кнопки «принять»</span><span class="sxs-lookup"><span data-stu-id="cc327-106">To designate the accept button</span></span>  
  
1. <span data-ttu-id="cc327-107">Задайте для свойства <xref:System.Windows.Forms.Form.AcceptButton%2A> формы соответствующий элемент управления <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="cc327-107">Set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cc327-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="cc327-108">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="cc327-109">Общие сведения об элементе управления Button</span><span class="sxs-lookup"><span data-stu-id="cc327-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="cc327-110">Способы активации элемента управления Button в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc327-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="cc327-111">Практическое руководство. Обработка события нажатия кнопки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc327-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="cc327-112">Практическое руководство. Создание кнопки отмены в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cc327-112">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [<span data-ttu-id="cc327-113">Элемент управления Button</span><span class="sxs-lookup"><span data-stu-id="cc327-113">Button Control</span></span>](button-control-windows-forms.md)
