---
title: Практическое руководство. Создание составных элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 42ea424507b89576df8099fd4849dd2665135a55
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459433"
---
# <a name="how-to-author-composite-controls"></a><span data-ttu-id="af820-102">Руководство. Создание составных элементов управления</span><span class="sxs-lookup"><span data-stu-id="af820-102">How to: Author composite controls</span></span>

<span data-ttu-id="af820-103">Составные элементы управления можно применять различным образом.</span><span class="sxs-lookup"><span data-stu-id="af820-103">Composite controls can be employed in many ways.</span></span> <span data-ttu-id="af820-104">Их можно создать как часть проекта приложения рабочего стола Windows и использовать только в формах проекта.</span><span class="sxs-lookup"><span data-stu-id="af820-104">You can author them as part of a Windows desktop application project, and use them only on forms in the project.</span></span> <span data-ttu-id="af820-105">Или их можно создать в проекте библиотеки элементов управления Windows, скомпилировать проект в сборку и использовать элементы управления в других проектах.</span><span class="sxs-lookup"><span data-stu-id="af820-105">Or you can author them in a Windows Control Library project, compile the project into an assembly, and use the controls in other projects.</span></span> <span data-ttu-id="af820-106">Можно даже наследовать от них и использовать визуальное наследование, чтобы быстро настроить их для специальных целей.</span><span class="sxs-lookup"><span data-stu-id="af820-106">You can even inherit from them and use visual inheritance to customize them quickly for special purposes.</span></span>

## <a name="to-author-a-composite-control"></a><span data-ttu-id="af820-107">Создание составного элемента управления</span><span class="sxs-lookup"><span data-stu-id="af820-107">To author a composite control</span></span>

1. <span data-ttu-id="af820-108">В Visual Studio создайте новый проект **приложения Windows** и назовите его **демоконтролхост**.</span><span class="sxs-lookup"><span data-stu-id="af820-108">In Visual Studio, create a new **Windows Application** project, and name it **DemoControlHost**.</span></span>

2. <span data-ttu-id="af820-109">В меню **Проект** выберите команду **Добавить пользовательский элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="af820-109">On the **Project** menu, click **Add User Control**.</span></span>

3. <span data-ttu-id="af820-110">В диалоговом окне **Добавить новый элемент** присвойте файлу класса (файлу VB или CS) имя, которое должен иметь составной элемент управления.</span><span class="sxs-lookup"><span data-stu-id="af820-110">In the **Add New Item** dialog box, give the class file (.vb or .cs file) the name you want the composite control to have.</span></span>

4. <span data-ttu-id="af820-111">Нажмите кнопку **Добавить** , чтобы создать файл класса для составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="af820-111">Select the **Add** button to create the class file for the composite control.</span></span>

5. <span data-ttu-id="af820-112">Добавьте элементы управления с **панели элементов** на поверхность составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="af820-112">Add controls from the **Toolbox** to the composite control surface.</span></span>

6. <span data-ttu-id="af820-113">Поместите код в соответствующие процедуры для обработки событий, вызываемых составным элементом управления или входящими в его состав элементами управления.</span><span class="sxs-lookup"><span data-stu-id="af820-113">Place code in event procedures, to handle events raised by the composite control or by its constituent controls.</span></span>

7. <span data-ttu-id="af820-114">Закройте конструктор для составного элемента управления и сохраните файл по запросу.</span><span class="sxs-lookup"><span data-stu-id="af820-114">Close the designer for the composite control, and save the file when you are prompted.</span></span>

8. <span data-ttu-id="af820-115">В меню **Сборка** выберите **Собрать решение**.</span><span class="sxs-lookup"><span data-stu-id="af820-115">On the **Build** menu, click **Build Solution**.</span></span>

     <span data-ttu-id="af820-116">Проект необходимо собрать, чтобы пользовательские элементы управления появились на **панели элементов**.</span><span class="sxs-lookup"><span data-stu-id="af820-116">The project must be built in order for custom controls to appear in the **Toolbox**.</span></span>

9. <span data-ttu-id="af820-117">Для добавления экземпляров элемента управления в `Form1` используйте вкладку **DemoControlHost** на **панели элементов**.</span><span class="sxs-lookup"><span data-stu-id="af820-117">Use the **DemoControlHost** tab of the **Toolbox** to add instances of your control to `Form1`.</span></span>

## <a name="to-author-a-control-class-library"></a><span data-ttu-id="af820-118">Разработка библиотеки классов элементов управления</span><span class="sxs-lookup"><span data-stu-id="af820-118">To author a control class library</span></span>

1. <span data-ttu-id="af820-119">Откройте новый проект **библиотеки элементов управления Windows**.</span><span class="sxs-lookup"><span data-stu-id="af820-119">Open a new **Windows Control Library** project.</span></span>

     <span data-ttu-id="af820-120">По умолчанию проект содержит составной элемент управления.</span><span class="sxs-lookup"><span data-stu-id="af820-120">By default, the project contains a composite control.</span></span>

