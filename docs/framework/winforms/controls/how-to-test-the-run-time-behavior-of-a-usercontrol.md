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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: be6c913c43e3559806bc9f38a9c3152b544e4c07
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73455535"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="9821e-102">Как проверить поведение пользовательского элемента управления во время выполнения</span><span class="sxs-lookup"><span data-stu-id="9821e-102">How to: Test the run-time behavior of a UserControl</span></span>

<span data-ttu-id="9821e-103">При разработке <xref:System.Windows.Forms.UserControl>необходимо протестировать его поведение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9821e-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="9821e-104">Можно создать отдельный проект приложения на основе Windows и разместить элемент управления в тестовой форме, но эта процедура неудобна.</span><span class="sxs-lookup"><span data-stu-id="9821e-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="9821e-105">Более быстрый и простой способ — использовать **тестовый контейнер UserControl** , предоставляемый Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9821e-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="9821e-106">Этот тестовый контейнер запускается непосредственно из проекта библиотеки элементов управления Windows.</span><span class="sxs-lookup"><span data-stu-id="9821e-106">This test container starts directly from your Windows control library project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9821e-107">Чтобы тестовый контейнер загружал <xref:System.Windows.Forms.UserControl>, элемент управления должен иметь по крайней мере один открытый конструктор.</span><span class="sxs-lookup"><span data-stu-id="9821e-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="9821e-108">Визуальный C++ элемент управления не может быть проверен с помощью **тестового контейнера UserControl**.</span><span class="sxs-lookup"><span data-stu-id="9821e-108">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="9821e-109">Проверка поведения элемента управления UserControl во время выполнения</span><span class="sxs-lookup"><span data-stu-id="9821e-109">Test the run-time behavior of a UserControl</span></span>

1. <span data-ttu-id="9821e-110">В Visual Studio создайте проект библиотеки элементов управления Windows и назовите его **тестконтаинерексампле**.</span><span class="sxs-lookup"><span data-stu-id="9821e-110">In Visual Studio, create a Windows control library project, and name it **TestContainerExample**.</span></span>

2. <span data-ttu-id="9821e-111">В **конструктор Windows Forms**перетащите элемент управления <xref:System.Windows.Forms.Label> из **панели элементов** в область конструктора элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9821e-111">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="9821e-112">Нажмите клавишу <kbd>F5</kbd> , чтобы выполнить сборку проекта и запустить **тестовый контейнер UserControl**.</span><span class="sxs-lookup"><span data-stu-id="9821e-112">Press <kbd>F5</kbd> to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="9821e-113">Тестовый контейнер отобразится <xref:System.Windows.Forms.UserControl> в области **просмотра** .</span><span class="sxs-lookup"><span data-stu-id="9821e-113">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="9821e-114">Выберите свойство <xref:System.Windows.Forms.Control.BackColor%2A>, отображаемое в элементе управления <xref:System.Windows.Forms.PropertyGrid> справа от области **просмотра** .</span><span class="sxs-lookup"><span data-stu-id="9821e-114">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="9821e-115">Измените его значение на **контролдарк**.</span><span class="sxs-lookup"><span data-stu-id="9821e-115">Change its value to **ControlDark**.</span></span> <span data-ttu-id="9821e-116">Обратите внимание, что элемент управления превращается в более темный цвет.</span><span class="sxs-lookup"><span data-stu-id="9821e-116">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="9821e-117">Попробуйте изменить другие значения свойств и обратите внимание на то, как это влияет на ваш элемент управления.</span><span class="sxs-lookup"><span data-stu-id="9821e-117">Try changing other property values and observe the effect on your control.</span></span>

5. <span data-ttu-id="9821e-118">Установите флажок **закрепить пользовательский элемент управления** под областью **просмотра** .</span><span class="sxs-lookup"><span data-stu-id="9821e-118">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="9821e-119">Обратите внимание, что размер элемента управления изменяется для заполнения области.</span><span class="sxs-lookup"><span data-stu-id="9821e-119">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="9821e-120">Измените размер тестового контейнера и убедитесь, что размер элемента управления изменяется с помощью панели.</span><span class="sxs-lookup"><span data-stu-id="9821e-120">Resize the test container and observe that the control is resized with the pane.</span></span>

6. <span data-ttu-id="9821e-121">Закройте тестовый контейнер.</span><span class="sxs-lookup"><span data-stu-id="9821e-121">Close the test container.</span></span>

