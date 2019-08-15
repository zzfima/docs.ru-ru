---
title: Практическое руководство. Добавление и удаление элементов с использованием элемента управления ListView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: 62665746ea9fcd1553717b02b1f1349dc6415ab2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040085"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="4f84b-102">Практическое руководство. Добавление и удаление элементов с использованием элемента управления ListView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="4f84b-102">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="4f84b-103">Процесс добавления элемента в элемент управления Windows Forms <xref:System.Windows.Forms.ListView> состоит в основном из указания элемента и присвоения ему свойств.</span><span class="sxs-lookup"><span data-stu-id="4f84b-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="4f84b-104">Добавление или удаление элементов списка можно выполнить в любое время.</span><span class="sxs-lookup"><span data-stu-id="4f84b-104">Adding or removing list items can be done at any time.</span></span>

<span data-ttu-id="4f84b-105">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.ListView> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="4f84b-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="4f84b-106">Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4f84b-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-or-remove-items-using-the-designer"></a><span data-ttu-id="4f84b-107">Добавление или удаление элементов с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="4f84b-107">To add or remove items using the designer</span></span>

1. <span data-ttu-id="4f84b-108">Выберите элемент управления <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="4f84b-108">Select the <xref:System.Windows.Forms.ListView> control.</span></span>

2. <span data-ttu-id="4f84b-109">В окне **"свойства** " нажмите кнопку **с** многоточием![(...) в окно свойств кнопки Visual Studio <xref:System.Windows.Forms.ListView.Items%2A> .](./media/visual-studio-ellipsis-button.png)) рядом со свойством.</span><span class="sxs-lookup"><span data-stu-id="4f84b-109">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="4f84b-110">Откроется **Редактор коллекции ListViewItem** .</span><span class="sxs-lookup"><span data-stu-id="4f84b-110">The **ListViewItem Collection Editor** appears.</span></span>

3. <span data-ttu-id="4f84b-111">Чтобы добавить элемент, нажмите кнопку " **Добавить** ".</span><span class="sxs-lookup"><span data-stu-id="4f84b-111">To add an item, click the **Add** button.</span></span> <span data-ttu-id="4f84b-112">Затем можно задать свойства нового элемента, например <xref:System.Windows.Forms.ListView.Text%2A> свойства и. <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A></span><span class="sxs-lookup"><span data-stu-id="4f84b-112">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListView.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

4. <span data-ttu-id="4f84b-113">Чтобы удалить элемент, выберите его и нажмите кнопку **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="4f84b-113">To remove an item, select it and click the **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f84b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4f84b-114">See also</span></span>

- [<span data-ttu-id="4f84b-115">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="4f84b-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="4f84b-116">Практическое руководство. Добавление столбцов в Windows Forms элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="4f84b-116">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="4f84b-117">Практическое руководство. Отображение подэлементов в столбцах с Windows Forms элементом управления ListView</span><span class="sxs-lookup"><span data-stu-id="4f84b-117">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="4f84b-118">Практическое руководство. Отображение значков для элемента управления ListView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f84b-118">How to: Display Icons for the Windows Forms ListView Control</span></span>](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [<span data-ttu-id="4f84b-119">Практическое руководство. Добавление пользовательских сведений в элемент управления TreeView или ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4f84b-119">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="4f84b-120">Практическое руководство. Группирование элементов в элементе управления ListView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f84b-120">How to: Group Items in a Windows Forms ListView Control</span></span>](how-to-group-items-in-a-windows-forms-listview-control.md)
