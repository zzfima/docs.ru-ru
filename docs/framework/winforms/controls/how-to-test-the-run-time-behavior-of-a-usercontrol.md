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
ms.openlocfilehash: 110036e5031a2956375b1edf0689237661522d39
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180208"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="dead4-102">Практическое руководство. Проверка поведения элемента управления UserControl во время выполнения</span><span class="sxs-lookup"><span data-stu-id="dead4-102">How to: Test the run-time behavior of a UserControl</span></span>

<span data-ttu-id="dead4-103">При разработке <xref:System.Windows.Forms.UserControl> необходимо проверить его поведение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="dead4-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="dead4-104">Можно создать отдельный проект приложения на основе Windows и разместить элемент управления в тестовой форме, но эта процедура неудобна.</span><span class="sxs-lookup"><span data-stu-id="dead4-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="dead4-105">Более быстрый и простой способ — использовать **тестовый контейнер UserControl** , предоставляемый Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="dead4-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="dead4-106">Этот тестовый контейнер запускается непосредственно из проекта библиотеки элементов управления Windows.</span><span class="sxs-lookup"><span data-stu-id="dead4-106">This test container starts directly from your Windows control library project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dead4-107">Чтобы тестовый контейнер загружал <xref:System.Windows.Forms.UserControl>, элемент управления должен иметь по крайней мере один открытый конструктор.</span><span class="sxs-lookup"><span data-stu-id="dead4-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="dead4-108">Визуальный C++ элемент управления не может быть проверен с помощью **тестового контейнера UserControl**.</span><span class="sxs-lookup"><span data-stu-id="dead4-108">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="dead4-109">Проверка поведения элемента управления UserControl во время выполнения</span><span class="sxs-lookup"><span data-stu-id="dead4-109">Test the run-time behavior of a UserControl</span></span>

1. <span data-ttu-id="dead4-110">В Visual Studio создайте проект библиотеки элементов управления Windows и назовите его **тестконтаинерексампле**.</span><span class="sxs-lookup"><span data-stu-id="dead4-110">In Visual Studio, create a Windows control library project, and name it **TestContainerExample**.</span></span>

2. <span data-ttu-id="dead4-111">В **конструктор Windows Forms**перетащите элемент управления <xref:System.Windows.Forms.Label> с **панели элементов** на поверхность конструктора элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dead4-111">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="dead4-112">Нажмите клавишу <kbd>F5</kbd> , чтобы выполнить сборку проекта и запустить **тестовый контейнер UserControl**.</span><span class="sxs-lookup"><span data-stu-id="dead4-112">Press <kbd>F5</kbd> to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="dead4-113">Тестовый контейнер отобразится с <xref:System.Windows.Forms.UserControl> в области **просмотра** .</span><span class="sxs-lookup"><span data-stu-id="dead4-113">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="dead4-114">Выберите свойство <xref:System.Windows.Forms.Control.BackColor%2A>, отображаемое в элементе управления <xref:System.Windows.Forms.PropertyGrid> справа от области **просмотра** .</span><span class="sxs-lookup"><span data-stu-id="dead4-114">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="dead4-115">Измените его значение на **контролдарк**.</span><span class="sxs-lookup"><span data-stu-id="dead4-115">Change its value to **ControlDark**.</span></span> <span data-ttu-id="dead4-116">Обратите внимание, что элемент управления превращается в более темный цвет.</span><span class="sxs-lookup"><span data-stu-id="dead4-116">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="dead4-117">Попробуйте изменить другие значения свойств и обратите внимание на то, как это влияет на ваш элемент управления.</span><span class="sxs-lookup"><span data-stu-id="dead4-117">Try changing other property values and observe the effect on your control.</span></span>

5. <span data-ttu-id="dead4-118">Установите флажок **закрепить пользовательский элемент управления** под областью **просмотра** .</span><span class="sxs-lookup"><span data-stu-id="dead4-118">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="dead4-119">Обратите внимание, что размер элемента управления изменяется для заполнения области.</span><span class="sxs-lookup"><span data-stu-id="dead4-119">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="dead4-120">Измените размер тестового контейнера и убедитесь, что размер элемента управления изменяется с помощью панели.</span><span class="sxs-lookup"><span data-stu-id="dead4-120">Resize the test container and observe that the control is resized with the pane.</span></span>

6. <span data-ttu-id="dead4-121">Закройте тестовый контейнер.</span><span class="sxs-lookup"><span data-stu-id="dead4-121">Close the test container.</span></span>

