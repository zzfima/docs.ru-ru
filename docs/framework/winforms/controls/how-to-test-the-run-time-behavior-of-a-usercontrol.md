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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1be79d52be3b5b84938d8548a8f101e965fa9dbb
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015778"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="bc540-102">Практическое руководство. Проверка поведения элемента управления UserControl во время выполнения</span><span class="sxs-lookup"><span data-stu-id="bc540-102">How to: Test the run-time behavior of a UserControl</span></span>

<span data-ttu-id="bc540-103">При разработке <xref:System.Windows.Forms.UserControl>необходимо протестировать поведение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="bc540-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="bc540-104">Можно создать отдельный проект приложения на основе Windows и разместить элемент управления в тестовой форме, но эта процедура неудобна.</span><span class="sxs-lookup"><span data-stu-id="bc540-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="bc540-105">Более быстрый и простой способ — использовать тестовый **контейнер UserControl** , предоставляемый Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bc540-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="bc540-106">Этот тестовый контейнер запускается непосредственно из проекта библиотеки элементов управления Windows.</span><span class="sxs-lookup"><span data-stu-id="bc540-106">This test container starts directly from your Windows control library project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc540-107">Чтобы тестовый контейнер загружался <xref:System.Windows.Forms.UserControl>, элемент управления должен иметь по крайней мере один открытый конструктор.</span><span class="sxs-lookup"><span data-stu-id="bc540-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="bc540-108">Визуальный C++ элемент управления не может быть проверен с помощью **тестового контейнера UserControl**.</span><span class="sxs-lookup"><span data-stu-id="bc540-108">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="bc540-109">Проверка поведения элемента управления UserControl во время выполнения</span><span class="sxs-lookup"><span data-stu-id="bc540-109">Test the run-time behavior of a UserControl</span></span>

1. <span data-ttu-id="bc540-110">В Visual Studio создайте проект библиотеки элементов управления Windows и назовите его **тестконтаинерексампле**.</span><span class="sxs-lookup"><span data-stu-id="bc540-110">In Visual Studio, create a Windows control library project, and name it **TestContainerExample**.</span></span>

2. <span data-ttu-id="bc540-111">В **конструктор Windows Forms**перетащите <xref:System.Windows.Forms.Label> элемент управления с **панели элементов** на поверхность конструктора элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bc540-111">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="bc540-112">Нажмите клавишу **F5** , чтобы выполнить сборку проекта и запустить **тестовый контейнер UserControl**.</span><span class="sxs-lookup"><span data-stu-id="bc540-112">Press **F5** to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="bc540-113">Тестовый контейнер появится <xref:System.Windows.Forms.UserControl> в области **просмотра** .</span><span class="sxs-lookup"><span data-stu-id="bc540-113">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="bc540-114">Выберите свойство, отображаемое <xref:System.Windows.Forms.PropertyGrid> в элементе управления справа от области **просмотра.** <xref:System.Windows.Forms.Control.BackColor%2A></span><span class="sxs-lookup"><span data-stu-id="bc540-114">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="bc540-115">Измените его значение на **контролдарк**.</span><span class="sxs-lookup"><span data-stu-id="bc540-115">Change its value to **ControlDark**.</span></span> <span data-ttu-id="bc540-116">Обратите внимание, что элемент управления превращается в более темный цвет.</span><span class="sxs-lookup"><span data-stu-id="bc540-116">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="bc540-117">Попробуйте изменить другие значения свойств и обратите внимание на то, как это влияет на ваш элемент управления.</span><span class="sxs-lookup"><span data-stu-id="bc540-117">Try changing other property values and observe the effect on your control.</span></span>

5. <span data-ttu-id="bc540-118">Установите флажок **закрепить пользовательский элемент управления** под областью **просмотра** .</span><span class="sxs-lookup"><span data-stu-id="bc540-118">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="bc540-119">Обратите внимание, что размер элемента управления изменяется для заполнения области.</span><span class="sxs-lookup"><span data-stu-id="bc540-119">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="bc540-120">Измените размер тестового контейнера и убедитесь, что размер элемента управления изменяется с помощью панели.</span><span class="sxs-lookup"><span data-stu-id="bc540-120">Resize the test container and observe that the control is resized with the pane.</span></span>

