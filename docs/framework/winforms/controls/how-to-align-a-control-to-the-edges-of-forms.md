---
title: Практическое руководство. Выравнивание элементов управления по границам формы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock property [Windows Forms], aligning controls (using code)
- forms [Windows Forms], aligning controls
- controls [Windows Forms], aligning on forms
- custom controls [Windows Forms], docking using code
ms.assetid: 5994cb59-242b-4e75-bd0e-62879c34d702
ms.openlocfilehash: beb8881dbd2aedaefe66510c2942ce6c082b9729
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59329977"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms"></a><span data-ttu-id="937ea-102">Практическое руководство. Выравнивание элементов управления по границам формы</span><span class="sxs-lookup"><span data-stu-id="937ea-102">How to: Align a Control to the Edges of Forms</span></span>
<span data-ttu-id="937ea-103">Элемент управления можно выровнять по границе формы с помощью свойства <xref:System.Windows.Forms.Control.Dock%2A>.</span><span class="sxs-lookup"><span data-stu-id="937ea-103">You can make your control align to the edge of your forms by setting the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span> <span data-ttu-id="937ea-104">Это свойство определяет, в каком месте формы будет размещаться элемент управления.</span><span class="sxs-lookup"><span data-stu-id="937ea-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="937ea-105">Свойство <xref:System.Windows.Forms.Control.Dock%2A> может принимать указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="937ea-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>  
  
|<span data-ttu-id="937ea-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="937ea-106">Setting</span></span>|<span data-ttu-id="937ea-107">Влияние на элемент управления</span><span class="sxs-lookup"><span data-stu-id="937ea-107">Effect on your control</span></span>|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="937ea-108">Фиксирует элемент управления у нижнего края формы.</span><span class="sxs-lookup"><span data-stu-id="937ea-108">Docks to the bottom of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="937ea-109">Заполняет все свободное пространство формы.</span><span class="sxs-lookup"><span data-stu-id="937ea-109">Fills all remaining space in the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="937ea-110">Фиксирует элемент управления у левого края формы.</span><span class="sxs-lookup"><span data-stu-id="937ea-110">Docks to the left side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="937ea-111">Не фиксирует элемент нигде; он отображается в месте, указанном в свойстве <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="937ea-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="937ea-112">Фиксирует элемент управления у правого края формы.</span><span class="sxs-lookup"><span data-stu-id="937ea-112">Docks to the right side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="937ea-113">Фиксирует элемент управления у верхнего края формы.</span><span class="sxs-lookup"><span data-stu-id="937ea-113">Docks to the top of the form.</span></span>|  
  
 <span data-ttu-id="937ea-114">Эта возможность поддерживается во время разработки в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="937ea-114">There is design-time support for this feature in Visual Studio.</span></span>  
  
### <a name="to-set-the-dock-property-for-your-control-at-run-time"></a><span data-ttu-id="937ea-115">Задание свойства Dock для элемента управления во время выполнения</span><span class="sxs-lookup"><span data-stu-id="937ea-115">To set the Dock property for your control at run time</span></span>  
  
1. <span data-ttu-id="937ea-116">Присвойте свойству <xref:System.Windows.Forms.Control.Dock%2A> соответствующее значение в коде.</span><span class="sxs-lookup"><span data-stu-id="937ea-116">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to the appropriate value in code.</span></span>  
  
    ```vb  
    ' To set the Dock property internally.  
    Me.Dock = DockStyle.Top  
    ' To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top  
    ```  
  
    ```csharp  
    // To set the Dock property internally.  
    this.Dock = DockStyle.Top;  
    // To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="937ea-117">См. также</span><span class="sxs-lookup"><span data-stu-id="937ea-117">See also</span></span>

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [<span data-ttu-id="937ea-118">Разработка пользовательских элементов управления Windows Forms в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="937ea-118">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="937ea-119">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="937ea-119">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="937ea-120">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="937ea-120">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="937ea-121">Свойство AutoSize</span><span class="sxs-lookup"><span data-stu-id="937ea-121">AutoSize Property Overview</span></span>](autosize-property-overview.md)
