---
title: Практическое руководство. Тестирование поведения элемента UserControl во время выполнения
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: 48531ab1ef3b30b6516e3f2e7b5858a8884cbfe8
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211710"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="90496-102">Практическое руководство. Тестирование во время выполнения поведения элемента UserControl</span><span class="sxs-lookup"><span data-stu-id="90496-102">How to: Test the run-time behavior of a UserControl</span></span>

<span data-ttu-id="90496-103">При разработке <xref:System.Windows.Forms.UserControl>, необходимо проверить его поведение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="90496-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="90496-104">Можно создать проект отдельные приложения на основе Windows и разместить элемент управления в тестовую форму, но эта процедура неудобно.</span><span class="sxs-lookup"><span data-stu-id="90496-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="90496-105">Быстрый и удобный способ — использовать **тестовом контейнере элементов управления** , предоставляемые Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="90496-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="90496-106">Тестовый контейнер запускается непосредственно из проект библиотеки элементов управления Windows.</span><span class="sxs-lookup"><span data-stu-id="90496-106">This test container starts directly from your Windows control library project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90496-107">К контейнеру теста для загрузки вашего <xref:System.Windows.Forms.UserControl>, элемент управления должен иметь по крайней мере один открытый конструктор.</span><span class="sxs-lookup"><span data-stu-id="90496-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="90496-108">Элемент управления Visual C++ не может быть проверен с использованием **тестовом контейнере элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="90496-108">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="90496-109">Тестирование во время выполнения поведения элемента UserControl</span><span class="sxs-lookup"><span data-stu-id="90496-109">Test the run-time behavior of a UserControl</span></span>

