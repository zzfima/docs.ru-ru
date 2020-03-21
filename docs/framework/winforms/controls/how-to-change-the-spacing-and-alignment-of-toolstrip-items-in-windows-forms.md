---
title: 'Как: Изменить интервал и выравнивание элементов ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 550ac1660a077e8d766a01bfa8d102c07f0fbfeb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182230"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="7898f-102">Практическое руководство. Изменение расстояния между элементами и способа их выравнивания для элемента управления ToolStrip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7898f-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="7898f-103">Элемент <xref:System.Windows.Forms.ToolStrip> управления полностью поддерживает функции компоновки, такие как размер, расстояние <xref:System.Windows.Forms.ToolStripItem> <xref:System.Windows.Forms.ToolStrip>элементов управления относительно друг друга, <xref:System.Windows.Forms.ToolStrip>расположение элементов управления на , и расстояние элементов управления по отношению к .</span><span class="sxs-lookup"><span data-stu-id="7898f-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="7898f-104">Поскольку <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> значение свойства по `true`умолчанию является, элементы <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> управления `false`размерируются автоматически, если вы не установите свойство.</span><span class="sxs-lookup"><span data-stu-id="7898f-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="7898f-105">Вручную размер ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="7898f-105">To manually size a ToolStripItem</span></span>  
  
1. <span data-ttu-id="7898f-106">Установите <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> свойство `false` для связанного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7898f-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. <span data-ttu-id="7898f-107">Установите <xref:System.Windows.Forms.ToolStripItem.Size%2A> свойство так, как <xref:System.Windows.Forms.ToolStripItem>вы хотите для связанных.</span><span class="sxs-lookup"><span data-stu-id="7898f-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="7898f-108">Установить интервал ы от ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="7898f-108">To set the spacing of a ToolStripItem</span></span>  
  
1. <span data-ttu-id="7898f-109">Вставьте желаемые значения в пиксели в свойство <xref:System.Windows.Forms.ToolStripItem.Margin%2A> связанного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7898f-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="7898f-110">Значения <xref:System.Windows.Forms.ToolStripItem.Margin%2A> свойства указывают расстояние между элементом и соседними элементами в этом порядке: левый, верхний, правый и нижний.</span><span class="sxs-lookup"><span data-stu-id="7898f-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="7898f-111">Для выравнивания ToolStripItem в правую сторону ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7898f-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1. <span data-ttu-id="7898f-112">Установите <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> свойство <xref:System.Windows.Forms.ToolStripItemAlignment.Right> для связанного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7898f-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="7898f-113">По умолчанию, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> <xref:System.Windows.Forms.ToolStripItemAlignment.Left>устанавливается, который выравнивает элементы <xref:System.Windows.Forms.ToolStrip>управления в левую сторону .</span><span class="sxs-lookup"><span data-stu-id="7898f-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="7898f-114">Для организации элементов ToolStrip на ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7898f-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
- <span data-ttu-id="7898f-115">Установите <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> свойство на <xref:System.Windows.Forms.ToolStripLayoutStyle> стоимость, что вы хотите.</span><span class="sxs-lookup"><span data-stu-id="7898f-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7898f-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7898f-116">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="7898f-117">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7898f-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="7898f-118">Архитектура элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7898f-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="7898f-119">Технологии, положенные в основу работы элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7898f-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
