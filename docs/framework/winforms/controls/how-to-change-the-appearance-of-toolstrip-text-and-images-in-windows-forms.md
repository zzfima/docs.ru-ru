---
title: Практическое руководство. Изменение внешнего вида текста и изображений элемента управления ToolStrip в Windows Forms
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
ms.openlocfilehash: cf2f332b17bf6ff5b6ffb7cbc2d5777649728ec6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650845"
---
# <a name="how-to-change-the-appearance-of-toolstrip-text-and-images-in-windows-forms"></a><span data-ttu-id="f6259-102">Практическое руководство. Изменение внешнего вида текста и изображений элемента управления ToolStrip в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f6259-102">How to: Change the Appearance of ToolStrip Text and Images in Windows Forms</span></span>
<span data-ttu-id="f6259-103">Можно управлять, отображаются ли текст и изображения на <xref:System.Windows.Forms.ToolStripItem> и как они выравниваются относительно друг друга и <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="f6259-103">You can control whether text and images are displayed on a <xref:System.Windows.Forms.ToolStripItem> and how they are aligned relative to each other and the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-define-what-is-displayed-on-a-toolstripitem"></a><span data-ttu-id="f6259-104">Чтобы определить, отображаемые на ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="f6259-104">To define what is displayed on a ToolStripItem</span></span>  
  
- <span data-ttu-id="f6259-105">Задайте <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> свойство нужное значение.</span><span class="sxs-lookup"><span data-stu-id="f6259-105">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to the desired value.</span></span> <span data-ttu-id="f6259-106">Возможные значения — `Image`, `ImageAndText`, `None`, и `Text`.</span><span class="sxs-lookup"><span data-stu-id="f6259-106">The possibilities are `Image`, `ImageAndText`, `None`, and `Text`.</span></span> <span data-ttu-id="f6259-107">Значение по умолчанию — `ImageAndText`.</span><span class="sxs-lookup"><span data-stu-id="f6259-107">The default is `ImageAndText`.</span></span>  
  
    ```vb  
    ToolStripButton2.DisplayStyle = _  
        System.Windows.Forms.ToolStripItemDisplayStyle.Image  
    ```  
  
    ```csharp  
    toolStripButton2.DisplayStyle = System.Windows.Forms.ToolStripItemDisplayStyle.Image;  
    ```  
  
### <a name="to-align-text-on-a-toolstripitem"></a><span data-ttu-id="f6259-108">Для выравнивания текста на ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="f6259-108">To align text on a ToolStripItem</span></span>  
  
- <span data-ttu-id="f6259-109">Задайте <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> свойство нужное значение.</span><span class="sxs-lookup"><span data-stu-id="f6259-109">Set the <xref:System.Windows.Forms.ToolStripItem.TextAlign%2A> property to the desired value.</span></span> <span data-ttu-id="f6259-110">Возможные значения — любое сочетание сверху "," Средний "и" нижний left, center и right.</span><span class="sxs-lookup"><span data-stu-id="f6259-110">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="f6259-111">Значение по умолчанию — `MiddleCenter`.</span><span class="sxs-lookup"><span data-stu-id="f6259-111">The default is `MiddleCenter`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.TextAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.TextAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-align-an-image-on-a-toolstripitem"></a><span data-ttu-id="f6259-112">Чтобы выровнять изображение на ToolStripItem</span><span class="sxs-lookup"><span data-stu-id="f6259-112">To align an image on a ToolStripItem</span></span>  
  
- <span data-ttu-id="f6259-113">Задайте <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> свойство нужное значение.</span><span class="sxs-lookup"><span data-stu-id="f6259-113">Set the <xref:System.Windows.Forms.ToolStripItem.ImageAlign%2A> property to the desired value.</span></span> <span data-ttu-id="f6259-114">Возможные значения — любое сочетание сверху "," Средний "и" нижний left, center и right.</span><span class="sxs-lookup"><span data-stu-id="f6259-114">The possibilities are any combination of top, middle, and bottom with left, center, and right.</span></span> <span data-ttu-id="f6259-115">Значение по умолчанию — `MiddleLeft`.</span><span class="sxs-lookup"><span data-stu-id="f6259-115">The default is `MiddleLeft`.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.ImageAlign = _  
        System.Drawing.ContentAlignment.MiddleRight  
    ```  
  
    ```csharp  
    toolStripSplitButton1.ImageAlign = System.Drawing.ContentAlignment.MiddleRight;  
    ```  
  
### <a name="to-define-how-toolstripitem-text-and-images-are-displayed-relative-to-each-other"></a><span data-ttu-id="f6259-116">Чтобы определить способ отображения выравниванием текста и изображения относительно друг друга</span><span class="sxs-lookup"><span data-stu-id="f6259-116">To define how ToolStripItem text and images are displayed relative to each other</span></span>  
  
- <span data-ttu-id="f6259-117">Задайте <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> свойство нужное значение.</span><span class="sxs-lookup"><span data-stu-id="f6259-117">Set the <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A> property to the desired value.</span></span> <span data-ttu-id="f6259-118">Возможные значения — `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, и `TextBeforeImage`.</span><span class="sxs-lookup"><span data-stu-id="f6259-118">The possibilities are `ImageAboveText`, `ImageBeforeText`, `Overlay`, `TextAboveImage`, and `TextBeforeImage`.</span></span> <span data-ttu-id="f6259-119">Значение по умолчанию — `ImageBeforeText`.</span><span class="sxs-lookup"><span data-stu-id="f6259-119">The default is `ImageBeforeText`.</span></span>  
  
    ```vb  
    ToolStripButton1.TextImageRelation = _  
        System.Windows.Forms.TextImageRelation.ImageAboveText  
    ```  
  
    ```csharp  
    toolStripButton1.TextImageRelation = System.Windows.Forms.TextImageRelation.ImageAboveText;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f6259-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f6259-120">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="f6259-121">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="f6259-121">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="f6259-122">Архитектура элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="f6259-122">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="f6259-123">Технологии, положенные в основу работы элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="f6259-123">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
