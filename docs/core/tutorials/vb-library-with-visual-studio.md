---
title: Создание библиотеки классов Visual Basic .NET Standard в Visual Studio 2017
description: Узнайте, как создать библиотеку классов .NET Standard, написанную на языке Visual Basic, с помощью Visual Studio 2017
ms.date: 08/07/2017
dev_langs:
- vb
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 1daab377abe3b6b89f73ed48eafadeae4d7eee77
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73100868"
---
# <a name="build-a-net-standard-library-with-visual-basic-and-the-net-core-sdk-in-visual-studio-2017"></a><span data-ttu-id="0a2d0-103">Создание библиотеки .NET Standard с помощью Visual Basic и пакета SDK для .NET Core в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="0a2d0-103">Build a .NET Standard library with Visual Basic and the .NET Core SDK in Visual Studio 2017</span></span>

<span data-ttu-id="0a2d0-104">*Библиотека классов* определяет типы и методы, которые могут быть вызваны из любого приложения.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="0a2d0-105">Библиотеку классов, предназначенную для .NET Standard 2.0, можно вызывать из любой реализации .NET, которая поддерживает эту версию .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-105">A class library that targets the .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of the .NET Standard.</span></span> <span data-ttu-id="0a2d0-106">Когда вы завершите создание библиотеки классов, вы сможете по своему усмотрению распространять ее как независимый компонент или включить в состав одного или нескольких приложений.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="0a2d0-107">Список версий .NET Standard и поддерживаемых ими платформ см. в разделе [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="0a2d0-107">For a list of the .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="0a2d0-108">В этой статье вы создадите простую служебную библиотеку с одним методом для обработки строк.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="0a2d0-109">Вы реализуете его как [метод расширения](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md), чтобы вызывать его так же, как любой член класса <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-109">You'll implement it as an [extension method](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="creating-a-class-library-solution"></a><span data-ttu-id="0a2d0-110">Создание решения для библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="0a2d0-110">Creating a class library solution</span></span>

<span data-ttu-id="0a2d0-111">Начнем с создания решения для нашего проекта библиотеки классов и связанных с ней проектов.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-111">Start by creating a solution for your class library project and its related projects.</span></span> <span data-ttu-id="0a2d0-112">Решение Visual Studio служит контейнером для одного или нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-112">A Visual Studio Solution just serves as a container for one or more projects.</span></span> <span data-ttu-id="0a2d0-113">Чтобы создать решение, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-113">To create the solution:</span></span>

1. <span data-ttu-id="0a2d0-114">В строке меню Visual Studio выберите **Файл** > **Создать** > **Проект**.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-114">On the Visual Studio menu bar, choose **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="0a2d0-115">В диалоговом окне **Новый проект** разверните узел **Другие типы проектов** и выберите **Решения Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-115">In the **New Project** dialog, expand the **Other Project Types** node, and select **Visual Studio Solutions**.</span></span> <span data-ttu-id="0a2d0-116">Присвойте решению имя ClassLibraryProjects и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-116">Name the solution "ClassLibraryProjects" and select the **OK** button.</span></span>

   ![Visual Studio создает диалоговое окно нового проекта тестирования](./media/library-with-visual-studio/new-project-dialog.png)

## <a name="creating-the-class-library-project"></a><span data-ttu-id="0a2d0-118">Создание проекта для библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="0a2d0-118">Creating the class library project</span></span>

<span data-ttu-id="0a2d0-119">Теперь можно создать проект библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-119">Create your class library project:</span></span>

