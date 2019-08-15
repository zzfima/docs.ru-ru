---
title: Практическое руководство. Прикрепление контекстного меню к элементу управления TreeNode с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: eb3240d35309e03aa8ce949b9c5000f8581d2c2f
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040449"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a><span data-ttu-id="d809d-102">Практическое руководство. Прикрепление контекстного меню к элементу управления TreeNode с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="d809d-102">How to: Attach a Shortcut Menu to a TreeNode Using the Designer</span></span>
<span data-ttu-id="d809d-103">Элемент управления <xref:System.Windows.Forms.TreeView> Windows Forms отображает иерархию узлов, аналогично файлам и папкам, отображаемым на левой панели функции проводника Windows в операционных системах Windows.</span><span class="sxs-lookup"><span data-stu-id="d809d-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of the Windows Explorer feature in Windows operating systems.</span></span> <span data-ttu-id="d809d-104">Установив <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> свойство, можно предоставить пользователю контекстно-зависимые операции, если щелкнуть <xref:System.Windows.Forms.TreeView> элемент управления правой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="d809d-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="d809d-105">Связав <xref:System.Windows.Forms.ContextMenuStrip> компонент с отдельными <xref:System.Windows.Forms.TreeNode> элементами, можно добавить в <xref:System.Windows.Forms.TreeView> элементы управления пользовательский уровень функциональности контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="d809d-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>

## <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a><span data-ttu-id="d809d-106">Связывание контекстного меню с TreeNode во время разработки</span><span class="sxs-lookup"><span data-stu-id="d809d-106">To associate a shortcut menu with a TreeNode at design time</span></span>

1. <span data-ttu-id="d809d-107">Добавьте в форму <xref:System.Windows.Forms.TreeView> элементуправления,азатемдобавьтеузлыв<xref:System.Windows.Forms.TreeView> нужные элементы.</span><span class="sxs-lookup"><span data-stu-id="d809d-107">Add a <xref:System.Windows.Forms.TreeView> control to your form, and then add nodes to the <xref:System.Windows.Forms.TreeView> as needed.</span></span> <span data-ttu-id="d809d-108">Дополнительные сведения см. в разделе [Практическое руководство. Добавление и удаление узлов с помощью элемента управления](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)Windows Forms TreeView.</span><span class="sxs-lookup"><span data-stu-id="d809d-108">For more information, see [How to: Add and Remove Nodes with the Windows Forms TreeView Control](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).</span></span>

2. <span data-ttu-id="d809d-109">Добавьте в форму компонент, а затем добавьте пункты меню в контекстное меню, представляющее операции на уровне узла, которые необходимо сделать доступными во время выполнения. <xref:System.Windows.Forms.ContextMenuStrip></span><span class="sxs-lookup"><span data-stu-id="d809d-109">Add a <xref:System.Windows.Forms.ContextMenuStrip> component to your form, and then add menu items to the shortcut menu that represent node-level operations you wish to make available at run time.</span></span> <span data-ttu-id="d809d-110">Дополнительные сведения см. в разделе [Практическое руководство. Добавление пунктов меню в ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md).</span><span class="sxs-lookup"><span data-stu-id="d809d-110">For more information, see [How to: Add Menu Items to a ContextMenuStrip](how-to-add-menu-items-to-a-contextmenustrip.md).</span></span>

3. <span data-ttu-id="d809d-111">Снова откройте диалоговое окно **тринодидитор** для <xref:System.Windows.Forms.TreeView> элемента управления, выберите изменяемый узел и присвойте его <xref:System.Windows.Forms.ContextMenuStrip> свойству добавленное контекстное меню.</span><span class="sxs-lookup"><span data-stu-id="d809d-111">Reopen the **TreeNodeEditor** dialog box for the <xref:System.Windows.Forms.TreeView> control, select the node to edit, and set its <xref:System.Windows.Forms.ContextMenuStrip> property to the shortcut menu that you added.</span></span>

4. <span data-ttu-id="d809d-112">Если это свойство задано, контекстное меню будет отображаться при щелчке правой кнопкой мыши на узле.</span><span class="sxs-lookup"><span data-stu-id="d809d-112">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>

     <span data-ttu-id="d809d-113">Кроме того, необходимо написать код для управления <xref:System.Windows.Forms.ToolStripItem.Click> событиями этих пунктов меню.</span><span class="sxs-lookup"><span data-stu-id="d809d-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>

## <a name="see-also"></a><span data-ttu-id="d809d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d809d-114">See also</span></span>

- [<span data-ttu-id="d809d-115">Элемент управления TreeView</span><span class="sxs-lookup"><span data-stu-id="d809d-115">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="d809d-116">Общие сведения об элементе управления TreeView</span><span class="sxs-lookup"><span data-stu-id="d809d-116">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="d809d-117">Элемент управления ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="d809d-117">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
