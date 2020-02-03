---
title: Изменение задержки компонента ToolTip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: 8ab0b0760e8c82d752eaada19f14cae57fa63fdc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746592"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a><span data-ttu-id="76461-102">Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="76461-102">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>
<span data-ttu-id="76461-103">Для компонента Windows Forms <xref:System.Windows.Forms.ToolTip> можно задать несколько значений задержки.</span><span class="sxs-lookup"><span data-stu-id="76461-103">There are multiple delay values that you can set for a Windows Forms <xref:System.Windows.Forms.ToolTip> component.</span></span> <span data-ttu-id="76461-104">Единицей измерения для всех этих свойств является миллисекунда.</span><span class="sxs-lookup"><span data-stu-id="76461-104">The unit of measure for all these properties is milliseconds.</span></span> <span data-ttu-id="76461-105">Свойство <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> определяет, как долго пользователь должен указывать на соответствующий элемент управления для отображения строки подсказки.</span><span class="sxs-lookup"><span data-stu-id="76461-105">The <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> property determines how long the user must point at the associated control for the ToolTip string to appear.</span></span> <span data-ttu-id="76461-106">Свойство <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> задает число миллисекунд, необходимое для отображения последующих строк подсказки при перемещении мыши из одного связанного элемента управления ToolTip в другой.</span><span class="sxs-lookup"><span data-stu-id="76461-106">The <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> property sets the number of milliseconds it takes for subsequent ToolTip strings to appear as the mouse moves from one ToolTip-associated control to another.</span></span> <span data-ttu-id="76461-107">Свойство <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> определяет продолжительность отображения строки подсказки.</span><span class="sxs-lookup"><span data-stu-id="76461-107">The <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> property determines the length of time the ToolTip string is shown.</span></span> <span data-ttu-id="76461-108">Эти значения можно задать по отдельности или задав значение свойства <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>. другие свойства задержки задаются на основе значения, присвоенного свойству <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>.</span><span class="sxs-lookup"><span data-stu-id="76461-108">You can set these values individually, or by setting the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property; the other delay properties are set based on the value assigned to the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property.</span></span> <span data-ttu-id="76461-109">Например, если для <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> задано значение N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> имеет значение N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> устанавливается равным значению <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, деленному на 5 (или N/5), а <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> устанавливается в значение, которое в пять раз превышает значение свойства <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> (или менее 5N).</span><span class="sxs-lookup"><span data-stu-id="76461-109">For example, when <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> is set to a value N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> is set to N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> is set to the value of <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> divided by five (or N/5), and <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> is set to a value that is five times the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property (or 5N).</span></span>  
  
### <a name="to-set-the-delay"></a><span data-ttu-id="76461-110">Установка задержки</span><span class="sxs-lookup"><span data-stu-id="76461-110">To set the delay</span></span>  
  
1. <span data-ttu-id="76461-111">Задайте следующие свойства, как показано в этом примере.</span><span class="sxs-lookup"><span data-stu-id="76461-111">Set the following properties as shown in this example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="76461-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="76461-112">See also</span></span>

- [<span data-ttu-id="76461-113">Общие сведения об элементе управления ToolTip</span><span class="sxs-lookup"><span data-stu-id="76461-113">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="76461-114">Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="76461-114">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [<span data-ttu-id="76461-115">Компонент ToolTip</span><span class="sxs-lookup"><span data-stu-id="76461-115">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
