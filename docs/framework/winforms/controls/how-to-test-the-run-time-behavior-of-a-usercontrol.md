---
title: "Практическое руководство. Тестирование поведения элемента UserControl во время выполнения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2ce4f821a7b964b3ed2e03c795346b47bb88d618
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="f9b36-102">Практическое руководство. Тестирование поведения элемента UserControl во время выполнения</span><span class="sxs-lookup"><span data-stu-id="f9b36-102">How to: Test the Run-Time Behavior of a UserControl</span></span>
<span data-ttu-id="f9b36-103">При разработке <xref:System.Windows.Forms.UserControl>, необходимо проверить его поведение во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f9b36-103">When you develop a <xref:System.Windows.Forms.UserControl>, you need to test its run-time behavior.</span></span> <span data-ttu-id="f9b36-104">Можно создать проект отдельные приложения на основе Windows и разместить элемент управления в тестовую форму, но эта процедура неудобно.</span><span class="sxs-lookup"><span data-stu-id="f9b36-104">You can create a separate Windows-based application project and place your control on a test form, but this procedure is inconvenient.</span></span> <span data-ttu-id="f9b36-105">Более быстрым и удобным способом является использование **тестовый контейнер пользовательских элементов управления** , предоставляемые Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f9b36-105">A faster and easier way is to use the **UserControl Test Container** provided by Visual Studio.</span></span> <span data-ttu-id="f9b36-106">Тестовый контейнер запускается непосредственно из проекта библиотеки элементов управления Windows.</span><span class="sxs-lookup"><span data-stu-id="f9b36-106">This test container starts directly from your Windows control library project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f9b36-107">К контейнеру теста для загрузки вашей <xref:System.Windows.Forms.UserControl>, элемент управления должен иметь по крайней мере один открытый конструктор.</span><span class="sxs-lookup"><span data-stu-id="f9b36-107">For the test container to load your <xref:System.Windows.Forms.UserControl>, the control must have at least one public constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9b36-108">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="f9b36-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f9b36-109">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="f9b36-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f9b36-110">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="f9b36-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9b36-111">Элемент управления Visual C++ не может быть проверен с использованием **тестовый контейнер пользовательских элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="f9b36-111">A Visual C++ control cannot be tested using the **UserControl Test Container**.</span></span>  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a><span data-ttu-id="f9b36-112">Для тестирования поведения элемента UserControl во время выполнения</span><span class="sxs-lookup"><span data-stu-id="f9b36-112">To test the run-time behavior of a UserControl</span></span>  
  
