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
ms.openlocfilehash: 537593399db7deb775929cd742a749ce47890db6
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703630"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a><span data-ttu-id="06330-102">Практическое руководство. Подключение контекстного меню к узлу элемента управления TreeView</span><span class="sxs-lookup"><span data-stu-id="06330-102">How to: Attach a ShortCut Menu to a TreeView Node</span></span>
<span data-ttu-id="06330-103">Windows Forms <xref:System.Windows.Forms.TreeView> элемент управления отображает иерархию узлов аналогично к файлам и папкам, отображаемым в левой части проводника Windows.</span><span class="sxs-lookup"><span data-stu-id="06330-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of Windows Explorer.</span></span> <span data-ttu-id="06330-104">Установив <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> свойство, можно предоставить контекстно-зависимые операции для пользователя при их правой кнопкой мыши <xref:System.Windows.Forms.TreeView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="06330-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="06330-105">Связав <xref:System.Windows.Forms.ContextMenuStrip> компонента с отдельными <xref:System.Windows.Forms.TreeNode> элементы, можно добавить пользовательский уровень функциональности контекстное меню для вашей <xref:System.Windows.Forms.TreeView> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="06330-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a><span data-ttu-id="06330-106">Чтобы связать контекстное меню с TreeNode программным способом</span><span class="sxs-lookup"><span data-stu-id="06330-106">To associate a shortcut menu with a TreeNode programmatically</span></span>  
  
1.  <span data-ttu-id="06330-107">Создать экземпляр <xref:System.Windows.Forms.TreeView> управления с соответствующими параметрами свойств, создайте корневой <xref:System.Windows.Forms.TreeNode>, а затем добавьте подузлы.</span><span class="sxs-lookup"><span data-stu-id="06330-107">Instantiate a <xref:System.Windows.Forms.TreeView> control with the appropriate property settings, create a root <xref:System.Windows.Forms.TreeNode>, and then add subnodes.</span></span>  
  
2.  <span data-ttu-id="06330-108">Создать экземпляр <xref:System.Windows.Forms.ContextMenuStrip> компонента, а затем добавьте <xref:System.Windows.Forms.ToolStripMenuItem> для каждой операции, которые требуется сделать доступными во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="06330-108">Instantiate a <xref:System.Windows.Forms.ContextMenuStrip> component, and then add a <xref:System.Windows.Forms.ToolStripMenuItem> for each operation you want to make available at run time.</span></span>  
  
3.  <span data-ttu-id="06330-109">Задайте <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> свойства соответствующего <xref:System.Windows.Forms.TreeNode> в контекстное меню создания.</span><span class="sxs-lookup"><span data-stu-id="06330-109">Set the <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> property of the appropriate <xref:System.Windows.Forms.TreeNode> to the shortcut menu you create.</span></span>  
  
4.  <span data-ttu-id="06330-110">Если это свойство имеет значение, в контекстном меню отображается при щелчке правой кнопкой узел.</span><span class="sxs-lookup"><span data-stu-id="06330-110">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
 <span data-ttu-id="06330-111">В следующем примере кода создает базовое <xref:System.Windows.Forms.TreeView> и <xref:System.Windows.Forms.ContextMenuStrip> связанный с этим корнем <xref:System.Windows.Forms.TreeNode> из <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="06330-111">The following code example creates a basic <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ContextMenuStrip> associated with the root <xref:System.Windows.Forms.TreeNode> of the <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="06330-112">Вам потребуется подставить пункты меню, которые соответствуют <xref:System.Windows.Forms.TreeView> при разработке.</span><span class="sxs-lookup"><span data-stu-id="06330-112">You will need to customize the menu choices to those that fit the <xref:System.Windows.Forms.TreeView> you are developing.</span></span> <span data-ttu-id="06330-113">Кроме того, необходимо написать код для обработки <xref:System.Windows.Forms.ToolStripItem.Click> события для этих пунктов меню.</span><span class="sxs-lookup"><span data-stu-id="06330-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="06330-114">См. также</span><span class="sxs-lookup"><span data-stu-id="06330-114">See also</span></span>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="06330-115">Элемент управления TreeView</span><span class="sxs-lookup"><span data-stu-id="06330-115">TreeView Control</span></span>](treeview-control-windows-forms.md)
