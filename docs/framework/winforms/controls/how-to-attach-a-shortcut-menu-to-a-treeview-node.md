---
title: Практическое руководство. Подключение контекстного меню к узлу элемента управления TreeView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
ms.openlocfilehash: 737e74184b0763ed84b4e585f2508d69944d0e77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528224"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a><span data-ttu-id="a622b-102">Практическое руководство. Подключение контекстного меню к узлу элемента управления TreeView</span><span class="sxs-lookup"><span data-stu-id="a622b-102">How to: Attach a ShortCut Menu to a TreeView Node</span></span>
<span data-ttu-id="a622b-103">Windows Forms <xref:System.Windows.Forms.TreeView> элемент управления выводит на экран иерархию узлов аналогично отображения файлов и папок в левой области окна проводника.</span><span class="sxs-lookup"><span data-stu-id="a622b-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of Windows Explorer.</span></span> <span data-ttu-id="a622b-104">Установив <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> свойства, можно предоставить контекстно-зависимые операции для пользователя при их правой кнопкой мыши <xref:System.Windows.Forms.TreeView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a622b-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="a622b-105">Связав <xref:System.Windows.Forms.ContextMenuStrip> компонента с отдельными <xref:System.Windows.Forms.TreeNode> элементы, можно добавить настраиваемый уровень функциональности контекстное меню для вашего <xref:System.Windows.Forms.TreeView> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="a622b-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a><span data-ttu-id="a622b-106">Чтобы связать контекстное меню с TreeNode программным способом</span><span class="sxs-lookup"><span data-stu-id="a622b-106">To associate a shortcut menu with a TreeNode programmatically</span></span>  
  
1.  <span data-ttu-id="a622b-107">Создать экземпляр <xref:System.Windows.Forms.TreeView> управления с соответствующими параметрами свойств, создайте корневой <xref:System.Windows.Forms.TreeNode>, а затем добавьте вложенные узлы.</span><span class="sxs-lookup"><span data-stu-id="a622b-107">Instantiate a <xref:System.Windows.Forms.TreeView> control with the appropriate property settings, create a root <xref:System.Windows.Forms.TreeNode>, and then add subnodes.</span></span>  
  
2.  <span data-ttu-id="a622b-108">Создать экземпляр <xref:System.Windows.Forms.ContextMenuStrip> компонента, а затем добавьте <xref:System.Windows.Forms.ToolStripMenuItem> для каждой операции, которую нужно сделать доступными во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a622b-108">Instantiate a <xref:System.Windows.Forms.ContextMenuStrip> component, and then add a <xref:System.Windows.Forms.ToolStripMenuItem> for each operation you want to make available at run time.</span></span>  
  
3.  <span data-ttu-id="a622b-109">Задать <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> свойства соответствующего <xref:System.Windows.Forms.TreeNode> в контекстное меню создания.</span><span class="sxs-lookup"><span data-stu-id="a622b-109">Set the <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> property of the appropriate <xref:System.Windows.Forms.TreeNode> to the shortcut menu you create.</span></span>  
  
4.  <span data-ttu-id="a622b-110">Если это свойство имеет значение, в контекстном меню отображается при щелчке правой кнопкой мыши узел.</span><span class="sxs-lookup"><span data-stu-id="a622b-110">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
 <span data-ttu-id="a622b-111">В следующем примере кода создается простой <xref:System.Windows.Forms.TreeView> и <xref:System.Windows.Forms.ContextMenuStrip> связанную с корневым <xref:System.Windows.Forms.TreeNode> из <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="a622b-111">The following code example creates a basic <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ContextMenuStrip> associated with the root <xref:System.Windows.Forms.TreeNode> of the <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="a622b-112">Необходимо будет подставить те пункты меню, которые соответствуют <xref:System.Windows.Forms.TreeView> вы разрабатываете.</span><span class="sxs-lookup"><span data-stu-id="a622b-112">You will need to customize the menu choices to those that fit the <xref:System.Windows.Forms.TreeView> you are developing.</span></span> <span data-ttu-id="a622b-113">Кроме того, необходимо написать код для обработки <xref:System.Windows.Forms.ToolStripItem.Click> событий для этих пунктов меню.</span><span class="sxs-lookup"><span data-stu-id="a622b-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a622b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a622b-114">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [<span data-ttu-id="a622b-115">Элемент управления TreeView</span><span class="sxs-lookup"><span data-stu-id="a622b-115">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
