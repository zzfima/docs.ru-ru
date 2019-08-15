---
title: Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: b63bcd9e5e357db350cc2987e09af84eb58bdcff
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039402"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="421fe-102">Практическое руководство. Группирование элементов в элементе управления ListView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="421fe-102">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>

<span data-ttu-id="421fe-103">Функция группирования <xref:System.Windows.Forms.ListView> элемента управления позволяет отображать связанные наборы элементов в группах.</span><span class="sxs-lookup"><span data-stu-id="421fe-103">The grouping feature of the <xref:System.Windows.Forms.ListView> control enables you to display related sets of items in groups.</span></span> <span data-ttu-id="421fe-104">Эти группы разделяются на экране горизонтальными заголовками групп, которые содержат заголовки групп.</span><span class="sxs-lookup"><span data-stu-id="421fe-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="421fe-105">Группы можно использовать <xref:System.Windows.Forms.ListView> для упрощения навигации по большим спискам путем группировки элементов по алфавиту, по датам или по любой другой логической группировке.</span><span class="sxs-lookup"><span data-stu-id="421fe-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="421fe-106">На следующем рисунке показаны некоторые сгруппированные элементы.</span><span class="sxs-lookup"><span data-stu-id="421fe-106">The following image shows some grouped items:</span></span>

![Числа, разделенные на четные и четные группы.](./media/how-to-group-items-in-a-windows-forms-listview-control-using-the-designer/odd-even-list-view-groups.gif)

<span data-ttu-id="421fe-108">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.ListView> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="421fe-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="421fe-109">Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="421fe-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

<span data-ttu-id="421fe-110">Чтобы включить группирование, необходимо сначала создать один или несколько <xref:System.Windows.Forms.ListViewGroup> объектов либо в конструкторе, либо программно.</span><span class="sxs-lookup"><span data-stu-id="421fe-110">To enable grouping, you must first create one or more <xref:System.Windows.Forms.ListViewGroup> objects either in the designer or programmatically.</span></span> <span data-ttu-id="421fe-111">После определения группы можно назначить ей элементы.</span><span class="sxs-lookup"><span data-stu-id="421fe-111">Once a group has been defined, you can assign items to it.</span></span>

> [!NOTE]
> <span data-ttu-id="421fe-112"><xref:System.Windows.Forms.ListView>группы доступны только в [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] том случае, <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> если приложение вызывает метод.</span><span class="sxs-lookup"><span data-stu-id="421fe-112"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="421fe-113">В более ранних операционных системах любой код, связанный с группами, не оказывает никакого влияния, и группы не будут отображаться.</span><span class="sxs-lookup"><span data-stu-id="421fe-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="421fe-114">Дополнительные сведения см. в разделе <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="421fe-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>

## <a name="to-add-or-remove-groups-in-the-designer"></a><span data-ttu-id="421fe-115">Добавление или удаление групп в конструкторе</span><span class="sxs-lookup"><span data-stu-id="421fe-115">To add or remove groups in the designer</span></span>

1. <span data-ttu-id="421fe-116">В окне **"свойства** " нажмите кнопку **с** многоточием![(...) в окно свойств кнопки Visual Studio <xref:System.Windows.Forms.ListView.Groups%2A> .](./media/visual-studio-ellipsis-button.png)) рядом со свойством.</span><span class="sxs-lookup"><span data-stu-id="421fe-116">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Groups%2A> property.</span></span>

     <span data-ttu-id="421fe-117">Откроется **Редактор коллекции листвиевграуп** .</span><span class="sxs-lookup"><span data-stu-id="421fe-117">The **ListViewGroup Collection Editor** appears.</span></span>

2. <span data-ttu-id="421fe-118">Чтобы добавить группу, нажмите кнопку " **Добавить** ".</span><span class="sxs-lookup"><span data-stu-id="421fe-118">To add a group, click the **Add** button.</span></span> <span data-ttu-id="421fe-119">Затем можно задать свойства новой группы, например <xref:System.Windows.Forms.ListViewGroup.Header%2A> свойства и. <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A></span><span class="sxs-lookup"><span data-stu-id="421fe-119">You can then set properties of the new group, such as the <xref:System.Windows.Forms.ListViewGroup.Header%2A> and <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> properties.</span></span> <span data-ttu-id="421fe-120">Чтобы удалить группу, выберите ее и нажмите кнопку **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="421fe-120">To remove a group, select it and click the **Remove** button.</span></span>

## <a name="to-assign-items-to-groups-in-the-designer"></a><span data-ttu-id="421fe-121">Назначение элементов группам в конструкторе</span><span class="sxs-lookup"><span data-stu-id="421fe-121">To assign items to groups in the designer</span></span>

1. <span data-ttu-id="421fe-122">В окне **"свойства** " нажмите кнопку **с** многоточием![(...) в окно свойств кнопки Visual Studio <xref:System.Windows.Forms.ListView.Items%2A> .](./media/visual-studio-ellipsis-button.png)) рядом со свойством.</span><span class="sxs-lookup"><span data-stu-id="421fe-122">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>

     <span data-ttu-id="421fe-123">Откроется **Редактор коллекции ListViewItem** .</span><span class="sxs-lookup"><span data-stu-id="421fe-123">The **ListViewItem Collection Editor** appears.</span></span>

2. <span data-ttu-id="421fe-124">Чтобы добавить новый элемент, нажмите кнопку " **Добавить** ".</span><span class="sxs-lookup"><span data-stu-id="421fe-124">To add a new item, click the **Add** button.</span></span> <span data-ttu-id="421fe-125">Затем можно задать свойства нового элемента, например <xref:System.Windows.Forms.ListViewItem.Text%2A> свойства и. <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A></span><span class="sxs-lookup"><span data-stu-id="421fe-125">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListViewItem.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>

3. <span data-ttu-id="421fe-126"><xref:System.Windows.Forms.ListViewItem.Group%2A> Выберите свойство и выберите группу из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="421fe-126">Select the <xref:System.Windows.Forms.ListViewItem.Group%2A> property and choose a group from the drop-down list.</span></span>

## <a name="see-also"></a><span data-ttu-id="421fe-127">См. также</span><span class="sxs-lookup"><span data-stu-id="421fe-127">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="421fe-128">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="421fe-128">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="421fe-129">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="421fe-129">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="421fe-130">Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="421fe-130">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
