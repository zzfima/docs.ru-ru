---
title: Пошаговое руководство. Создание профессионально оформленного элемента управления ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStripRenderer class [Windows Forms]
- toolbars [Windows Forms], walkthroughs
- ToolStrip control [Windows Forms], creating professionally styled controls
ms.assetid: b52339ae-f1d3-494e-996e-eb455614098a
ms.openlocfilehash: 64624508a50eb6e28337baa1a3600298e2c83fd7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710749"
---
# <a name="walkthrough-creating-a-professionally-styled-toolstrip-control"></a><span data-ttu-id="7a9ba-102">Пошаговое руководство. Создание профессионально оформленного элемента управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7a9ba-102">Walkthrough: Creating a Professionally Styled ToolStrip Control</span></span>
<span data-ttu-id="7a9ba-103">Можно предоставить приложения <xref:System.Windows.Forms.ToolStrip> управляет профессиональный вид и поведение, написав собственный класс, производный от <xref:System.Windows.Forms.ToolStripProfessionalRenderer> типа.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-103">You can give your application’s <xref:System.Windows.Forms.ToolStrip> controls a professional appearance and behavior by writing your own class derived from the <xref:System.Windows.Forms.ToolStripProfessionalRenderer> type.</span></span>  
  
 <span data-ttu-id="7a9ba-104">В этом пошаговом руководстве демонстрируется использование <xref:System.Windows.Forms.ToolStrip> элементы управления для создания составного элемента управления, которая напоминает **редактируемую** в Microsoft® Outlook®.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-104">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStrip> controls to create a composite control that resembles the **Navigation Pane** provided by Microsoft® Outlook®.</span></span> <span data-ttu-id="7a9ba-105">В этом пошаговом руководстве показаны следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="7a9ba-105">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="7a9ba-106">Создание проекта библиотеки элементов управления Windows.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-106">Creating a Windows Control Library project.</span></span>  
  
-   <span data-ttu-id="7a9ba-107">Проектирование StackView элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-107">Designing the StackView Control.</span></span>  
  