2. <span data-ttu-id="af820-121">Добавьте элементы управления и код, как описано в предыдущей процедуре.</span><span class="sxs-lookup"><span data-stu-id="af820-121">Add controls and code as described in the procedure above.</span></span>

3. <span data-ttu-id="af820-122">Выберите элемент управления, который не должны изменять производные классы, и установите для свойства **Модификаторы** этого элемента управления значение **Закрытый**.</span><span class="sxs-lookup"><span data-stu-id="af820-122">Choose a control you do not want inheriting classes to change, and set the **Modifiers** property of this control to **Private**.</span></span>

4. <span data-ttu-id="af820-123">Построение библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="af820-123">Build the DLL.</span></span>

## <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a><span data-ttu-id="af820-124">Наследование от составного элемента управления в библиотеке классов элементов управления</span><span class="sxs-lookup"><span data-stu-id="af820-124">To inherit from a composite control in a control class library</span></span>

1. <span data-ttu-id="af820-125">В меню **Файл** наведите указатель мыши на **Добавить** и выберите **Новый проект** для добавления нового проекта **приложения Windows** в решение.</span><span class="sxs-lookup"><span data-stu-id="af820-125">On the **File** menu, point to **Add** and select **New Project** to add a new **Windows Application** project to the solution.</span></span>

2. <span data-ttu-id="af820-126">В **обозревателе решений** щелкните правой кнопкой мыши папку **Ссылки** для нового проекта и выберите **Добавить ссылку**, чтобы открыть диалоговое окно **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="af820-126">In **Solution Explorer**, right-click the **References** folder for the new project and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>

3. <span data-ttu-id="af820-127">Перейдите на вкладку **Проекты** и дважды щелкните проект библиотеки элементов управления.</span><span class="sxs-lookup"><span data-stu-id="af820-127">Select the **Projects** tab and double-click your control library project.</span></span>

4. <span data-ttu-id="af820-128">В меню **Сборка** выберите **Собрать решение**.</span><span class="sxs-lookup"><span data-stu-id="af820-128">On the **Build** menu, click **Build Solution**.</span></span>

5. <span data-ttu-id="af820-129">В **обозревателе решений** щелкните правой кнопкой мыши проект библиотеки элементов управления и выберите пункт **Добавить новый элемент** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="af820-129">In **Solution Explorer**, right-click your control library project and select **Add New Item** from the shortcut menu.</span></span>

6. <span data-ttu-id="af820-130">Выберите шаблон **Производный пользовательский элемент управления** в диалоговом окне **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="af820-130">Select the **Inherited User Control** template from the **Add New Item** dialog box.</span></span>

7. <span data-ttu-id="af820-131">В диалоговом окне **Выбор компонентов для наследования** дважды щелкните элемент управления, от которого должно производиться наследование.</span><span class="sxs-lookup"><span data-stu-id="af820-131">In the **Inheritance Picker** dialog box, double-click the control you want to inherit from.</span></span>

     <span data-ttu-id="af820-132">В ваш проект будет добавлен новый элемент управления.</span><span class="sxs-lookup"><span data-stu-id="af820-132">A new control is added to your project.</span></span>

8. <span data-ttu-id="af820-133">Откройте визуальный конструктор для нового элемента управления и добавьте дополнительные вложенные элементы управления.</span><span class="sxs-lookup"><span data-stu-id="af820-133">Open the visual designer for the new control and add additional constituent controls.</span></span>

     <span data-ttu-id="af820-134">Вы увидите вложенные элементы управления, унаследованные от составного элемента управления в библиотеке DLL, и сможете изменить свойства элементов управления, для свойства **Модификаторы** которых установлено значение **Открытый**.</span><span class="sxs-lookup"><span data-stu-id="af820-134">You can see the constituent controls that were inherited from the composite control in your DLL, and you can alter the properties of controls whose **Modifiers** property is **Public**.</span></span> <span data-ttu-id="af820-135">Свойства элемента управления, для свойства **Модификаторы** которого установлено значение **Закрытый**, менять нельзя.</span><span class="sxs-lookup"><span data-stu-id="af820-135">You cannot change the properties of the control whose **Modifiers** property is **Private**.</span></span>

## <a name="see-also"></a><span data-ttu-id="af820-136">См. также</span><span class="sxs-lookup"><span data-stu-id="af820-136">See also</span></span>

- [<span data-ttu-id="af820-137">Пошаговое руководство. Создание составного элемента управления</span><span class="sxs-lookup"><span data-stu-id="af820-137">Walkthrough: Authoring a Composite Control</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [<span data-ttu-id="af820-138">Пошаговое руководство. наследование от элемента управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af820-138">Walkthrough: Inheriting from a Windows Forms Control</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
- [<span data-ttu-id="af820-139">Рекомендации относительно типов элементов управления</span><span class="sxs-lookup"><span data-stu-id="af820-139">Control Type Recommendations</span></span>](control-type-recommendations.md)
- [<span data-ttu-id="af820-140">Практическое руководство. Создание элементов управления для форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af820-140">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="af820-141">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="af820-141">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
