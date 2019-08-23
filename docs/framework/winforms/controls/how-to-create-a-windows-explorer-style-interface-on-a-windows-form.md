---
title: Практическое руководство. Создание интерфейса в стиле проводника в форме Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 34a5cd735c350688d9e83003806668e213932c85
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960629"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="19669-102">Практическое руководство. Создание интерфейса в стиле проводника в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="19669-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="19669-103">Проводник Windows — это общий вариант пользовательского интерфейса для приложений из-за его готовности.</span><span class="sxs-lookup"><span data-stu-id="19669-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>

 <span data-ttu-id="19669-104">Проводник Windows — это, по сути <xref:System.Windows.Forms.TreeView> , элемент управления <xref:System.Windows.Forms.ListView> и элемент управления на отдельных панелях.</span><span class="sxs-lookup"><span data-stu-id="19669-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="19669-105">Размеры панелей преобразуются в один и тот же разделитель.</span><span class="sxs-lookup"><span data-stu-id="19669-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="19669-106">Такое размещение элементов управления очень эффективно для отображения и просмотра информации.</span><span class="sxs-lookup"><span data-stu-id="19669-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>

 <span data-ttu-id="19669-107">Ниже показано, как упорядочивать элементы управления в форме, похожей на проводник Windows.</span><span class="sxs-lookup"><span data-stu-id="19669-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="19669-108">Они не показывают, как добавить функции просмотра файлов в приложении проводника Windows.</span><span class="sxs-lookup"><span data-stu-id="19669-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>

## <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="19669-109">Создание Windows Form в стиле проводника Windows</span><span class="sxs-lookup"><span data-stu-id="19669-109">To create a Windows Explorer-style Windows Form</span></span>

1. <span data-ttu-id="19669-110">Создание нового проекта приложения Windows (**файл** > **создать** > **проект** > **визуальный C#**  элемент или **Visual Basic** > **классический рабочий стол**  > ) **Windows Forms приложение**).</span><span class="sxs-lookup"><span data-stu-id="19669-110">Create a new Windows Application project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="19669-111">Из **области элементов**:</span><span class="sxs-lookup"><span data-stu-id="19669-111">From the **Toolbox**:</span></span>

    1. <span data-ttu-id="19669-112"><xref:System.Windows.Forms.SplitContainer> Перетащите элемент управления на форму.</span><span class="sxs-lookup"><span data-stu-id="19669-112">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>

    2. <span data-ttu-id="19669-113">Перетащите элемент управления в **SplitterPanel1** (панель <xref:System.Windows.Forms.SplitContainer> элемента управления с меткой Panel1). <xref:System.Windows.Forms.TreeView></span><span class="sxs-lookup"><span data-stu-id="19669-113">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>

    3. <span data-ttu-id="19669-114">Перетащите элемент управления в **SplitterPanel2** (панель <xref:System.Windows.Forms.SplitContainer> элемента управления с пометкой Panel2). <xref:System.Windows.Forms.ListView></span><span class="sxs-lookup"><span data-stu-id="19669-114">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>

3. <span data-ttu-id="19669-115">Выберите все три элемента управления, нажав клавишу CTRL и щелкнув их по очереди.</span><span class="sxs-lookup"><span data-stu-id="19669-115">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="19669-116">При выборе <xref:System.Windows.Forms.SplitContainer> элемента управления щелкните линию разделения, а не панели.</span><span class="sxs-lookup"><span data-stu-id="19669-116">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>

    > [!NOTE]
    > <span data-ttu-id="19669-117">Не используйте команду **выбрать все** в меню **Правка** .</span><span class="sxs-lookup"><span data-stu-id="19669-117">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="19669-118">В этом случае свойство, необходимое на следующем шаге, не будет отображаться в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="19669-118">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>

4. <span data-ttu-id="19669-119">В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.SplitContainer.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="19669-119">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

5. <span data-ttu-id="19669-120">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="19669-120">Press F5 to run the application.</span></span>

     <span data-ttu-id="19669-121">В этой форме представлен пользовательский интерфейс с двумя частями, аналогичный проводнику Windows.</span><span class="sxs-lookup"><span data-stu-id="19669-121">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="19669-122">При перетаскивании разделителя размеры панелей изменяются самим.</span><span class="sxs-lookup"><span data-stu-id="19669-122">When you drag the splitter, the panels resize themselves.</span></span>

## <a name="see-also"></a><span data-ttu-id="19669-123">См. также</span><span class="sxs-lookup"><span data-stu-id="19669-123">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="19669-124">Практическое руководство. Создание пользовательского интерфейса с несколькими панелями с помощью Windows Forms</span><span class="sxs-lookup"><span data-stu-id="19669-124">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [<span data-ttu-id="19669-125">Практическое руководство. Определение поведения изменения размера и позиционирования в окне с разделением</span><span class="sxs-lookup"><span data-stu-id="19669-125">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [<span data-ttu-id="19669-126">Практическое руководство. Разделение окна по горизонтали</span><span class="sxs-lookup"><span data-stu-id="19669-126">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)
- [<span data-ttu-id="19669-127">Элемент управления SplitContainer</span><span class="sxs-lookup"><span data-stu-id="19669-127">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
