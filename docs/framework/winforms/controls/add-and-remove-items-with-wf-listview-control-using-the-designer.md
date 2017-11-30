---
title: "Практическое руководство. Добавление и удаление элементов с использованием элемента управления ListView в формах Windows Forms с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1fe301f4c504d43fd83eb52e3b32f78af2ca78a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="b1d43-102">Практическое руководство. Добавление и удаление элементов с использованием элемента управления ListView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="b1d43-102">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="b1d43-103">Процесс добавления элемента в форму Windows Forms <xref:System.Windows.Forms.ListView> управления состоит в определение элемента и назначение ему свойств.</span><span class="sxs-lookup"><span data-stu-id="b1d43-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="b1d43-104">Добавление или удаление элементов списка может выполняться в любое время.</span><span class="sxs-lookup"><span data-stu-id="b1d43-104">Adding or removing list items can be done at any time.</span></span>  
  
 <span data-ttu-id="b1d43-105">В следующей процедуре требуется **приложение Windows** проекта с формой, содержащей <xref:System.Windows.Forms.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b1d43-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="b1d43-106">Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b1d43-106">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1d43-107">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="b1d43-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b1d43-108">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="b1d43-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b1d43-109">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="b1d43-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-or-remove-items-using-the-designer"></a><span data-ttu-id="b1d43-110">Для добавления или удаления элементов с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="b1d43-110">To add or remove items using the designer</span></span>  
  
1.  <span data-ttu-id="b1d43-111">Выберите элемент управления <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="b1d43-111">Select the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
2.  <span data-ttu-id="b1d43-112">В **свойства** окно, нажмите кнопку **многоточие** (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с <xref:System.Windows.Forms.ListView.Items%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="b1d43-112">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     <span data-ttu-id="b1d43-113">**Редактор коллекции ListViewItem** отображается.</span><span class="sxs-lookup"><span data-stu-id="b1d43-113">The **ListViewItem Collection Editor** appears.</span></span>  
  
3.  <span data-ttu-id="b1d43-114">Чтобы добавить элемент, нажмите кнопку **добавить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="b1d43-114">To add an item, click the **Add** button.</span></span> <span data-ttu-id="b1d43-115">Затем можно задать свойства нового элемента, например <xref:System.Windows.Forms.ListView.Text%2A> и <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="b1d43-115">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListView.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>  
  
4.  <span data-ttu-id="b1d43-116">Чтобы удалить элемент, выберите его и нажмите кнопку **удалить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="b1d43-116">To remove an item, select it and click the **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d43-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b1d43-117">See Also</span></span>  
 [<span data-ttu-id="b1d43-118">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="b1d43-118">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="b1d43-119">Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1d43-119">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="b1d43-120">Практическое руководство. Отображение дополнительных данных в столбцах элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1d43-120">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="b1d43-121">Практическое руководство. Отображение значков в элементе управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1d43-121">How to: Display Icons for the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="b1d43-122">Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b1d43-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [<span data-ttu-id="b1d43-123">Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b1d43-123">How to: Group Items in a Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)