1. <span data-ttu-id="90496-110">В Visual Studio создайте проект библиотеки элементов управления Windows вызывается **TestContainerExample**.</span><span class="sxs-lookup"><span data-stu-id="90496-110">In Visual Studio, create a Windows control library project called **TestContainerExample**.</span></span> <span data-ttu-id="90496-111">Дополнительные сведения см. в разделе [шаблон библиотеки элементов управления Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="90496-111">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="90496-112">В **конструктор Windows Forms**, перетащите <xref:System.Windows.Forms.Label> управления из **элементов** в область конструктора элемента управления.</span><span class="sxs-lookup"><span data-stu-id="90496-112">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="90496-113">Нажмите клавишу **F5** для сборки проекта и запуска **тестовом контейнере элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="90496-113">Press **F5** to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="90496-114">Тестовый контейнер будет отображаться с вашей <xref:System.Windows.Forms.UserControl> в **предварительной версии** области.</span><span class="sxs-lookup"><span data-stu-id="90496-114">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="90496-115">Выберите <xref:System.Windows.Forms.Control.BackColor%2A> свойство, отображаемое в <xref:System.Windows.Forms.PropertyGrid> управления справа от **предварительной версии** области.</span><span class="sxs-lookup"><span data-stu-id="90496-115">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="90496-116">Измените его значение на `ControlDark`.</span><span class="sxs-lookup"><span data-stu-id="90496-116">Change its value to `ControlDark`.</span></span> <span data-ttu-id="90496-117">Обратите внимание, что элемент управления примет более темным цветом.</span><span class="sxs-lookup"><span data-stu-id="90496-117">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="90496-118">Попробуйте изменить значения других свойств и понаблюдайте за влияние на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="90496-118">Try changing other property values and observe the effect on your control.</span></span>

5. <span data-ttu-id="90496-119">Нажмите кнопку **окно** флажок ниже **предварительной версии** области.</span><span class="sxs-lookup"><span data-stu-id="90496-119">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="90496-120">Обратите внимание, что элемент управления изменяется для заполнения области.</span><span class="sxs-lookup"><span data-stu-id="90496-120">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="90496-121">Измените размер тестового контейнера и обратите внимание, что элемент управления при изменении размеров области.</span><span class="sxs-lookup"><span data-stu-id="90496-121">Resize the test container and observe that the control is resized with the pane.</span></span>

6. <span data-ttu-id="90496-122">Закройте тестовый контейнер.</span><span class="sxs-lookup"><span data-stu-id="90496-122">Close the test container.</span></span>

7. <span data-ttu-id="90496-123">Добавить другой пользовательский элемент управления для **TestContainerExample** проекта.</span><span class="sxs-lookup"><span data-stu-id="90496-123">Add another user control to the **TestContainerExample** project.</span></span> <span data-ttu-id="90496-124">Подробную информацию см. в разделе [Практическое руководство. Добавление существующих элементов в проект](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="90496-124">For details, see [How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).</span></span>

8. <span data-ttu-id="90496-125">В **конструктор Windows Forms**, перетащите <xref:System.Windows.Forms.Button> управления из **элементов** в область конструктора элемента управления.</span><span class="sxs-lookup"><span data-stu-id="90496-125">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>

9. <span data-ttu-id="90496-126">Нажмите клавишу F5 для сборки проекта и запуска тестового контейнера.</span><span class="sxs-lookup"><span data-stu-id="90496-126">Press F5 to build the project and run the test container.</span></span>

10. <span data-ttu-id="90496-127">Нажмите кнопку **выберите пользовательский элемент управления** <xref:System.Windows.Forms.ComboBox> для переключения между двумя элементами управления.</span><span class="sxs-lookup"><span data-stu-id="90496-127">Click the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>

## <a name="test-user-controls-from-another-project"></a><span data-ttu-id="90496-128">Проверка пользовательских элементов управления из другого проекта</span><span class="sxs-lookup"><span data-stu-id="90496-128">Test user controls from another project</span></span>

<span data-ttu-id="90496-129">Пользовательские элементы управления из других проектов можно проверить в тестовом контейнере текущего проекта.</span><span class="sxs-lookup"><span data-stu-id="90496-129">You can test user controls from other projects in your current project's test container.</span></span>

1. <span data-ttu-id="90496-130">Создайте проект библиотеки элементов управления Windows вызывается **TestContainerExample2**.</span><span class="sxs-lookup"><span data-stu-id="90496-130">Create a Windows control library project called **TestContainerExample2**.</span></span> <span data-ttu-id="90496-131">Дополнительные сведения см. в разделе [шаблон библиотеки элементов управления Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="90496-131">For details, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="90496-132">В **конструктор Windows Forms**, перетащите <xref:System.Windows.Forms.RadioButton> управления из **элементов** в область конструктора элемента управления.</span><span class="sxs-lookup"><span data-stu-id="90496-132">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="90496-133">Нажмите клавишу F5 для сборки проекта и запуска тестового контейнера.</span><span class="sxs-lookup"><span data-stu-id="90496-133">Press F5 to build the project and run the test container.</span></span> <span data-ttu-id="90496-134">Тестовый контейнер будет отображаться с вашей <xref:System.Windows.Forms.UserControl> в **предварительной версии** области.</span><span class="sxs-lookup"><span data-stu-id="90496-134">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="90496-135">Нажмите кнопку **нагрузки** кнопки.</span><span class="sxs-lookup"><span data-stu-id="90496-135">Click the **Load** button.</span></span>

5. <span data-ttu-id="90496-136">В **откройте** диалоговом окне перейдите к **TestContainerExample**.dll, который встроен в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="90496-136">In the **Open** dialog box, navigate to **TestContainerExample**.dll, which you built in the previous procedure.</span></span> <span data-ttu-id="90496-137">Выберите **TestContainerExample**DLL-файл и нажмите кнопку **откройте** кнопку, чтобы загрузить пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="90496-137">Select **TestContainerExample**.dll and click the **Open** button to load the user controls</span></span>

6. <span data-ttu-id="90496-138">Используйте **выберите пользовательский элемент управления** <xref:System.Windows.Forms.ComboBox> для переключения между двумя элементами управления из **TestContainerExample** проекта.</span><span class="sxs-lookup"><span data-stu-id="90496-138">Use the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>

## <a name="see-also"></a><span data-ttu-id="90496-139">См. также</span><span class="sxs-lookup"><span data-stu-id="90496-139">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="90496-140">Практическое руководство. Создание составных элементов управления</span><span class="sxs-lookup"><span data-stu-id="90496-140">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="90496-141">Пошаговое руководство: Создание составного элемента управления с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="90496-141">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [<span data-ttu-id="90496-142">Пошаговое руководство: Создание составного элемента управления с помощью VisualC#</span><span class="sxs-lookup"><span data-stu-id="90496-142">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- <span data-ttu-id="90496-143">[Конструктор пользовательских элементов управления](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="90496-143">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