7. <span data-ttu-id="9821e-122">Добавьте еще один пользовательский элемент управления в проект **тестконтаинерексампле** .</span><span class="sxs-lookup"><span data-stu-id="9821e-122">Add another user control to the **TestContainerExample** project.</span></span>

8. <span data-ttu-id="9821e-123">В **конструктор Windows Forms**перетащите элемент управления <xref:System.Windows.Forms.Button> из **панели элементов** в область конструктора элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9821e-123">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>

9. <span data-ttu-id="9821e-124">Нажмите клавишу <kbd>F5</kbd> , чтобы выполнить сборку проекта и запустить тестовый контейнер.</span><span class="sxs-lookup"><span data-stu-id="9821e-124">Press <kbd>F5</kbd> to build the project and run the test container.</span></span>

10. <span data-ttu-id="9821e-125">Щелкните <xref:System.Windows.Forms.ComboBox> **Пользовательский элемент управления** , чтобы переключиться между двумя пользовательскими элементами управления.</span><span class="sxs-lookup"><span data-stu-id="9821e-125">Click the **Select User Control** <xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>

## <a name="test-user-controls-from-another-project"></a><span data-ttu-id="9821e-126">Тестирование пользовательских элементов управления из другого проекта</span><span class="sxs-lookup"><span data-stu-id="9821e-126">Test user controls from another project</span></span>

<span data-ttu-id="9821e-127">Вы можете протестировать пользовательские элементы управления из других проектов в тестовом контейнере текущего проекта.</span><span class="sxs-lookup"><span data-stu-id="9821e-127">You can test user controls from other projects in your current project's test container.</span></span>

1. <span data-ttu-id="9821e-128">В Visual Studio создайте проект библиотеки элементов управления Windows и назовите его **TestContainerExample2**.</span><span class="sxs-lookup"><span data-stu-id="9821e-128">In Visual Studio, create a Windows control library project, and name it **TestContainerExample2**.</span></span>

2. <span data-ttu-id="9821e-129">В **конструктор Windows Forms**перетащите элемент управления <xref:System.Windows.Forms.RadioButton> из **панели элементов** в область конструктора элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9821e-129">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="9821e-130">Нажмите клавишу <kbd>F5</kbd> , чтобы выполнить сборку проекта и запустить тестовый контейнер.</span><span class="sxs-lookup"><span data-stu-id="9821e-130">Press <kbd>F5</kbd> to build the project and run the test container.</span></span> <span data-ttu-id="9821e-131">Тестовый контейнер отобразится <xref:System.Windows.Forms.UserControl> в области **просмотра** .</span><span class="sxs-lookup"><span data-stu-id="9821e-131">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="9821e-132">Нажмите кнопку **загрузить** .</span><span class="sxs-lookup"><span data-stu-id="9821e-132">Click the **Load** button.</span></span>

5. <span data-ttu-id="9821e-133">В диалоговом окне **Открыть** перейдите к файлу *тестконтаинерексампле. dll*, созданному в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="9821e-133">In the **Open** dialog box, navigate to *TestContainerExample.dll*, which you built in the previous procedure.</span></span> <span data-ttu-id="9821e-134">Выберите *тестконтаинерексампле. dll* и нажмите кнопку **Открыть** , чтобы загрузить пользовательские элементы управления.</span><span class="sxs-lookup"><span data-stu-id="9821e-134">Select *TestContainerExample.dll* and click the **Open** button to load the user controls.</span></span>

6. <span data-ttu-id="9821e-135">Для переключения между двумя пользовательскими элементами управления из проекта **тестконтаинерексампле** используется <xref:System.Windows.Forms.ComboBox> **Выбор пользовательского элемента управления** .</span><span class="sxs-lookup"><span data-stu-id="9821e-135">Use the **Select User Control** <xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>

## <a name="see-also"></a><span data-ttu-id="9821e-136">См. также</span><span class="sxs-lookup"><span data-stu-id="9821e-136">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- [<span data-ttu-id="9821e-137">Практическое руководство. Создание составных элементов управления</span><span class="sxs-lookup"><span data-stu-id="9821e-137">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="9821e-138">Пошаговое руководство. Создание составного элемента управления</span><span class="sxs-lookup"><span data-stu-id="9821e-138">Walkthrough: Authoring a Composite Control</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- <span data-ttu-id="9821e-139">[Конструктор пользовательских элементов управления](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9821e-139">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
