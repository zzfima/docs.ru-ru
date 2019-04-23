---
title: Практическое руководство. Определение значков для элемента управления TreeView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: 1a857aade86d2366bb68ce14d716b3ce532ecb05
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59328417"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a><span data-ttu-id="da509-102">Практическое руководство. Определение значков для элемента управления TreeView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da509-102">How to: Set Icons for the Windows Forms TreeView Control</span></span>
<span data-ttu-id="da509-103">Windows Forms <xref:System.Windows.Forms.TreeView> элемент управления может отображать значки рядом с каждым узлом.</span><span class="sxs-lookup"><span data-stu-id="da509-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control can display icons next to each node.</span></span> <span data-ttu-id="da509-104">Значки располагаются непосредственно слева от текста узла.</span><span class="sxs-lookup"><span data-stu-id="da509-104">The icons are positioned to the immediate left of the node text.</span></span> <span data-ttu-id="da509-105">Чтобы отобразить эти значки, необходимо связать представлении в виде дерева с <xref:System.Windows.Forms.ImageList> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="da509-105">To display these icons, you must associate the tree view with an <xref:System.Windows.Forms.ImageList> control.</span></span> <span data-ttu-id="da509-106">Дополнительные сведения о списках изображений, см. в разделе [компонента ImageList](imagelist-component-windows-forms.md) и [как: Добавление и удаление изображений с помощью Windows Forms компонента ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="da509-106">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="da509-107">Ошибка в Microsoft .NET Framework версии 1.1 предотвращает появление на образы <xref:System.Windows.Forms.TreeView> узлы, когда приложение вызывает <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="da509-107">A bug in Microsoft .NET Framework version 1.1 prevents images from appearing on <xref:System.Windows.Forms.TreeView> nodes when your application calls <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="da509-108">Чтобы обойти эту ошибку, вызовите <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> в вашей `Main` метод сразу после вызова <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span><span class="sxs-lookup"><span data-stu-id="da509-108">To work around this bug, call <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in your `Main` method immediately after calling <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span></span> <span data-ttu-id="da509-109">Эта ошибка исправлена в [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da509-109">This bug is fixed in [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
### <a name="to-display-images-in-a-tree-view"></a><span data-ttu-id="da509-110">Для отображения изображений в виде дерева</span><span class="sxs-lookup"><span data-stu-id="da509-110">To display images in a tree view</span></span>  
  
1. <span data-ttu-id="da509-111">Задайте <xref:System.Windows.Forms.TreeView> элемента управления <xref:System.Windows.Forms.TreeView.ImageList%2A> к существующему полю <xref:System.Windows.Forms.ImageList> элемента управления, которые вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="da509-111">Set the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.ImageList%2A> property to the existing <xref:System.Windows.Forms.ImageList> control you wish to use.</span></span>  
  
     <span data-ttu-id="da509-112">Эти свойства можно задать в конструкторе с помощью окна «Свойства» или в коде.</span><span class="sxs-lookup"><span data-stu-id="da509-112">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. <span data-ttu-id="da509-113">Узел набора <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> и <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="da509-113">Set the node's <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> and <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> properties.</span></span> <span data-ttu-id="da509-114"><xref:System.Windows.Forms.TreeNode.ImageIndex%2A> Свойство определяет, изображения, отображаемого для обычного и развернутого состояний узла и <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> свойство определяет, изображения, отображаемого для выделенного узла.</span><span class="sxs-lookup"><span data-stu-id="da509-114">The <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> property determines the image displayed for the node's normal and expanded states, and the <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> property determines the image displayed for the node's selected state.</span></span>  
  
     <span data-ttu-id="da509-115">Эти свойства можно задать в коде или в редактор узлов дерева.</span><span class="sxs-lookup"><span data-stu-id="da509-115">These properties can be set in code, or within the TreeNode Editor.</span></span> <span data-ttu-id="da509-116">Чтобы открыть редактор узлов дерева, нажмите кнопку с многоточием ( ![экрана VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) рядом с полем <xref:System.Windows.Forms.TreeView.Nodes%2A> свойство в окне «Свойства».</span><span class="sxs-lookup"><span data-stu-id="da509-116">To open the TreeNode Editor, click the ellipsis button ( ![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property on the Properties window.</span></span>  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="da509-117">См. также</span><span class="sxs-lookup"><span data-stu-id="da509-117">See also</span></span>

- [<span data-ttu-id="da509-118">Общие сведения об элементе управления TreeView</span><span class="sxs-lookup"><span data-stu-id="da509-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="da509-119">Практическое руководство. Добавление и удаление узлов с помощью элемента управления TreeView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da509-119">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="da509-120">Практическое руководство. Перебор узлов элемента управления TreeView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="da509-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="da509-121">Практическое руководство. Определить, какой узел элемента управления TreeView была нажата</span><span class="sxs-lookup"><span data-stu-id="da509-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="da509-122">Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или элемент управления ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="da509-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
