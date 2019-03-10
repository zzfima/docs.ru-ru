---
title: Практическое руководство. Изменение внешнего вида элемента управления ToolStrip текста и изображений в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], appearance
- toolbars [Windows Forms], images
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], appearance
- ToolStrip control [Windows Forms], images
- ToolStrip control [Windows Forms], text
- toolbars [Windows Forms], text
ms.assetid: d62dc9d1-2edd-4dfa-aed7-1335d6e13d86
ms.openlocfilehash: cd15e581e646f53ed56af654917c7543bf18617e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705406"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a><span data-ttu-id="a1257-102">Практическое руководство. Изменение внешнего вида элемента управления ToolStrip текста и изображений в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a1257-102">How to: Change the Appearance of ToolStrip Text and Images in Windows Forms</span></span>
<span data-ttu-id="a1257-103">Можно управлять, отображаются ли текст и изображения на <xref:System.Windows.Forms.ToolStripItem> и как они выравниваются относительно друг друга и <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="a1257-103">You can control whether text and images are displayed on a <xref:System.Windows.Forms.ToolStripItem> and how they are aligned relative to each other and the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a><span data-ttu-id="a1257-104">Чтобы определить, отображаемые на ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="a1257-104">To define what is displayed on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="a1257-105">Задайте <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> свойство нужное значение.</span><span class="sxs-lookup"><span data-stu-id="a1257-105">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to the desired value.</span></span> <span data-ttu-id="a1257-106">Возможные значения — `Image`, `ImageAndText`, `None`, и `Text`.</span><span class="sxs-lookup"><span data-stu-id="a1257-106">The possibilities are `Image`, `ImageAndText`, `None`, and `Text`.</span></span> <span data-ttu-id="a1257-107">Значение по умолчанию — `ImageAndText`.</span><span class="sxs-lookup"><span data-stu-id="a1257-107">The default is `ImageAndText`.</span></span>  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a><span data-ttu-id="a1257-108">Для выравнивания текста на ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="a1257-108">To align text on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="a1257-109">Задайте <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> свойство нужное значение.</span><span class="sxs-lookup"><span data-stu-id="a1257-109">Set the <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> property to the desired value.</span></span> <span data-ttu-id="a1257-110">Возможные значения — любое сочетание сверху "," Средний "и" нижний left, center и right.</span><span class="sxs-lookup"><span data-stu-id="a1257-110">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="a1257-111">Значение по умолчанию — `MiddleCenter`.</span><span class="sxs-lookup"><span data-stu-id="a1257-111">The default is `MiddleCenter`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a><span data-ttu-id="a1257-112">Чтобы выровнять изображение на ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="a1257-112">To align an image on a ToolStripItem</span></span>  
  
-   <span data-ttu-id="a1257-113">Задайте <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> свойство нужное значение.</span><span class="sxs-lookup"><span data-stu-id="a1257-113">Set the <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> property to the desired value.</span></span> <span data-ttu-id="a1257-114">Возможные значения — любое сочетание сверху "," Средний "и" нижний left, center и right.</span><span class="sxs-lookup"><span data-stu-id="a1257-114">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="a1257-115">Значение по умолчанию — `MiddleLeft`.</span><span class="sxs-lookup"><span data-stu-id="a1257-115">The default is `MiddleLeft`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a><span data-ttu-id="a1257-116">Чтобы определить способ отображения выравниванием текста и изображения относительно друг друга</span><span class="sxs-lookup"><span data-stu-id="a1257-116">To define how ToolStripItem text and images are displayed relative to each other</span></span>  
  
-   <span data-ttu-id="a1257-117">Задайте <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> свойство нужное значение.</span><span class="sxs-lookup"><span data-stu-id="a1257-117">Set the <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> property to the desired value.</span></span> <span data-ttu-id="a1257-118">Возможные значения — `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, и `TextBeforeImage`.</span><span class="sxs-lookup"><span data-stu-id="a1257-118">The possibilities are `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, and `TextBeforeImage`.</span></span> <span data-ttu-id="a1257-119">Значение по умолчанию — `ImageBeforeText`.</span><span class="sxs-lookup"><span data-stu-id="a1257-119">The default is `ImageBeforeText`.</span></span>  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a1257-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a1257-120">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="a1257-121">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="a1257-121">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="a1257-122">Архитектура элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="a1257-122">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="a1257-123">Технологии, положенные в основу работы элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="a1257-123">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
