---
title: Добавление и удаление узлов с помощью элемента управления TreeView в конструкторе
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 7edf09539719ec76fa3f650254c5c84ff0bc3af7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732251"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a><span data-ttu-id="5a47b-102">Практическое руководство. Добавление и удаление узлов с использованием элемента управления TreeView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="5a47b-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control Using the Designer</span></span>

<span data-ttu-id="5a47b-103">Поскольку элемент управления Windows Forms <xref:System.Windows.Forms.TreeView> отображает узлы иерархически, при добавлении узла необходимо обратить внимание на то, что имеет его родительский узел.</span><span class="sxs-lookup"><span data-stu-id="5a47b-103">Because the Windows Forms <xref:System.Windows.Forms.TreeView> control displays nodes in a hierarchical manner, when adding a node you must pay attention to what its parent node is.</span></span>

<span data-ttu-id="5a47b-104">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="5a47b-104">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="5a47b-105">Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5a47b-105">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-or-remove-nodes-in-the-designer"></a><span data-ttu-id="5a47b-106">Добавление или удаление узлов в конструкторе</span><span class="sxs-lookup"><span data-stu-id="5a47b-106">To add or remove nodes in the designer</span></span>

1. <span data-ttu-id="5a47b-107">Выберите элемент управления <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="5a47b-107">Select the <xref:System.Windows.Forms.TreeView> control.</span></span>

2. <span data-ttu-id="5a47b-108">В окне **Свойства** нажмите кнопку **с многоточием** (![кнопку с многоточием (...) в окно свойств кнопки Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.TreeView.Nodes%2A>.</span><span class="sxs-lookup"><span data-stu-id="5a47b-108">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>

     <span data-ttu-id="5a47b-109">Откроется **Редактор TreeNode** .</span><span class="sxs-lookup"><span data-stu-id="5a47b-109">The **TreeNode Editor** appears.</span></span>

3. <span data-ttu-id="5a47b-110">Для добавления узлов должен существовать корневой узел. Если он не существует, необходимо сначала добавить корень, нажав кнопку **Добавить корень** .</span><span class="sxs-lookup"><span data-stu-id="5a47b-110">To add nodes, a root node must exist; if one does not exist, you must first add a root by clicking the **Add Root** button.</span></span> <span data-ttu-id="5a47b-111">Затем можно добавить дочерние узлы, выбрав корень или любой другой узел и нажав кнопку **Добавить дочерний** элемент.</span><span class="sxs-lookup"><span data-stu-id="5a47b-111">You can then add child nodes by selecting the root or any other node and clicking the **Add Child** button.</span></span>

4. <span data-ttu-id="5a47b-112">Чтобы удалить узлы, выберите узел для удаления и нажмите кнопку **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="5a47b-112">To delete nodes, select the node to delete and then click the **Delete** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a47b-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5a47b-113">See also</span></span>

- [<span data-ttu-id="5a47b-114">Элемент управления TreeView</span><span class="sxs-lookup"><span data-stu-id="5a47b-114">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="5a47b-115">Общие сведения об элементе управления TreeView</span><span class="sxs-lookup"><span data-stu-id="5a47b-115">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="5a47b-116">Практическое руководство. Определение значков для элемента управления TreeView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a47b-116">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="5a47b-117">Практическое руководство. Перебор узлов элемента управления TreeView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5a47b-117">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="5a47b-118">Практическое руководство. Определение того, какой узел элемента управления TreeView был выбран щелчком мыши</span><span class="sxs-lookup"><span data-stu-id="5a47b-118">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="5a47b-119">Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5a47b-119">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
