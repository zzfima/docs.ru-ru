---
title: Группирование элементов в элементе управления ListView с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 935d8d75517e1028e686ca229f6ada656f58b01e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736684"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="c5cb6-102">Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="c5cb6-102">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="c5cb6-103">Функция группирования элемента управления <xref:System.Windows.Forms.ListView> позволяет отображать связанные наборы элементов в группах.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-103">The grouping feature of the <xref:System.Windows.Forms.ListView> control enables you to display related sets of items in groups.</span></span> <span data-ttu-id="c5cb6-104">Эти группы разделяются на экране горизонтальными заголовками групп, которые содержат заголовки групп.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="c5cb6-105">Вы можете использовать группы <xref:System.Windows.Forms.ListView>, чтобы упростить навигацию по большим спискам, группируя элементы по алфавиту, по датам или по любой другой логической группировке.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="c5cb6-106">На следующем рисунке показаны некоторые сгруппированные элементы.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-106">The following image shows some grouped items:</span></span>

![Числа, разделенные на четные и четные группы.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

<span data-ttu-id="c5cb6-108">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="c5cb6-109">Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c5cb6-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

<span data-ttu-id="c5cb6-110">Чтобы включить группирование, необходимо сначала создать один или несколько объектов <xref:System.Windows.Forms.ListViewGroup> в конструкторе или программно.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-110">To enable grouping, you must first create one or more <xref:System.Windows.Forms.ListViewGroup> objects either in the designer or programmatically.</span></span> <span data-ttu-id="c5cb6-111">После определения группы можно назначить ей элементы.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-111">Once a group has been defined, you can assign items to it.</span></span>

## <a name="to-add-or-remove-groups-in-the-designer"></a><span data-ttu-id="c5cb6-112">Добавление или удаление групп в конструкторе</span><span class="sxs-lookup"><span data-stu-id="c5cb6-112">To add or remove groups in the designer</span></span>

1. <span data-ttu-id="c5cb6-113">В окне **Свойства** нажмите кнопку **с многоточием** (![кнопку с многоточием (...) в окно свойств кнопки Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.ListView.Groups%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-113">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Groups%2A> property.</span></span>

     <span data-ttu-id="c5cb6-114">Откроется **Редактор коллекции листвиевграуп** .</span><span class="sxs-lookup"><span data-stu-id="c5cb6-114">The **ListViewGroup Collection Editor** appears.</span></span>

2. <span data-ttu-id="c5cb6-115">Чтобы добавить группу, нажмите кнопку " **Добавить** ".</span><span class="sxs-lookup"><span data-stu-id="c5cb6-115">To add a group, click the **Add** button.</span></span> <span data-ttu-id="c5cb6-116">Затем можно задать свойства новой группы, например свойства <xref:System.Windows.Forms.ListViewGroup.Header%2A> и <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-116">You can then set properties of the new group, such as the <xref:System.Windows.Forms.ListViewGroup.Header%2A> and <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> properties.</span></span> <span data-ttu-id="c5cb6-117">Чтобы удалить группу, выберите ее и нажмите кнопку **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="c5cb6-117">To remove a group, select it and click the **Remove** button.</span></span>

## <a name="to-assign-items-to-groups-in-the-designer"></a><span data-ttu-id="c5cb6-118">Назначение элементов группам в конструкторе</span><span class="sxs-lookup"><span data-stu-id="c5cb6-118">To assign items to groups in the designer</span></span>

1. <span data-ttu-id="c5cb6-119">В окне **Свойства** нажмите кнопку **с многоточием** (![кнопку с многоточием (...) в окно свойств кнопки Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.ListView.Items%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-119">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="c5cb6-120">Откроется **Редактор коллекции ListViewItem** .</span><span class="sxs-lookup"><span data-stu-id="c5cb6-120">The **ListViewItem Collection Editor** appears.</span></span>

2. <span data-ttu-id="c5cb6-121">Чтобы добавить новый элемент, нажмите кнопку " **Добавить** ".</span><span class="sxs-lookup"><span data-stu-id="c5cb6-121">To add a new item, click the **Add** button.</span></span> <span data-ttu-id="c5cb6-122">Затем можно задать свойства нового элемента, например свойства <xref:System.Windows.Forms.ListViewItem.Text%2A> и <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-122">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListViewItem.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

3. <span data-ttu-id="c5cb6-123">Выберите свойство <xref:System.Windows.Forms.ListViewItem.Group%2A> и выберите группу из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="c5cb6-123">Select the <xref:System.Windows.Forms.ListViewItem.Group%2A> property and choose a group from the drop-down list.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5cb6-124">См. также:</span><span class="sxs-lookup"><span data-stu-id="c5cb6-124">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="c5cb6-125">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="c5cb6-125">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="c5cb6-126">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="c5cb6-126">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="c5cb6-127">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c5cb6-127">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
