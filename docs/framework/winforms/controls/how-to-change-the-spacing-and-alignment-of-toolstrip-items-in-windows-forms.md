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
ms.openlocfilehash: bed943466348447e30947c170e27027f324342c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59323178"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="be4e4-102">Практическое руководство. Изменение расстояния между элементами и способа их выравнивания для элемента управления ToolStrip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="be4e4-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="be4e4-103"><xref:System.Windows.Forms.ToolStrip> Управления полностью поддерживает функции макета, такие как определения размера, расстояние между <xref:System.Windows.Forms.ToolStripItem> элементов управления относительно друг друга, размещения элементов управления в <xref:System.Windows.Forms.ToolStrip>и расстояние между элементами управления <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="be4e4-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="be4e4-104">Так как значение по умолчанию <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> свойство `true`, элементов управления изменяются автоматически, если не задать <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="be4e4-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="be4e4-105">Чтобы вручную размер ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="be4e4-105">To manually size a ToolStripItem</span></span>  
  
1. <span data-ttu-id="be4e4-106">Задайте <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> свойства `false` для сопоставленного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="be4e4-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. <span data-ttu-id="be4e4-107">Задайте <xref:System.Windows.Forms.ToolStripItem.Size%2A> свойства, как нужно для связанного <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="be4e4-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="be4e4-108">Чтобы задать расстояние между ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="be4e4-108">To set the spacing of a ToolStripItem</span></span>  
  
1. <span data-ttu-id="be4e4-109">Вставьте нужные значения в пикселях <xref:System.Windows.Forms.ToolStripItem.Margin%2A> свойства сопоставленного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="be4e4-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="be4e4-110">Значения <xref:System.Windows.Forms.ToolStripItem.Margin%2A> свойства укажите расстояние между элементом и соседними элементами в следующем порядке: Слева, сверху, справа и нижней.</span><span class="sxs-lookup"><span data-stu-id="be4e4-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="be4e4-111">Чтобы выровнять ToolStripItem в правой части панели инструментов</span><span class="sxs-lookup"><span data-stu-id="be4e4-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1. <span data-ttu-id="be4e4-112">Задайте <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> свойства <xref:System.Windows.Forms.ToolStripItemAlignment.Right> для сопоставленного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="be4e4-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="be4e4-113">По умолчанию <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> присваивается <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, который элементы управления выравниваются по левому краю <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="be4e4-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="be4e4-114">Чтобы упорядочить элементы ToolStrip на панели инструментов</span><span class="sxs-lookup"><span data-stu-id="be4e4-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
-   <span data-ttu-id="be4e4-115">Задайте <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> свойства к значению <xref:System.Windows.Forms.ToolStripLayoutStyle> нужную.</span><span class="sxs-lookup"><span data-stu-id="be4e4-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="be4e4-116">См. также</span><span class="sxs-lookup"><span data-stu-id="be4e4-116">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="be4e4-117">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="be4e4-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="be4e4-118">Архитектура элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="be4e4-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="be4e4-119">Технологии, положенные в основу работы элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="be4e4-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