7. <span data-ttu-id="dead4-122">Добавьте еще один пользовательский элемент управления в проект **тестконтаинерексампле** .</span><span class="sxs-lookup"><span data-stu-id="dead4-122">Add another user control to the **TestContainerExample** project.</span></span>

8. <span data-ttu-id="dead4-123">В **конструктор Windows Forms**перетащите элемент управления <xref:System.Windows.Forms.Button> с **панели элементов** на поверхность конструктора элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dead4-123">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>

9. <span data-ttu-id="dead4-124">Нажмите клавишу <kbd>F5</kbd> , чтобы выполнить сборку проекта и запустить тестовый контейнер.</span><span class="sxs-lookup"><span data-stu-id="dead4-124">Press <kbd>F5</kbd> to build the project and run the test container.</span></span>

10. <span data-ttu-id="dead4-125">Нажмите кнопку **выбрать пользовательский элемент управления** <xref:System.Windows.Forms.ComboBox>, чтобы переключиться между двумя пользовательскими элементами управления.</span><span class="sxs-lookup"><span data-stu-id="dead4-125">Click the **Select User Control** <xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>

## <a name="test-user-controls-from-another-project"></a><span data-ttu-id="dead4-126">Тестирование пользовательских элементов управления из другого проекта</span><span class="sxs-lookup"><span data-stu-id="dead4-126">Test user controls from another project</span></span>

<span data-ttu-id="dead4-127">Вы можете протестировать пользовательские элементы управления из других проектов в тестовом контейнере текущего проекта.</span><span class="sxs-lookup"><span data-stu-id="dead4-127">You can test user controls from other projects in your current project's test container.</span></span>

1. <span data-ttu-id="dead4-128">В Visual Studio создайте проект библиотеки элементов управления Windows и назовите его **TestContainerExample2**.</span><span class="sxs-lookup"><span data-stu-id="dead4-128">In Visual Studio, create a Windows control library project, and name it **TestContainerExample2**.</span></span>

2. <span data-ttu-id="dead4-129">В **конструктор Windows Forms**перетащите элемент управления <xref:System.Windows.Forms.RadioButton> с **панели элементов** на поверхность конструктора элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dead4-129">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>

3. <span data-ttu-id="dead4-130">Нажмите клавишу <kbd>F5</kbd> , чтобы выполнить сборку проекта и запустить тестовый контейнер.</span><span class="sxs-lookup"><span data-stu-id="dead4-130">Press <kbd>F5</kbd> to build the project and run the test container.</span></span> <span data-ttu-id="dead4-131">Тестовый контейнер отобразится с <xref:System.Windows.Forms.UserControl> в области **просмотра** .</span><span class="sxs-lookup"><span data-stu-id="dead4-131">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>

4. <span data-ttu-id="dead4-132">Нажмите кнопку **загрузить** .</span><span class="sxs-lookup"><span data-stu-id="dead4-132">Click the **Load** button.</span></span>

5. <span data-ttu-id="dead4-133">В диалоговом окне **Открыть** перейдите к файлу *тестконтаинерексампле. dll*, созданному в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="dead4-133">In the **Open** dialog box, navigate to *TestContainerExample.dll*, which you built in the previous procedure.</span></span> <span data-ttu-id="dead4-134">Выберите *тестконтаинерексампле. dll* и нажмите кнопку **Открыть** , чтобы загрузить пользовательские элементы управления.</span><span class="sxs-lookup"><span data-stu-id="dead4-134">Select *TestContainerExample.dll* and click the **Open** button to load the user controls.</span></span>

6. <span data-ttu-id="dead4-135">Для переключения между двумя пользовательскими элементами управления из проекта **тестконтаинерексампле** используется параметр **Выбор пользовательского элемента управления** <xref:System.Windows.Forms.ComboBox>.</span><span class="sxs-lookup"><span data-stu-id="dead4-135">Use the **Select User Control** <xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>

## <a name="see-also"></a><span data-ttu-id="dead4-136">См. также</span><span class="sxs-lookup"><span data-stu-id="dead4-136">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <span data-ttu-id="dead4-137">[Практическое руководство. Создание составных элементов управления @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="dead4-137">[How to: Author Composite Controls](how-to-author-composite-controls.md)</span></span>
- <span data-ttu-id="dead4-138">[Пошаговое руководство: Создание составного элемента управления @ no__t-0</span><span class="sxs-lookup"><span data-stu-id="dead4-138">[Walkthrough: Authoring a Composite Control](walkthrough-authoring-a-composite-control-with-visual-csharp.md)</span></span>
- <span data-ttu-id="dead4-139">[Конструктор пользовательских элементов управления](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dead4-139">[User Control Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))</span></span>
