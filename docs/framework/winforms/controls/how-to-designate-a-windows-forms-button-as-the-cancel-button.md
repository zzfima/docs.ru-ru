---
title: Назначить кнопку кнопкой "Отмена"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 123b3e275065efadd24815320ea7d855808e60b9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743258"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="b409a-102">Практическое руководство. Создание кнопки отмены в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b409a-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="b409a-103">В любой форме Windows Forms можно назначить элемент управления <xref:System.Windows.Forms.Button> в качестве кнопки отмены.</span><span class="sxs-lookup"><span data-stu-id="b409a-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="b409a-104">Нажатие кнопки «отмена» происходит каждый раз, когда пользователь нажимает клавишу ESC, независимо от того, какой элемент управления формы имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="b409a-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="b409a-105">Такая кнопка обычно запрограммирована, позволяя пользователю быстро выйти из операции без фиксации каких-либо действий.</span><span class="sxs-lookup"><span data-stu-id="b409a-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="b409a-106">Назначение кнопки «Отмена»</span><span class="sxs-lookup"><span data-stu-id="b409a-106">To designate the cancel button</span></span>  
  
1. <span data-ttu-id="b409a-107">Задайте для свойства <xref:System.Windows.Forms.Form.CancelButton%2A> формы соответствующий элемент управления <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="b409a-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b409a-108">См. также:</span><span class="sxs-lookup"><span data-stu-id="b409a-108">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="b409a-109">Общие сведения об элементе управления Button</span><span class="sxs-lookup"><span data-stu-id="b409a-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="b409a-110">Способы активации элемента управления Button в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b409a-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="b409a-111">Практическое руководство. Обработка события нажатия кнопки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b409a-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="b409a-112">Практическое руководство. Создание кнопки принятия в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b409a-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [<span data-ttu-id="b409a-113">Элемент управления Button</span><span class="sxs-lookup"><span data-stu-id="b409a-113">Button Control</span></span>](button-control-windows-forms.md)
