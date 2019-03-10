---
title: Практическое руководство. Создание интерфейса в стиле проводника Windows в форме Windows
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 444d85265822b5dd4b3a5fd5f4329ec6cc1427f5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705016"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="0ad45-102">Практическое руководство. Создание интерфейса в стиле проводника Windows в форме Windows</span><span class="sxs-lookup"><span data-stu-id="0ad45-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="0ad45-103">Windows Explorer является распространенным вариантом пользовательского интерфейса для приложений из-за его хорошо знаком всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="0ad45-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>  
  
 <span data-ttu-id="0ad45-104">Windows Explorer является, по сути, <xref:System.Windows.Forms.TreeView> управления и <xref:System.Windows.Forms.ListView> на отдельных панелях.</span><span class="sxs-lookup"><span data-stu-id="0ad45-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="0ad45-105">Панелей вносятся можно изменять с помощью разделителя.</span><span class="sxs-lookup"><span data-stu-id="0ad45-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="0ad45-106">Это упорядочение элементов управления является весьма эффективным для отображения и просмотра информации.</span><span class="sxs-lookup"><span data-stu-id="0ad45-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>  
  
 <span data-ttu-id="0ad45-107">Ниже показано, как расположить элементы управления в форме проводника Windows.</span><span class="sxs-lookup"><span data-stu-id="0ad45-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="0ad45-108">Они не демонстрируют Добавление функций просмотра файлов приложения Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="0ad45-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ad45-109">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="0ad45-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0ad45-110">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="0ad45-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0ad45-111">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="0ad45-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="0ad45-112">Для создания формы Windows проводника Windows</span><span class="sxs-lookup"><span data-stu-id="0ad45-112">To create a Windows Explorer-style Windows Form</span></span>  
  
1.  <span data-ttu-id="0ad45-113">Создайте новый проект приложения Windows (**файл** > **New** > **проекта** > **Visual C#** или **Visual Basic** > **классический рабочий стол** > **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="0ad45-113">Create a new Windows Application project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="0ad45-114">Из **элементов**:</span><span class="sxs-lookup"><span data-stu-id="0ad45-114">From the **Toolbox**:</span></span>  
  
    1.  <span data-ttu-id="0ad45-115">Перетащите <xref:System.Windows.Forms.SplitContainer> управления на форму.</span><span class="sxs-lookup"><span data-stu-id="0ad45-115">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>  
  
    2.  <span data-ttu-id="0ad45-116">Перетащите <xref:System.Windows.Forms.TreeView> управления в **SplitterPanel1** (панели <xref:System.Windows.Forms.SplitContainer> управления, помеченных как **Panel1**).</span><span class="sxs-lookup"><span data-stu-id="0ad45-116">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>  
  
    3.  <span data-ttu-id="0ad45-117">Перетащите <xref:System.Windows.Forms.ListView> управления в **SplitterPanel2** (панели <xref:System.Windows.Forms.SplitContainer> управления, помеченных как **Panel2**).</span><span class="sxs-lookup"><span data-stu-id="0ad45-117">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>  
  
3.  <span data-ttu-id="0ad45-118">Выберите все три элемента управления, нажав клавишу CTRL и щелкая их в свою очередь.</span><span class="sxs-lookup"><span data-stu-id="0ad45-118">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="0ad45-119">При выборе <xref:System.Windows.Forms.SplitContainer> управлять, щелкните вешку разбивки, а не панели.</span><span class="sxs-lookup"><span data-stu-id="0ad45-119">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ad45-120">Не используйте **выбрать все** команды **изменить** меню.</span><span class="sxs-lookup"><span data-stu-id="0ad45-120">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="0ad45-121">Если это сделать, то свойство, необходимое на следующем шаге будет отсутствовать в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="0ad45-121">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>  
  
4.  <span data-ttu-id="0ad45-122">В окне **Свойства** присвойте свойству <xref:System.Windows.Forms.SplitContainer.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="0ad45-122">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5.  <span data-ttu-id="0ad45-123">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="0ad45-123">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="0ad45-124">Форма отображает двух частей пользовательского интерфейса, аналогичную, проводника Windows.</span><span class="sxs-lookup"><span data-stu-id="0ad45-124">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ad45-125">При перетаскивании разделителя панели Изменение размеров.</span><span class="sxs-lookup"><span data-stu-id="0ad45-125">When you drag the splitter, the panels resize themselves.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad45-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0ad45-126">See also</span></span>
- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="0ad45-127">Практическое руководство. Создание с несколькими областями пользовательского интерфейса с помощью Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0ad45-127">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [<span data-ttu-id="0ad45-128">Практическое руководство. Определение изменения размеров и позиционирования в окне с перемещаемым разделителем</span><span class="sxs-lookup"><span data-stu-id="0ad45-128">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [<span data-ttu-id="0ad45-129">Практическое руководство. Разделение окна по горизонтали</span><span class="sxs-lookup"><span data-stu-id="0ad45-129">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)
- [<span data-ttu-id="0ad45-130">Элемент управления SplitContainer</span><span class="sxs-lookup"><span data-stu-id="0ad45-130">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