1. <span data-ttu-id="0a2d0-120">В **обозревателе решений** щелкните правой кнопкой мыши решение **ClassLibraryProjects** и в контекстном меню выберите **Добавить** > **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-120">In **Solution Explorer**, right-click on the **ClassLibraryProjects** solution file and from the context menu, select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="0a2d0-121">В диалоговом окне **Добавление нового проекта** разверните узел **Visual Basic**, выберите узел **.NET Standard**, а затем — шаблон проекта **Библиотека классов (.NET Standard)** .</span><span class="sxs-lookup"><span data-stu-id="0a2d0-121">In the **Add New Project** dialog, expand the **Visual Basic** node, then select the **.NET Standard** node followed by the **Class Library (.NET Standard)** project template.</span></span> <span data-ttu-id="0a2d0-122">В текстовом поле **Имя** введите имя проекта StringLibrary.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-122">In the **Name** text box, enter "StringLibrary" as the name of the project.</span></span> <span data-ttu-id="0a2d0-123">Нажмите **ОК**, чтобы создать проект библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-123">Select **OK** to create the class library project.</span></span>

   ![Visual Studio создает диалоговое окно добавления нового проекта библиотеки](./media/vb-library-with-visual-studio/create-new-library-project.png)

   <span data-ttu-id="0a2d0-125">Окно кода затем откроется в среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-125">The code window then opens in the Visual Studio development environment.</span></span> 
 
   ![Окно приложения Visual Studio, отображающее код шаблона библиотеки классов по умолчанию](./media/vb-library-with-visual-studio/visual-studio-library.png)

1. <span data-ttu-id="0a2d0-127">Проверьте, предназначена ли библиотека для правильной версии .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-127">Check to make sure that the library targets the correct version of the .NET Standard.</span></span> <span data-ttu-id="0a2d0-128">В **обозревателе решений** щелкните проект библиотеки правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-128">Right-click on the library project in the **Solution Explorer** windows, then select **Properties**.</span></span> <span data-ttu-id="0a2d0-129">В текстовом поле **Целевая платформа** указано, что целевой платформой является .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-129">The **Target Framework** text box shows that we're targeting .NET Standard 2.0.</span></span>

   ![Свойства проекта для библиотеки классов](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="0a2d0-131">Кроме того, в диалоговом окне **Свойства** удалите текст в поле **Корневое пространство имен**.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-131">Also in the **Properties** dialog, clear the text in the **Root namespace** text box.</span></span> <span data-ttu-id="0a2d0-132">Для каждого проекта Visual Basic автоматически создает пространство имен, соответствующее имени проекта. Все пространства имен, определяемые в файлах с исходным кодом, являются родительскими по отношению к этому пространству имен.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-132">For each project, Visual Basic automatically creates a namespace that corresponds to the project name, and any namespaces defined in source code files are parents of that namespace.</span></span> <span data-ttu-id="0a2d0-133">Нам необходимо определить пространство имен верхнего уровня с помощью ключевого слова [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0a2d0-133">We want to define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword.</span></span>
  
1. <span data-ttu-id="0a2d0-134">Замените код, отображаемый в окне кода, следующим текстом, а затем сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-134">Replace the code in the code window with the following code and save the file:</span></span>

  [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   <span data-ttu-id="0a2d0-135">Библиотека классов (`UtilityLibraries.StringLibrary`) содержит метод с именем `StartsWithUpper`, который возвращает значение <xref:System.Boolean>. Это значение указывает, является ли первым символом текущего экземпляра строки символ верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-135">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`, which returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="0a2d0-136">Символы верхнего регистра определяются по стандарту Юникод.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-136">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="0a2d0-137">Метод <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> возвращает `true`, если символ является символом верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-137">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="0a2d0-138">В строке меню выберите **Сборка** > **Собрать решение**.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-138">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="0a2d0-139">Проект должен скомпилироваться без ошибок.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-139">The project should compile without error.</span></span>

   ![Область вывода, показывающая успешное завершение сборки](./media/library-with-visual-studio/output-pane-successful-build.png)

## <a name="next-step"></a><span data-ttu-id="0a2d0-141">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="0a2d0-141">Next step</span></span>

<span data-ttu-id="0a2d0-142">Итак, вы успешно создали библиотеку.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-142">You've successfully built the library.</span></span> <span data-ttu-id="0a2d0-143">Пока вы еще не вызывали ее методов, поэтому нельзя быть уверенным, что все работает так, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="0a2d0-143">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="0a2d0-144">Следующий шаг в разработке библиотеки — тестирование с помощью [проекта модульного теста](testing-library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="0a2d0-144">The next step in developing your library is to test it by using a [Unit Test Project](testing-library-with-visual-studio.md).</span></span>
