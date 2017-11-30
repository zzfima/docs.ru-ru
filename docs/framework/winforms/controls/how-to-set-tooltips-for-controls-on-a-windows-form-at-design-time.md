---
title: "Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки"
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
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 81716be53468242734c3d722eb21e020e58f65ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="af90e-102">Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="af90e-102">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>
<span data-ttu-id="af90e-103">Можно задать <xref:System.Windows.Forms.ToolTip> строки в коде или в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="af90e-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer.</span></span> <span data-ttu-id="af90e-104">Дополнительные сведения о <xref:System.Windows.Forms.ToolTip> компонента, в разделе [Общие сведения о компоненте ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="af90e-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af90e-105">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="af90e-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="af90e-106">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="af90e-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="af90e-107">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="af90e-107">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-a-tooltip-programmatically"></a><span data-ttu-id="af90e-108">Задание всплывающей подсказки программным способом</span><span class="sxs-lookup"><span data-stu-id="af90e-108">To set a ToolTip programmatically</span></span>  
  
1.  <span data-ttu-id="af90e-109">Добавьте элемент управления, который будет отображаться всплывающая подсказка.</span><span class="sxs-lookup"><span data-stu-id="af90e-109">Add the control that will display the ToolTip.</span></span>  
  
2.  <span data-ttu-id="af90e-110">Используйте <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> метод <xref:System.Windows.Forms.ToolTip> компонента.</span><span class="sxs-lookup"><span data-stu-id="af90e-110">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### <a name="to-set-a-tooltip-in-the-designer"></a><span data-ttu-id="af90e-111">Для задания подсказки в конструкторе</span><span class="sxs-lookup"><span data-stu-id="af90e-111">To set a ToolTip in the designer</span></span>  
  
1.  <span data-ttu-id="af90e-112">Добавьте в форму компонент <xref:System.Windows.Forms.ToolTip>.</span><span class="sxs-lookup"><span data-stu-id="af90e-112">Add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>  
  
2.  <span data-ttu-id="af90e-113">Выберите элемент управления, который будет отображаться всплывающая подсказка, или добавьте его в форму.</span><span class="sxs-lookup"><span data-stu-id="af90e-113">Select the control that will display the ToolTip, or add it to the form.</span></span>  
  
3.  <span data-ttu-id="af90e-114">В **свойства** задайте **ToolTip on ToolTip1** значение соответствующую строку текста.</span><span class="sxs-lookup"><span data-stu-id="af90e-114">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af90e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="af90e-115">See Also</span></span>  
 [<span data-ttu-id="af90e-116">Общие сведения об элементе управления ToolTip</span><span class="sxs-lookup"><span data-stu-id="af90e-116">ToolTip Component Overview</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [<span data-ttu-id="af90e-117">Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af90e-117">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)  
 [<span data-ttu-id="af90e-118">Компонент ToolTip</span><span class="sxs-lookup"><span data-stu-id="af90e-118">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