1.  <span data-ttu-id="f9b36-113">Создайте проект библиотеки элементов управления Windows вызывается **TestContainerExample**.</span><span class="sxs-lookup"><span data-stu-id="f9b36-113">Create a Windows control library project called **TestContainerExample**.</span></span> <span data-ttu-id="f9b36-114">Дополнительные сведения см. в разделе [шаблон библиотеки элементов управления Windows](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span><span class="sxs-lookup"><span data-stu-id="f9b36-114">For details, see [Windows Control Library Template](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span></span>  
  
2.  <span data-ttu-id="f9b36-115">В **конструктор Windows Forms**, перетащите <xref:System.Windows.Forms.Label> управления из **элементов** область конструктора элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f9b36-115">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3.  <span data-ttu-id="f9b36-116">Нажмите клавишу F5, чтобы построить проект и запустить **тестовый контейнер пользовательских элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="f9b36-116">Press F5 to build the project and run the **UserControl Test Container**.</span></span> <span data-ttu-id="f9b36-117">Тестовый контейнер будет отображаться с вашей <xref:System.Windows.Forms.UserControl> в **предварительного просмотра** области.</span><span class="sxs-lookup"><span data-stu-id="f9b36-117">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4.  <span data-ttu-id="f9b36-118">Выберите <xref:System.Windows.Forms.Control.BackColor%2A> свойства, отображенного в <xref:System.Windows.Forms.PropertyGrid> управления справа от **предварительного просмотра** области.</span><span class="sxs-lookup"><span data-stu-id="f9b36-118">Select the <xref:System.Windows.Forms.Control.BackColor%2A> property displayed in the <xref:System.Windows.Forms.PropertyGrid> control to the right of the **Preview** pane.</span></span> <span data-ttu-id="f9b36-119">Измените его значение на `ControlDark`.</span><span class="sxs-lookup"><span data-stu-id="f9b36-119">Change its value to `ControlDark`.</span></span> <span data-ttu-id="f9b36-120">Обратите внимание, что элемента управления изменяется в более темным цветом.</span><span class="sxs-lookup"><span data-stu-id="f9b36-120">Observe that the control changes to a darker color.</span></span> <span data-ttu-id="f9b36-121">Попробуйте изменять другие значения свойства и действие на элементе управления.</span><span class="sxs-lookup"><span data-stu-id="f9b36-121">Try changing other property values and observe the effect on your control.</span></span>  
  
5.  <span data-ttu-id="f9b36-122">Нажмите кнопку **окно** расположенный ниже флажок **предварительного просмотра** области.</span><span class="sxs-lookup"><span data-stu-id="f9b36-122">Click the **Dock Fill User Control** check box below the **Preview** pane.</span></span> <span data-ttu-id="f9b36-123">Обратите внимание, что размер для заполнения области.</span><span class="sxs-lookup"><span data-stu-id="f9b36-123">Observe that the control is resized to fill the pane.</span></span> <span data-ttu-id="f9b36-124">Измените размер тестового контейнера и обратите внимание, что элемент управления при изменении размеров области.</span><span class="sxs-lookup"><span data-stu-id="f9b36-124">Resize the test container and observe that the control is resized with the pane.</span></span>  
  
6.  <span data-ttu-id="f9b36-125">Закройте тестовый контейнер.</span><span class="sxs-lookup"><span data-stu-id="f9b36-125">Close the test container.</span></span>  
  
7.  <span data-ttu-id="f9b36-126">Добавьте другой пользовательский элемент управления для **TestContainerExample** проекта.</span><span class="sxs-lookup"><span data-stu-id="f9b36-126">Add another user control to the **TestContainerExample** project.</span></span> <span data-ttu-id="f9b36-127">Дополнительные сведения см. в разделе [NIB: Практическое: Добавление существующих элементов в проект](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span><span class="sxs-lookup"><span data-stu-id="f9b36-127">For details, see [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span></span>  
  
8.  <span data-ttu-id="f9b36-128">В **конструктор Windows Forms**, перетащите <xref:System.Windows.Forms.Button> управления из **элементов** область конструктора элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f9b36-128">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the control's design surface.</span></span>  
  
9. <span data-ttu-id="f9b36-129">Нажмите клавишу F5 для построения проекта и запуска тестового контейнера.</span><span class="sxs-lookup"><span data-stu-id="f9b36-129">Press F5 to build the project and run the test container.</span></span>  
  
10. <span data-ttu-id="f9b36-130">Нажмите кнопку **выберите пользовательский элемент управления** <xref:System.Windows.Forms.ComboBox> для переключения между двумя элементами управления.</span><span class="sxs-lookup"><span data-stu-id="f9b36-130">Click the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls.</span></span>  
  
## <a name="testing-user-controls-from-another-project"></a><span data-ttu-id="f9b36-131">Тестирование пользовательского элемента управления из другого проекта</span><span class="sxs-lookup"><span data-stu-id="f9b36-131">Testing User Controls from Another Project</span></span>  
 <span data-ttu-id="f9b36-132">Пользовательские элементы управления из других проектов, можно проверить в тестовом контейнере текущего проекта.</span><span class="sxs-lookup"><span data-stu-id="f9b36-132">You can test user controls from other projects in your current project's test container.</span></span>  
  
#### <a name="to-test-user-controls-from-another-project"></a><span data-ttu-id="f9b36-133">Для проверки пользовательских элементов управления из другого проекта</span><span class="sxs-lookup"><span data-stu-id="f9b36-133">To test user controls from another project</span></span>  
  
1.  <span data-ttu-id="f9b36-134">Создайте проект библиотеки элементов управления Windows вызывается **TestContainerExample2**.</span><span class="sxs-lookup"><span data-stu-id="f9b36-134">Create a Windows control library project called **TestContainerExample2**.</span></span> <span data-ttu-id="f9b36-135">Дополнительные сведения см. в разделе [шаблон библиотеки элементов управления Windows](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span><span class="sxs-lookup"><span data-stu-id="f9b36-135">For details, see [Windows Control Library Template](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span></span>  
  
2.  <span data-ttu-id="f9b36-136">В **конструктор Windows Forms**, перетащите <xref:System.Windows.Forms.RadioButton> управления из **элементов** область конструктора элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f9b36-136">In the **Windows Forms Designer**, drag a <xref:System.Windows.Forms.RadioButton> control from the **Toolbox** onto the control's design surface.</span></span>  
  
3.  <span data-ttu-id="f9b36-137">Нажмите клавишу F5 для построения проекта и запуска тестового контейнера.</span><span class="sxs-lookup"><span data-stu-id="f9b36-137">Press F5 to build the project and run the test container.</span></span> <span data-ttu-id="f9b36-138">Тестовый контейнер будет отображаться с вашей <xref:System.Windows.Forms.UserControl> в **предварительного просмотра** области.</span><span class="sxs-lookup"><span data-stu-id="f9b36-138">The test container appears with your <xref:System.Windows.Forms.UserControl> in the **Preview** pane.</span></span>  
  
4.  <span data-ttu-id="f9b36-139">Нажмите кнопку **нагрузки** кнопки.</span><span class="sxs-lookup"><span data-stu-id="f9b36-139">Click the **Load** button.</span></span>  
  
5.  <span data-ttu-id="f9b36-140">В **откройте** диалоговом окне перейдите к **TestContainerExample**DLL-файл, который создан в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="f9b36-140">In the **Open** dialog box, navigate to **TestContainerExample**.dll, which you built in the previous procedure.</span></span> <span data-ttu-id="f9b36-141">Выберите **TestContainerExample**DLL-файл и нажмите кнопку **откройте** кнопку, чтобы загрузить пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="f9b36-141">Select **TestContainerExample**.dll and click the **Open** button to load the user controls</span></span>  
  
6.  <span data-ttu-id="f9b36-142">Используйте **выберите пользовательский элемент управления** <xref:System.Windows.Forms.ComboBox> для переключения между двумя элементами управления из **TestContainerExample** проекта.</span><span class="sxs-lookup"><span data-stu-id="f9b36-142">Use the **Select User Control**<xref:System.Windows.Forms.ComboBox> to switch between the two user controls from the **TestContainerExample** project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9b36-143">См. также</span><span class="sxs-lookup"><span data-stu-id="f9b36-143">See Also</span></span>  
 <xref:System.Windows.Forms.UserControl>  
 [<span data-ttu-id="f9b36-144">Практическое руководство. Создание составных элементов управления</span><span class="sxs-lookup"><span data-stu-id="f9b36-144">How to: Author Composite Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 [<span data-ttu-id="f9b36-145">Пошаговое руководство. Создание составного элемента управления с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f9b36-145">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [<span data-ttu-id="f9b36-146">Пошаговое руководство. Создание составного элемента управления с помощью C#</span><span class="sxs-lookup"><span data-stu-id="f9b36-146">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [<span data-ttu-id="f9b36-147">Конструктор пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="f9b36-147">User Control Designer</span></span>](http://msdn.microsoft.com/en-us/2abb9eec-ba32-45cb-b73d-8b52a8bd6bf1)
