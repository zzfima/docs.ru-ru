---
title: Практическое руководство. Назначение кнопок отмены в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 8170190145e76a86f5343bc42b39be7fb9d61a0f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344147"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="92105-102">Практическое руководство. Назначение кнопок отмены в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92105-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="92105-103">В любой форме Windows, можно назначить <xref:System.Windows.Forms.Button> отображения элемента управления кнопки "Отмена".</span><span class="sxs-lookup"><span data-stu-id="92105-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="92105-104">Каждый раз, когда пользователь нажимает клавишу ESC, независимо от того, что другой элемент управления в форме имеет фокус, нажатии кнопки "Отмена".</span><span class="sxs-lookup"><span data-stu-id="92105-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="92105-105">Такая кнопка обычно создается, чтобы пользователи могли быстро прервать операцию, не выполняя никаких действий.</span><span class="sxs-lookup"><span data-stu-id="92105-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="92105-106">Чтобы создать кнопку «Отмена»</span><span class="sxs-lookup"><span data-stu-id="92105-106">To designate the cancel button</span></span>  
  
1. <span data-ttu-id="92105-107">Формы задайте <xref:System.Windows.Forms.Form.CancelButton%2A> свойство в соответствующий <xref:System.Windows.Forms.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="92105-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="92105-108">См. также</span><span class="sxs-lookup"><span data-stu-id="92105-108">See also</span></span>

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="92105-109">Общие сведения об элементе управления Button</span><span class="sxs-lookup"><span data-stu-id="92105-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="92105-110">Способы активации элемента управления Button в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92105-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="92105-111">Практическое руководство. Обработка события нажатия кнопки в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92105-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="92105-112">Практическое руководство. Назначение кнопок принятия в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="92105-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [<span data-ttu-id="92105-113">Элемент управления Button</span><span class="sxs-lookup"><span data-stu-id="92105-113">Button Control</span></span>](button-control-windows-forms.md)