6. <span data-ttu-id="bc540-121">Закройте тестовый контейнер.</span><span class="sxs-lookup"><span data-stu-id="bc540-121">Close the test container.</span></span>

7. <span data-ttu-id="bc540-122">Добавьте еще один пользовательский элемент управления в проект **тестконтаинерексампле** .</span><span class="sxs-lookup"><span data-stu-id="bc540-122">Add another user control to the **TestContainerExample** project.</span></span>

8. <span data-ttu-id="bc540-123">В **конструктор Windows Forms**перетащите <xref:System.Windows.Forms.Button> элемент управления с **панели элементов** на поверхность конструктора элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bc540-123">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>

9. <span data-ttu-id="bc540-124">Нажмите клавишу **F5** , чтобы выполнить сборку проекта и запустить тестовый контейнер.</span><span class="sxs-lookup"><span data-stu-id="bc540-124">Press **F5** to build the project and run the test container.</span></span>

10. <span data-ttu-id="bc540-125">Щелкните<xref:System.Windows.Forms.ComboBox> **элемент управления выбор пользователя** , чтобы переключиться между двумя пользовательскими элементами управления.</span><span class="sxs-lookup"><span data-stu-id="bc540-125">Click the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>

## <a name="test-user-controls-from-another-project"></a><span data-ttu-id="bc540-126">Тестирование пользовательских элементов управления из другого проекта</span><span class="sxs-lookup"><span data-stu-id="bc540-126">Test user controls from another project</span></span>

<span data-ttu-id="bc540-127">Вы можете протестировать пользовательские элементы управления из других проектов в тестовом контейнере текущего проекта.</span><span class="sxs-lookup"><span data-stu-id="bc540-127">You can test user controls from other projects in your current project's test container.</span></span>

1. <span data-ttu-id="bc540-128">В Visual Studio создайте проект библиотеки элементов управления Windows и назовите его **TestContainerExample2**.</span><span class="sxs-lookup"><span data-stu-id="bc540-128">In Visual Studio, create a Windows control library project, and name it **TestContainerExample2**.</span></span>

2. <span data-ttu-id="bc540-129">В **конструктор Windows Forms**перетащите <xref:System.Windows.Forms.RadioButton> элемент управления с **панели элементов** на поверхность конструктора элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bc540-129">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="bc540-130">Нажмите клавишу **F5** , чтобы выполнить сборку проекта и запустить тестовый контейнер.</span><span class="sxs-lookup"><span data-stu-id="bc540-130">Press **F5** to build the project and run the test container.</span></span> <span data-ttu-id="bc540-131">Тестовый контейнер появится <xref:System.Windows.Forms.UserControl> в области **просмотра** .</span><span class="sxs-lookup"><span data-stu-id="bc540-131">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="bc540-132">Нажмите кнопку **загрузить** .</span><span class="sxs-lookup"><span data-stu-id="bc540-132">Click the **Load** button.</span></span>

5. <span data-ttu-id="bc540-133">В диалоговом окне **Открыть** перейдите к файлу **тестконтаинерексампле**. dll, созданному в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="bc540-133">In the **Open** dialog box, navigate to **TestContainerExample**.dll, which you built in the previous procedure.</span></span> <span data-ttu-id="bc540-134">Выберите **тестконтаинерексампле**. dll и нажмите кнопку " **Открыть** ", чтобы загрузить пользовательские элементы управления.</span><span class="sxs-lookup"><span data-stu-id="bc540-134">Select **TestContainerExample**.dll and click the **Open** button to load the user controls</span></span>

6. <span data-ttu-id="bc540-135">Используйте<xref:System.Windows.Forms.ComboBox> **элемент управления выбор пользователя** для переключения между двумя пользовательскими элементами управления из проекта **тестконтаинерексампле** .</span><span class="sxs-lookup"><span data-stu-id="bc540-135">Use the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc540-136">См. также</span><span class="sxs-lookup"><span data-stu-id="bc540-136">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="bc540-137">Практическое руководство. Создание составных элементов управления</span><span class="sxs-lookup"><span data-stu-id="bc540-137">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="bc540-138">Пошаговое руководство: Создание составного элемента управления</span><span class="sxs-lookup"><span data-stu-id="bc540-138">Walkthrough: Authoring a Composite Control</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- <span data-ttu-id="bc540-139">[Конструктор пользовательских элементов управления](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bc540-139">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
