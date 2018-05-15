---
title: Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: 5b36879413442ff99da034fcbee6bf6388affa6d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a><span data-ttu-id="ddd0e-102">Практическое руководство. Выравнивание элементов управления по границам формы во время выполнения</span><span class="sxs-lookup"><span data-stu-id="ddd0e-102">How to: Align a Control to the Edges of Forms at Design Time</span></span>
<span data-ttu-id="ddd0e-103">Можно сделать элемент управления Выровнять по границе формы, задав <xref:System.Windows.Forms.Control.Dock%2A>.</span><span class="sxs-lookup"><span data-stu-id="ddd0e-103">You can make your control align to the edge of your forms by setting the <xref:System.Windows.Forms.Control.Dock%2A>.</span></span> <span data-ttu-id="ddd0e-104">Это свойство определяет, в каком месте формы будет размещаться элемент управления.</span><span class="sxs-lookup"><span data-stu-id="ddd0e-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="ddd0e-105">Свойство <xref:System.Windows.Forms.Control.Dock%2A> может принимать указанные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="ddd0e-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>  
  
|<span data-ttu-id="ddd0e-106">Параметр</span><span class="sxs-lookup"><span data-stu-id="ddd0e-106">Setting</span></span>|<span data-ttu-id="ddd0e-107">Влияние на элемент управления</span><span class="sxs-lookup"><span data-stu-id="ddd0e-107">Effect on your control</span></span>|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="ddd0e-108">Фиксирует элемент управления у нижнего края формы.</span><span class="sxs-lookup"><span data-stu-id="ddd0e-108">Docks to the bottom of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="ddd0e-109">Заполняет все свободное пространство формы.</span><span class="sxs-lookup"><span data-stu-id="ddd0e-109">Fills all remaining space in the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="ddd0e-110">Фиксирует элемент управления у левого края формы.</span><span class="sxs-lookup"><span data-stu-id="ddd0e-110">Docks to the left side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="ddd0e-111">Не фиксирует элемент нигде, он отображается в месте, указанном в его <xref:System.Windows.Forms.Control.Location%2A>.</span><span class="sxs-lookup"><span data-stu-id="ddd0e-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A>.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="ddd0e-112">Фиксирует элемент управления у правого края формы.</span><span class="sxs-lookup"><span data-stu-id="ddd0e-112">Docks to the right side of the form.</span></span>|  
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="ddd0e-113">Фиксирует элемент управления у верхнего края формы.</span><span class="sxs-lookup"><span data-stu-id="ddd0e-113">Docks to the top of the form.</span></span>|  
  
 <span data-ttu-id="ddd0e-114">Эти значения можно также задать в коде.</span><span class="sxs-lookup"><span data-stu-id="ddd0e-114">These values can also be set in code.</span></span> <span data-ttu-id="ddd0e-115">Дополнительные сведения см. в разделе [как: выравнивание элементов управления на границы формы](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ddd0e-115">For more information, see [How to: Align a Control to the Edges of Forms](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ddd0e-116">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="ddd0e-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ddd0e-117">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="ddd0e-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ddd0e-118">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="ddd0e-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-set-the-dock-property-for-your-control-at-design-time"></a><span data-ttu-id="ddd0e-119">Чтобы задать свойства Dock для элемента управления во время разработки</span><span class="sxs-lookup"><span data-stu-id="ddd0e-119">To set the Dock property for your control at design time</span></span>  
  
1.  <span data-ttu-id="ddd0e-120">В конструкторе Windows Forms выберите элемент управления.</span><span class="sxs-lookup"><span data-stu-id="ddd0e-120">In the Windows Forms Designer, select your control.</span></span>  
  
2.  <span data-ttu-id="ddd0e-121">В **свойства** окно, щелкните раскрывающийся список полю <xref:System.Windows.Forms.Control.Dock%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="ddd0e-121">In the **Properties** window, click the drop-down box next to the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="ddd0e-122">Графический интерфейс с шестью возможными <xref:System.Windows.Forms.Control.Dock%2A> параметров отображается.</span><span class="sxs-lookup"><span data-stu-id="ddd0e-122">A graphical interface representing the six possible <xref:System.Windows.Forms.Control.Dock%2A> settings is displayed.</span></span>  
  
3.  <span data-ttu-id="ddd0e-123">Выберите соответствующий параметр.</span><span class="sxs-lookup"><span data-stu-id="ddd0e-123">Choose the appropriate setting.</span></span>  
  
4.  <span data-ttu-id="ddd0e-124">Элемент управления будет зафиксировано в соответствии с параметр.</span><span class="sxs-lookup"><span data-stu-id="ddd0e-124">Your control will now dock in the manner specified by the setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddd0e-125">См. также</span><span class="sxs-lookup"><span data-stu-id="ddd0e-125">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="ddd0e-126">Практическое руководство. Выравнивание элементов управления по границам формы</span><span class="sxs-lookup"><span data-stu-id="ddd0e-126">How to: Align a Control to the Edges of Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)  
 [<span data-ttu-id="ddd0e-127">Пример. Упорядочение элементов управления в формах Windows Forms с помощью линий привязки</span><span class="sxs-lookup"><span data-stu-id="ddd0e-127">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="ddd0e-128">Практическое руководство. Привязка элементов управления в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ddd0e-128">How to: Anchor Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)  
 [<span data-ttu-id="ddd0e-129">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ddd0e-129">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="ddd0e-130">Практическое руководство. Закрепление дочерних элементов управления в элементе управления FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ddd0e-130">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [<span data-ttu-id="ddd0e-131">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ddd0e-131">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="ddd0e-132">Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="ddd0e-132">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="ddd0e-133">Создание элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="ddd0e-133">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)