-   <span data-ttu-id="7a9ba-108">Реализация пользовательского модуля отрисовки.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-108">Implementing a Custom Renderer.</span></span>  
  
 <span data-ttu-id="7a9ba-109">Когда вы закончите, имеется элемент управления для повторного использования настраиваемых клиентских с профессиональный внешний вид элемента управления Microsoft Office® XP.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-109">When you are finished, you will have a reusable custom client control with the professional appearance of a Microsoft Office® XP control.</span></span>  
  
 <span data-ttu-id="7a9ba-110">Чтобы скопировать код из этого раздела единым блоком, см. раздел [Практическое руководство. Создание профессионально оформленного элемента управления ToolStrip](how-to-create-a-professionally-styled-toolstrip-control.md).</span><span class="sxs-lookup"><span data-stu-id="7a9ba-110">To copy the code in this topic as a single listing, see [How to: Create a Professionally Styled ToolStrip Control](how-to-create-a-professionally-styled-toolstrip-control.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a9ba-111">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-111">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7a9ba-112">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="7a9ba-112">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7a9ba-113">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="7a9ba-113">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7a9ba-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7a9ba-114">Prerequisites</span></span>  
 <span data-ttu-id="7a9ba-115">Для выполнения данного пошагового руководства требуется:</span><span class="sxs-lookup"><span data-stu-id="7a9ba-115">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="7a9ba-116">Разрешения, необходимые для создания и выполнения проектов приложений Windows Forms на компьютере, на котором установлена Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-116">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-a-windows-control-library-project"></a><span data-ttu-id="7a9ba-117">Создание проекта библиотеки элементов управления Windows</span><span class="sxs-lookup"><span data-stu-id="7a9ba-117">Creating a Windows Control Library Project</span></span>  
 <span data-ttu-id="7a9ba-118">Первым шагом является создание проекта библиотеки элементов управления.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-118">The first step is to create the control library project.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="7a9ba-119">Чтобы создать проект библиотеки элементов управления</span><span class="sxs-lookup"><span data-stu-id="7a9ba-119">To create the control library project</span></span>  
  
1.  <span data-ttu-id="7a9ba-120">Создайте новый проект библиотеки элементов управления Windows с именем `StackViewLibrary`.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-120">Create a new Windows Control Library project named `StackViewLibrary`.</span></span>  
  
2.  <span data-ttu-id="7a9ba-121">В **обозревателе решений**, удалите элемент управления проекта по умолчанию, удаляя исходный файл с именем «UserControl1.cs» или «UserControl1.vb» в зависимости от выбранного языка.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-121">In **Solution Explorer**, delete the project's default control by deleting the source file named "UserControl1.cs" or "UserControl1.vb", depending on your language of choice.</span></span>  
  
     <span data-ttu-id="7a9ba-122">Дополнительные сведения см. в разделе [Как Удалить, удаление и исключить элементы](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="7a9ba-122">For more information, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>  
  
3.  <span data-ttu-id="7a9ba-123">Добавьте новый <xref:System.Windows.Forms.UserControl> элемент **StackViewLibrary** проекта.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-123">Add a new <xref:System.Windows.Forms.UserControl> item to the **StackViewLibrary** project.</span></span> <span data-ttu-id="7a9ba-124">Назовите новый исходный файл базового объекта `StackView`.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-124">Give the new source file a base name of `StackView`.</span></span>  
  
## <a name="designing-the-stackview-control"></a><span data-ttu-id="7a9ba-125">Проектирование элемента управления StackView</span><span class="sxs-lookup"><span data-stu-id="7a9ba-125">Designing the StackView Control</span></span>  
 <span data-ttu-id="7a9ba-126">`StackView` Элемент управления является составного элемента управления с одним дочерним <xref:System.Windows.Forms.ToolStrip> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-126">The `StackView` control is a composite control with one child <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="7a9ba-127">Дополнительные сведения о составных элементов управления, см. в разделе [разновидности пользовательских элементов управления](varieties-of-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="7a9ba-127">For more information about composite controls, see [Varieties of Custom Controls](varieties-of-custom-controls.md).</span></span>  
  
#### <a name="to-design-the-stackview-control"></a><span data-ttu-id="7a9ba-128">Чтобы разработать элемент управления StackView</span><span class="sxs-lookup"><span data-stu-id="7a9ba-128">To design the StackView control</span></span>  
  
1.  <span data-ttu-id="7a9ba-129">Из **элементов**, перетащите <xref:System.Windows.Forms.ToolStrip> элемента управления в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStrip> control to the design surface.</span></span>  
  
2.  <span data-ttu-id="7a9ba-130">В **свойства** окне <xref:System.Windows.Forms.ToolStrip> свойства элемента управления согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-130">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStrip> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="7a9ba-131">Свойство.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-131">Property</span></span>|<span data-ttu-id="7a9ba-132">Значение</span><span class="sxs-lookup"><span data-stu-id="7a9ba-132">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="7a9ba-133">name</span><span class="sxs-lookup"><span data-stu-id="7a9ba-133">Name</span></span>|`stackStrip`|  
    |<span data-ttu-id="7a9ba-134">CanOverflow</span><span class="sxs-lookup"><span data-stu-id="7a9ba-134">CanOverflow</span></span>|`false`|  
    |<span data-ttu-id="7a9ba-135">Закрепить</span><span class="sxs-lookup"><span data-stu-id="7a9ba-135">Dock</span></span>|<xref:System.Windows.Forms.DockStyle.Bottom>|  
    |<span data-ttu-id="7a9ba-136">Шрифт</span><span class="sxs-lookup"><span data-stu-id="7a9ba-136">Font</span></span>|`Tahoma, 10pt, style=Bold`|  
    |<span data-ttu-id="7a9ba-137">Стиль захвата</span><span class="sxs-lookup"><span data-stu-id="7a9ba-137">GripStyle</span></span>|<xref:System.Windows.Forms.ToolStripGripStyle.Hidden>|  
    |<span data-ttu-id="7a9ba-138">LayoutStyle</span><span class="sxs-lookup"><span data-stu-id="7a9ba-138">LayoutStyle</span></span>|<xref:System.Windows.Forms.ToolStripLayoutStyle.VerticalStackWithOverflow>|  
    |<span data-ttu-id="7a9ba-139">Заполнение</span><span class="sxs-lookup"><span data-stu-id="7a9ba-139">Padding</span></span>|`0, 7, 0, 0`|  
    |<span data-ttu-id="7a9ba-140">Отображается как</span><span class="sxs-lookup"><span data-stu-id="7a9ba-140">RenderMode</span></span>|<xref:System.Windows.Forms.ToolStripRenderMode.Professional>|  
  
3.  <span data-ttu-id="7a9ba-141">В конструкторе Windows Forms, нажмите кнопку <xref:System.Windows.Forms.ToolStrip> элемента управления **добавить** и добавьте <xref:System.Windows.Forms.ToolStripButton> для `stackStrip` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-141">In the Windows Forms Designer, click the <xref:System.Windows.Forms.ToolStrip> control's **Add** button and add a <xref:System.Windows.Forms.ToolStripButton> to the `stackStrip` control.</span></span>  
  
4.  <span data-ttu-id="7a9ba-142">В **свойства** окне <xref:System.Windows.Forms.ToolStripButton> свойства элемента управления согласно следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-142">In the **Properties** window, set the <xref:System.Windows.Forms.ToolStripButton> control's properties according to the following table.</span></span>  
  
    |<span data-ttu-id="7a9ba-143">Свойство.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-143">Property</span></span>|<span data-ttu-id="7a9ba-144">Значение</span><span class="sxs-lookup"><span data-stu-id="7a9ba-144">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="7a9ba-145">name</span><span class="sxs-lookup"><span data-stu-id="7a9ba-145">Name</span></span>|`mailStackButton`|  
    |<span data-ttu-id="7a9ba-146">CheckOnClick</span><span class="sxs-lookup"><span data-stu-id="7a9ba-146">CheckOnClick</span></span>|<span data-ttu-id="7a9ba-147">true</span><span class="sxs-lookup"><span data-stu-id="7a9ba-147">true</span></span>|  
    |<span data-ttu-id="7a9ba-148">Свойство CheckState</span><span class="sxs-lookup"><span data-stu-id="7a9ba-148">CheckState</span></span>|<xref:System.Windows.Forms.CheckState.Checked>|  
    |<span data-ttu-id="7a9ba-149">DisplayStyle</span><span class="sxs-lookup"><span data-stu-id="7a9ba-149">DisplayStyle</span></span>|<xref:System.Windows.Forms.ToolStripItemDisplayStyle.ImageAndText>|  
    |<span data-ttu-id="7a9ba-150">ImageAlign</span><span class="sxs-lookup"><span data-stu-id="7a9ba-150">ImageAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
    |<span data-ttu-id="7a9ba-151">ImageScaling</span><span class="sxs-lookup"><span data-stu-id="7a9ba-151">ImageScaling</span></span>|<xref:System.Windows.Forms.ToolStripItemImageScaling.None>|  
    |<span data-ttu-id="7a9ba-152">ImageTransparentColor</span><span class="sxs-lookup"><span data-stu-id="7a9ba-152">ImageTransparentColor</span></span>|`238, 238, 238`|  
    |<span data-ttu-id="7a9ba-153">Поля</span><span class="sxs-lookup"><span data-stu-id="7a9ba-153">Margin</span></span>|`0, 0, 0, 0`|  
    |<span data-ttu-id="7a9ba-154">Заполнение</span><span class="sxs-lookup"><span data-stu-id="7a9ba-154">Padding</span></span>|`3, 3, 3, 3`|  
    |<span data-ttu-id="7a9ba-155">Текста</span><span class="sxs-lookup"><span data-stu-id="7a9ba-155">Text</span></span>|<span data-ttu-id="7a9ba-156">**Mail**</span><span class="sxs-lookup"><span data-stu-id="7a9ba-156">**Mail**</span></span>|  
    |<span data-ttu-id="7a9ba-157">TextAlign</span><span class="sxs-lookup"><span data-stu-id="7a9ba-157">TextAlign</span></span>|<xref:System.Drawing.ContentAlignment.MiddleLeft>|  
  
5.  <span data-ttu-id="7a9ba-158">Повторите шаг 7 для три раза <xref:System.Windows.Forms.ToolStripButton> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-158">Repeat step 7 for three more <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
     <span data-ttu-id="7a9ba-159">Присвоение имен элементам управления `calendarStackButton`, `contactsStackButton`, и `tasksStackButton`.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-159">Name the controls `calendarStackButton`, `contactsStackButton`, and `tasksStackButton`.</span></span> <span data-ttu-id="7a9ba-160">Установите для параметра <xref:System.Windows.Forms.Control.Text%2A> свойства **календаря**, **контакты**, и **задачи**, соответственно.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-160">Set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to **Calendar**, **Contacts**, and **Tasks**, respectively.</span></span>  
  
## <a name="handling-events"></a><span data-ttu-id="7a9ba-161">Обработка событий</span><span class="sxs-lookup"><span data-stu-id="7a9ba-161">Handling Events</span></span>  
 <span data-ttu-id="7a9ba-162">Важны два события сделать `StackView` корректного поведения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-162">Two events are important to make the `StackView` control behave correctly.</span></span> <span data-ttu-id="7a9ba-163">Обрабатывать <xref:System.Windows.Forms.UserControl.Load> событий, чтобы правильно разместить элемент управления.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-163">Handle the <xref:System.Windows.Forms.UserControl.Load> event to position the control correctly.</span></span> <span data-ttu-id="7a9ba-164">Обрабатывать <xref:System.Windows.Forms.ToolStripItem.Click> событий для каждого <xref:System.Windows.Forms.ToolStripButton> для предоставления `StackView` управления поведением состояния, аналогичную <xref:System.Windows.Forms.RadioButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-164">Handle the <xref:System.Windows.Forms.ToolStripItem.Click> event for each <xref:System.Windows.Forms.ToolStripButton> to give the `StackView` control state behavior similar to the <xref:System.Windows.Forms.RadioButton> control.</span></span>  
  
#### <a name="to-handle-events"></a><span data-ttu-id="7a9ba-165">Для обработки событий</span><span class="sxs-lookup"><span data-stu-id="7a9ba-165">To handle events</span></span>  
  
1.  <span data-ttu-id="7a9ba-166">В конструкторе Windows Forms выберите `StackView` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-166">In the Windows Forms Designer, select the `StackView` control.</span></span>  
  
2.  <span data-ttu-id="7a9ba-167">В окне **Свойства** выберите **События**.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-167">In the **Properties** window, click **Events**.</span></span>  
  
3.  <span data-ttu-id="7a9ba-168">Дважды щелкните событие Load для создания `StackView_Load` обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-168">Double-click the Load event to generate the `StackView_Load` event handler.</span></span>  
  
4.  <span data-ttu-id="7a9ba-169">Скопируйте и вставьте в обработчике события `StackView_Load` следующий код.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-169">In the `StackView_Load` event handler, copy and paste the following code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#3)]  
  
5.  <span data-ttu-id="7a9ba-170">В конструкторе Windows Forms выберите `mailStackButton` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-170">In the Windows Forms Designer, select the `mailStackButton` control.</span></span>  
  
6.  <span data-ttu-id="7a9ba-171">В окне **Свойства** выберите **События**.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-171">In the **Properties** window, click **Events**.</span></span>  
  
7.  <span data-ttu-id="7a9ba-172">Дважды щелкните событие Click.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-172">Double-click the Click event.</span></span>  
  
     <span data-ttu-id="7a9ba-173">Конструктор Windows Forms создает `mailStackButton_Click` обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-173">The Windows Forms Designer generates the `mailStackButton_Click` event handler.</span></span>  
  
8.  <span data-ttu-id="7a9ba-174">Переименуйте `mailStackButton_Click` в обработчике событий `stackButton_Click`.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-174">Rename the `mailStackButton_Click` event handler to `stackButton_Click`.</span></span>  
  
     <span data-ttu-id="7a9ba-175">Дополнительные сведения см. в разделе [переименование рефакторинга кода символа](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="7a9ba-175">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>  
  
9. <span data-ttu-id="7a9ba-176">Вставьте следующий код в `stackButton_Click` обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-176">Insert the following code into the `stackButton_Click` event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#4)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#4)]  
  
10. <span data-ttu-id="7a9ba-177">В конструкторе Windows Forms выберите `calendarStackButton` элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-177">In the Windows Forms Designer, select the `calendarStackButton` control.</span></span>  
  
11. <span data-ttu-id="7a9ba-178">В **свойства** окна, задайте событие Click `stackButton_Click` обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-178">In the **Properties** window, set the Click event to the `stackButton_Click` event handler.</span></span>  
  
12. <span data-ttu-id="7a9ba-179">Повторите шаги 10 и 11 for `contactsStackButton` и `tasksStackButton` элементов управления.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-179">Repeat steps 10 and 11 for the `contactsStackButton` and `tasksStackButton` controls.</span></span>  
  
## <a name="defining-icons"></a><span data-ttu-id="7a9ba-180">Определение значков</span><span class="sxs-lookup"><span data-stu-id="7a9ba-180">Defining Icons</span></span>  
 <span data-ttu-id="7a9ba-181">Каждый `StackView` кнопка имеет значок.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-181">Each `StackView` button has an associated icon.</span></span> <span data-ttu-id="7a9ba-182">Для удобства каждый значок представлен как строка в кодировке Base64, которая десериализуется до <xref:System.Drawing.Bitmap> создается из него.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-182">For convenience, each icon is represented as a Base64-encoded string, which is deserialized before a <xref:System.Drawing.Bitmap> is created from it.</span></span> <span data-ttu-id="7a9ba-183">В рабочей среде данные растрового изображения хранятся в виде ресурса и значки отображаются в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-183">In a production environment, you store bitmap data as a resource, and your icons appear in the Windows Forms Designer.</span></span> <span data-ttu-id="7a9ba-184">Дополнительные сведения см. в разделе [Как Добавление фоновых изображений в формы Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="7a9ba-184">For more information, see [How to: Add Background Images to Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dff9f95f(v=vs.100)).</span></span>  
  
#### <a name="to-define-icons"></a><span data-ttu-id="7a9ba-185">Чтобы определить значки</span><span class="sxs-lookup"><span data-stu-id="7a9ba-185">To define icons</span></span>  
  
1.  <span data-ttu-id="7a9ba-186">В редакторе кода вставьте следующий код в `StackView` определение класса.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-186">In the Code Editor, insert the following code into the `StackView` class definition.</span></span> <span data-ttu-id="7a9ba-187">Этот код инициализирует точечные рисунки для <xref:System.Windows.Forms.ToolStripButton> значков.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-187">This code initializes the bitmaps for the <xref:System.Windows.Forms.ToolStripButton> icons.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#2)]  
  
2.  <span data-ttu-id="7a9ba-188">Добавьте вызов `InitializeImages` метод в `StackView` конструктора класса.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-188">Add a call to the `InitializeImages` method in the `StackView` class constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="implementing-a-custom-renderer"></a><span data-ttu-id="7a9ba-189">Реализация пользовательского средства отрисовки</span><span class="sxs-lookup"><span data-stu-id="7a9ba-189">Implementing a Custom Renderer</span></span>  
 <span data-ttu-id="7a9ba-190">Можно настроить большинство элементов `StackView` управления, реализовав класс, производный от <xref:System.Windows.Forms.ToolStripRenderer> класса.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-190">You can customize most elements of the `StackView` control my implementing a class that derives from the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span> <span data-ttu-id="7a9ba-191">В этой процедуре вы реализуете <xref:System.Windows.Forms.ToolStripProfessionalRenderer> класс, используемый для настройки захвата и изображения градиентного фона для <xref:System.Windows.Forms.ToolStripButton> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-191">In this procedure, you will implement a <xref:System.Windows.Forms.ToolStripProfessionalRenderer> class that customizes the grip and draws gradient backgrounds for the <xref:System.Windows.Forms.ToolStripButton> controls.</span></span>  
  
#### <a name="to-implement-a-custom-renderer"></a><span data-ttu-id="7a9ba-192">Чтобы реализовать пользовательское средство отрисовки</span><span class="sxs-lookup"><span data-stu-id="7a9ba-192">To implement a custom renderer</span></span>  
  
1.  <span data-ttu-id="7a9ba-193">Вставьте следующий код в `StackView` управлять определением.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-193">Insert the following code into the `StackView` control definition.</span></span>  
  
     <span data-ttu-id="7a9ba-194">Это определение для `StackRenderer` класс, переопределяющий <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, и <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> методы для получения пользовательское оформление.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-194">This is the definition for the `StackRenderer` class, which overrides the <xref:System.Windows.Forms.ToolStripRenderer.RenderGrip>, <xref:System.Windows.Forms.ToolStripRenderer.RenderToolStripBorder>, and <xref:System.Windows.Forms.ToolStripRenderer.RenderButtonBackground> methods to produce a custom appearance.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#10)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#10)]  
  
2.  <span data-ttu-id="7a9ba-195">В `StackView` конструктора элемента управления, создайте новый экземпляр класса `StackRenderer` класса и присвойте этот экземпляр `stackStrip` элемента управления <xref:System.Windows.Forms.ToolStrip.Renderer%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-195">In the `StackView` control's constructor, create a new instance of the `StackRenderer` class and assign this instance to the `stackStrip` control's <xref:System.Windows.Forms.ToolStrip.Renderer%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#5)]
     [!code-vb[System.Windows.Forms.ToolStrip.StackView#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#5)]  
  
## <a name="testing-the-stackview-control"></a><span data-ttu-id="7a9ba-196">Тестирование элемента управления StackView</span><span class="sxs-lookup"><span data-stu-id="7a9ba-196">Testing the StackView Control</span></span>  
 <span data-ttu-id="7a9ba-197">`StackView` Элемент управления наследуется от <xref:System.Windows.Forms.UserControl> класса.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-197">The `StackView` control derives from the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="7a9ba-198">Таким образом, можно проверить элемент управления с **тестового контейнера UserControl**.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-198">Therefore, you can test the control with the **UserControl Test Container**.</span></span> <span data-ttu-id="7a9ba-199">Дополнительные сведения см. в разделе [Как Тестирование во время выполнения поведения элемента UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="7a9ba-199">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
#### <a name="to-test-the-stackview-control"></a><span data-ttu-id="7a9ba-200">Чтобы протестировать элемент управления StackView</span><span class="sxs-lookup"><span data-stu-id="7a9ba-200">To test the StackView control</span></span>  
  
1.  <span data-ttu-id="7a9ba-201">Нажмите клавишу F5, чтобы создать проект и запустить **тестовом контейнере элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-201">Press F5 to build the project and start the **UserControl Test Container**.</span></span>  
  
2.  <span data-ttu-id="7a9ba-202">Наведите указатель на кнопки `StackView` управления и нажмите кнопку для просмотра внешнего вида выбранного состояния.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-202">Move the pointer over the buttons of the `StackView` control, and then click a button to see the appearance of its selected state.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7a9ba-203">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="7a9ba-203">Next Steps</span></span>  
 <span data-ttu-id="7a9ba-204">В этом пошаговом руководстве вы создали повторно используемый пользовательский клиентский элемент управления с профессиональный внешний вид элемента управления Office XP.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-204">In this walkthrough, you have created a reusable custom client control with the professional appearance of an Office XP control.</span></span> <span data-ttu-id="7a9ba-205">Можно использовать <xref:System.Windows.Forms.ToolStrip> семейства элементов управления, для многих других целей:</span><span class="sxs-lookup"><span data-stu-id="7a9ba-205">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="7a9ba-206">Создать контекстное меню для элементов управления с <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-206">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="7a9ba-207">Дополнительные сведения см. в разделе [Общие сведения о компоненте ContextMenu](contextmenu-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="7a9ba-207">For more information, see [ContextMenu Component Overview](contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="7a9ba-208">Создайте форму с автоматически заполненные стандартным меню.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-208">Create a form with an automatically populated standard menu.</span></span> <span data-ttu-id="7a9ba-209">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание стандартных пунктов меню для формы](walkthrough-providing-standard-menu-items-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="7a9ba-209">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="7a9ba-210">Создайте форму многодокументного интерфейса (MDI) закрепленный <xref:System.Windows.Forms.ToolStrip> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="7a9ba-210">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="7a9ba-211">Дополнительные сведения см. в разделе [Как Создание формы MDI путем слияния меню и элементов управления ToolStrip](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span><span class="sxs-lookup"><span data-stu-id="7a9ba-211">For more information, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a9ba-212">См. также</span><span class="sxs-lookup"><span data-stu-id="7a9ba-212">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="7a9ba-213">Элемент управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7a9ba-213">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
- [<span data-ttu-id="7a9ba-214">Практическое руководство. Обеспечивают стандартные пункты меню в форму</span><span class="sxs-lookup"><span data-stu-id="7a9ba-214">How to: Provide Standard Menu Items to a Form</span></span>](how-to-provide-standard-menu-items-to-a-form.md)
