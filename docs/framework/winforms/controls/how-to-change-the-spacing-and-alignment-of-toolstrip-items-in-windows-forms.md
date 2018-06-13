---
title: Практическое руководство. Изменение расстояния между элементами и способа их выравнивания для элемента управления ToolStrip в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 7951a545fd8cbd0ae30907922551216161171a8d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531268"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="9a418-102">Практическое руководство. Изменение расстояния между элементами и способа их выравнивания для элемента управления ToolStrip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9a418-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="9a418-103"><xref:System.Windows.Forms.ToolStrip> Управления полностью поддерживает возможности макета, такие как изменение размера, расстояние между <xref:System.Windows.Forms.ToolStripItem> элементов управления относительно друг друга, размещение элементов управления в <xref:System.Windows.Forms.ToolStrip>и интервалы между элементами управления <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="9a418-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="9a418-104">Так как значение по умолчанию <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> свойство `true`, элементов управления изменяются автоматически, если не задать <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="9a418-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="9a418-105">Чтобы вручную указать значения на элемент ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="9a418-105">To manually size a ToolStripItem</span></span>  
  
1.  <span data-ttu-id="9a418-106">Задать <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> свойства `false` для связанного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9a418-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2.  <span data-ttu-id="9a418-107">Задать <xref:System.Windows.Forms.ToolStripItem.Size%2A> нужным образом для связанного свойства <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="9a418-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="9a418-108">Чтобы задать интервал ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="9a418-108">To set the spacing of a ToolStripItem</span></span>  
  
1.  <span data-ttu-id="9a418-109">Вставьте нужные значения в пикселях <xref:System.Windows.Forms.ToolStripItem.Margin%2A> свойств связанного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9a418-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="9a418-110">Значения <xref:System.Windows.Forms.ToolStripItem.Margin%2A> свойства задайте интервал между элементом и соседними элементами в следующем порядке: слева, сверху, справа и нижней.</span><span class="sxs-lookup"><span data-stu-id="9a418-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="9a418-111">Чтобы выровнять ToolStripItem правую сторону элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9a418-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1.  <span data-ttu-id="9a418-112">Задать <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> свойства <xref:System.Windows.Forms.ToolStripItemAlignment.Right> для связанного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9a418-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="9a418-113">По умолчанию <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> равно <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, что элементы управления выравниваются по левому краю <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="9a418-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="9a418-114">Чтобы упорядочить элементы ToolStrip на панели инструментов</span><span class="sxs-lookup"><span data-stu-id="9a418-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
-   <span data-ttu-id="9a418-115">Задать <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> значение из свойства <xref:System.Windows.Forms.ToolStripLayoutStyle> нужного.</span><span class="sxs-lookup"><span data-stu-id="9a418-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9a418-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9a418-116">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.Control.Layout>  
 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>  
 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>  
 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Placement%2A>  
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>  
 [<span data-ttu-id="9a418-117">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9a418-117">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="9a418-118">Архитектура элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9a418-118">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="9a418-119">Технологии, положенные в основу работы элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="9a418-119">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
