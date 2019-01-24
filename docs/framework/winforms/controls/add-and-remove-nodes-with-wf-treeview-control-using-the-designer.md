---
title: Как выполнить Добавление и удаление узлов с помощью элемента управления Windows Forms TreeView с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: 7ef1a21ee4cb6e8313c01e7f5af30d19d00d07cf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649886"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a><span data-ttu-id="02eb4-102">Как выполнить Добавление и удаление узлов с помощью элемента управления Windows Forms TreeView с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="02eb4-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control Using the Designer</span></span>
<span data-ttu-id="02eb4-103">Так как Windows Forms <xref:System.Windows.Forms.TreeView> элемент управления отображает узлы в виде иерархии, при добавлении узла следует обращать внимание на является его родительским узлом.</span><span class="sxs-lookup"><span data-stu-id="02eb4-103">Because the Windows Forms <xref:System.Windows.Forms.TreeView> control displays nodes in a hierarchical manner, when adding a node you must pay attention to what its parent node is.</span></span>  
  
 <span data-ttu-id="02eb4-104">Следующая процедура требуется **приложения Windows** проекта с формой, содержащей <xref:System.Windows.Forms.TreeView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="02eb4-104">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="02eb4-105">Сведения о настройке такого проекта см. в разделе [как: Создайте проект приложения Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="02eb4-105">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02eb4-106">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="02eb4-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="02eb4-107">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="02eb4-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="02eb4-108">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="02eb4-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a><span data-ttu-id="02eb4-109">Для добавления или удаления узлов в конструкторе</span><span class="sxs-lookup"><span data-stu-id="02eb4-109">To add or remove nodes in the designer</span></span>  
  
1.  <span data-ttu-id="02eb4-110">Выберите элемент управления <xref:System.Windows.Forms.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="02eb4-110">Select the <xref:System.Windows.Forms.TreeView> control.</span></span>  
  
2.  <span data-ttu-id="02eb4-111">В **свойства** окно, нажмите кнопку **кнопку с многоточием** (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с полем <xref:System.Windows.Forms.TreeView.Nodes%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="02eb4-111">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
     <span data-ttu-id="02eb4-112">**Редактор TreeNode** отображается.</span><span class="sxs-lookup"><span data-stu-id="02eb4-112">The **TreeNode Editor** appears.</span></span>  
  
3.  <span data-ttu-id="02eb4-113">Чтобы добавить узлы, необходимо наличие корневого узла; Если она отсутствует, вы должны сначала добавить его, нажав кнопку **Добавить корень** кнопки.</span><span class="sxs-lookup"><span data-stu-id="02eb4-113">To add nodes, a root node must exist; if one does not exist, you must first add a root by clicking the **Add Root** button.</span></span> <span data-ttu-id="02eb4-114">После этого можно добавить дочерний узел, выделив корневой или любой другой узел и нажав кнопку **добавить дочерний элемент** кнопки.</span><span class="sxs-lookup"><span data-stu-id="02eb4-114">You can then add child nodes by selecting the root or any other node and clicking the **Add Child** button.</span></span>  
  
4.  <span data-ttu-id="02eb4-115">Чтобы удалить узлы, выберите узел, чтобы удалить, а затем нажмите кнопку **удалить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="02eb4-115">To delete nodes, select the node to delete and then click the **Delete** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02eb4-116">См. также</span><span class="sxs-lookup"><span data-stu-id="02eb4-116">See also</span></span>
- [<span data-ttu-id="02eb4-117">Элемент управления TreeView</span><span class="sxs-lookup"><span data-stu-id="02eb4-117">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
- [<span data-ttu-id="02eb4-118">Общие сведения об элементе управления TreeView</span><span class="sxs-lookup"><span data-stu-id="02eb4-118">TreeView Control Overview</span></span>](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="02eb4-119">Практическое руководство. Определение значков для элемента управления TreeView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="02eb4-119">How to: Set Icons for the Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="02eb4-120">Практическое руководство. Перебор узлов элемента управления TreeView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="02eb4-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="02eb4-121">Практическое руководство. Определить, какой узел элемента управления TreeView была нажата</span><span class="sxs-lookup"><span data-stu-id="02eb4-121">How to: Determine Which TreeView Node Was Clicked</span></span>](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="02eb4-122">Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или элемент управления ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="02eb4-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
