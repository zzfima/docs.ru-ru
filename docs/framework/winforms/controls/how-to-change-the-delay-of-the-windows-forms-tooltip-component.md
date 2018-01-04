---
title: "Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms"
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
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8506df062729a98adc1aa1e0dcb524aa4ec812c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a><span data-ttu-id="9f68b-102">Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f68b-102">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>
<span data-ttu-id="9f68b-103">Существует несколько значений задержек, которые можно задать для Windows Forms <xref:System.Windows.Forms.ToolTip> компонента.</span><span class="sxs-lookup"><span data-stu-id="9f68b-103">There are multiple delay values that you can set for a Windows Forms <xref:System.Windows.Forms.ToolTip> component.</span></span> <span data-ttu-id="9f68b-104">Единицы измерения для этих свойств — миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="9f68b-104">The unit of measure for all these properties is milliseconds.</span></span> <span data-ttu-id="9f68b-105"><xref:System.Windows.Forms.ToolTip.InitialDelay%2A> Свойство определяет, как долго пользователь должен указывать на элементом управления, чтобы появилась строка ToolTip.</span><span class="sxs-lookup"><span data-stu-id="9f68b-105">The <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> property determines how long the user must point at the associated control for the ToolTip string to appear.</span></span> <span data-ttu-id="9f68b-106"><xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> Свойство задает время в миллисекундах, затрачиваемое строки ToolTip отображаться при перемещении мыши с одного элемента управления связанный всплывающей подсказки в другую.</span><span class="sxs-lookup"><span data-stu-id="9f68b-106">The <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> property sets the number of milliseconds it takes for subsequent ToolTip strings to appear as the mouse moves from one ToolTip-associated control to another.</span></span> <span data-ttu-id="9f68b-107"><xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> Свойство определяет время строки всплывающей подсказки.</span><span class="sxs-lookup"><span data-stu-id="9f68b-107">The <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> property determines the length of time the ToolTip string is shown.</span></span> <span data-ttu-id="9f68b-108">Эти значения можно задать по отдельности или установив значение <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> свойство; другие свойства задаются с учетом на значение, присваиваемое задержка <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="9f68b-108">You can set these values individually, or by setting the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property; the other delay properties are set based on the value assigned to the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property.</span></span> <span data-ttu-id="9f68b-109">Например, если <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> присваивается значение N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> равно N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> присвоено значение <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> деленное на пять (или N-5), и <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> присвоено значение, которое является пять раз значение <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> свойства (5N).</span><span class="sxs-lookup"><span data-stu-id="9f68b-109">For example, when <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> is set to a value N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> is set to N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> is set to the value of <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> divided by five (or N/5), and <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> is set to a value that is five times the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property (or 5N).</span></span>  
  
### <a name="to-set-the-delay"></a><span data-ttu-id="9f68b-110">Чтобы задать значение задержки</span><span class="sxs-lookup"><span data-stu-id="9f68b-110">To set the delay</span></span>  
  
1.  <span data-ttu-id="9f68b-111">Задайте следующие свойства, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9f68b-111">Set the following properties as shown in this example.</span></span>  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9f68b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9f68b-112">See Also</span></span>  
 [<span data-ttu-id="9f68b-113">Общие сведения об элементе управления ToolTip</span><span class="sxs-lookup"><span data-stu-id="9f68b-113">ToolTip Component Overview</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [<span data-ttu-id="9f68b-114">Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="9f68b-114">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [<span data-ttu-id="9f68b-115">Компонент ToolTip</span><span class="sxs-lookup"><span data-stu-id="9f68b-115">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
