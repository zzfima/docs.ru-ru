---
title: Руководство. Изменение расстояния и выравнивания элементов ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 805fbac5fe33071006f29692d503e5c57eacd765
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746560"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="4dc9b-102">Практическое руководство. Изменение расстояния между элементами и способа их выравнивания для элемента управления ToolStrip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4dc9b-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="4dc9b-103">Элемент управления <xref:System.Windows.Forms.ToolStrip> полностью поддерживает функции макета, такие как изменение размера, расстояния от <xref:System.Windows.Forms.ToolStripItem> элементов управления относительно друг друга, размещение элементов управления в <xref:System.Windows.Forms.ToolStrip>и расстояния от элементов управления относительно <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="4dc9b-104">Так как значение свойства <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> по умолчанию равно `true`, размер элементов управления изменяется автоматически, если только для свойства <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> не установлено значение `false`.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="4dc9b-105">Ручное изменение размера элемента ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="4dc9b-105">To manually size a ToolStripItem</span></span>  
  
1. <span data-ttu-id="4dc9b-106">Задайте для свойства <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> значение `false` для связанного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. <span data-ttu-id="4dc9b-107">Задайте свойство <xref:System.Windows.Forms.ToolStripItem.Size%2A> для связанного <xref:System.Windows.Forms.ToolStripItem>.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="4dc9b-108">Задание расстояния для элемента ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="4dc9b-108">To set the spacing of a ToolStripItem</span></span>  
  
1. <span data-ttu-id="4dc9b-109">Вставьте нужные значения (в пикселях) в свойство <xref:System.Windows.Forms.ToolStripItem.Margin%2A> связанного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="4dc9b-110">Значения свойства <xref:System.Windows.Forms.ToolStripItem.Margin%2A> задают интервал между элементом и соседними элементами в следующем порядке: слева, сверху, справа и снизу.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="4dc9b-111">Выровняйте ToolStripItem с правой стороны ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4dc9b-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1. <span data-ttu-id="4dc9b-112">Задайте для свойства <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> значение <xref:System.Windows.Forms.ToolStripItemAlignment.Right> для связанного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="4dc9b-113">По умолчанию <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> имеет значение <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, которое выровняйте элементы управления по левой стороне <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="4dc9b-114">Упорядочивание элементов ToolStrip на ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4dc9b-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
- <span data-ttu-id="4dc9b-115">Присвойте свойству <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> нужное значение <xref:System.Windows.Forms.ToolStripLayoutStyle>.</span><span class="sxs-lookup"><span data-stu-id="4dc9b-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4dc9b-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4dc9b-116">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="4dc9b-117">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4dc9b-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="4dc9b-118">Архитектура элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4dc9b-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="4dc9b-119">Технологии, положенные в основу работы элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="4dc9b-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
