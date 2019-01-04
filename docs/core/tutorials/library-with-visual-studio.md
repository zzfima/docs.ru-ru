---
title: Создание библиотеки классов .NET Standard на C# с помощью Visual Studio 2017
description: Сведения о создании библиотеки классов .NET Standard, написанной на языке C#, с помощью Visual Studio 2017.
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 0c98f8c8fc4847570964d8d4ea8deb221164441d
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168940"
---
# <a name="build-a-net-standard-class-library-with-c-and-the-net-core-sdk-in-visual-studio-2017"></a><span data-ttu-id="e6805-103">Создание библиотеки классов .NET Standard с помощью C# и пакета SDK для .NET Core в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="e6805-103">Build a .NET Standard class library with C# and the .NET Core SDK in Visual Studio 2017</span></span>

<span data-ttu-id="e6805-104">*Библиотека классов* определяет типы и методы, которые могут быть вызваны из любого приложения.</span><span class="sxs-lookup"><span data-stu-id="e6805-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="e6805-105">Библиотеку классов, предназначенную для .NET Standard 2.0, можно вызывать из любой реализации .NET, которая поддерживает эту версию .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e6805-105">A class library that targets the .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of the .NET Standard.</span></span> <span data-ttu-id="e6805-106">Когда вы завершите создание библиотеки классов, вы сможете по своему усмотрению распространять ее как независимый компонент или включить в состав одного или нескольких приложений.</span><span class="sxs-lookup"><span data-stu-id="e6805-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="e6805-107">Список версий .NET Standard и поддерживаемых ими платформ см. в разделе [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="e6805-107">For a list of the .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="e6805-108">В этой статье вы создадите простую служебную библиотеку с одним методом для обработки строк.</span><span class="sxs-lookup"><span data-stu-id="e6805-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="e6805-109">Вы реализуете его как [метод расширения](../../csharp/programming-guide/classes-and-structs/extension-methods.md), чтобы вызывать его так же, как любой член класса <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="e6805-109">You'll implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="creating-a-class-library-solution"></a><span data-ttu-id="e6805-110">Создание решения для библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="e6805-110">Creating a class library solution</span></span>

<span data-ttu-id="e6805-111">Начнем с создания решения для нашего проекта библиотеки классов и связанных с ней проектов.</span><span class="sxs-lookup"><span data-stu-id="e6805-111">Start by creating a solution for your class library project and its related projects.</span></span> <span data-ttu-id="e6805-112">Решение Visual Studio служит контейнером для одного или нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="e6805-112">A Visual Studio Solution just serves as a container for one or more projects.</span></span> <span data-ttu-id="e6805-113">Чтобы создать решение, выполните следующее.</span><span class="sxs-lookup"><span data-stu-id="e6805-113">To create the solution:</span></span>

1. <span data-ttu-id="e6805-114">В строке меню Visual Studio выберите **Файл** > **Создать** > **Проект**.</span><span class="sxs-lookup"><span data-stu-id="e6805-114">On the Visual Studio menu bar, choose **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="e6805-115">В диалоговом окне **Новый проект** разверните узел **Другие типы проектов** и выберите **Решения Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="e6805-115">In the **New Project** dialog, expand the **Other Project Types** node, and select **Visual Studio Solutions**.</span></span> <span data-ttu-id="e6805-116">Присвойте решению имя ClassLibraryProjects и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e6805-116">Name the solution "ClassLibraryProjects" and select the **OK** button.</span></span>

   ![Диалоговое окно создания проекта с выделенным новым решением](./media/library-with-visual-studio/new-project-dialog.png)

## <a name="creating-the-class-library-project"></a><span data-ttu-id="e6805-118">Создание проекта для библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="e6805-118">Creating the class library project</span></span>

<span data-ttu-id="e6805-119">Теперь можно создать проект библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="e6805-119">Create your class library project:</span></span>

1. <span data-ttu-id="e6805-120">В **обозревателе решений** щелкните правой кнопкой мыши решение **ClassLibraryProjects** и в контекстном меню выберите **Добавить** > **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="e6805-120">In **Solution Explorer**, right-click on the **ClassLibraryProjects** solution file and from the context menu, select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="e6805-121">В диалоговом окне **Добавление нового проекта** разверните узел **Visual C#**, выберите узел **.NET Standard**, а затем — шаблон проекта **Библиотека классов (.NET Standard)**.</span><span class="sxs-lookup"><span data-stu-id="e6805-121">In the **Add New Project** dialog, expand the **Visual C#** node, then select the **.NET Standard** node followed by the **Class Library (.NET Standard)** project template.</span></span> <span data-ttu-id="e6805-122">В текстовом поле **Имя** введите имя проекта StringLibrary.</span><span class="sxs-lookup"><span data-stu-id="e6805-122">In the **Name** text box, enter "StringLibrary" as the name of the project.</span></span> <span data-ttu-id="e6805-123">Нажмите **ОК**, чтобы создать проект библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="e6805-123">Select **OK** to create the class library project.</span></span>

   ![Диалоговое окно добавления нового проекта библиотеки](./media/library-with-visual-studio/add-new-library-project.png)

   <span data-ttu-id="e6805-125">Окно кода затем откроется в среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e6805-125">The code window then opens in the Visual Studio development environment.</span></span>

   ![Окно приложения Visual Studio, отображающее код шаблона библиотеки классов по умолчанию](./media/library-with-visual-studio/string-library-project.png)

1. <span data-ttu-id="e6805-127">Проверьте, предназначена ли библиотека для правильной версии .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e6805-127">Check to make sure that our library targets the correct version of the .NET Standard.</span></span> <span data-ttu-id="e6805-128">В **обозревателе решений** щелкните проект библиотеки правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="e6805-128">Right-click on the library project in the **Solution Explorer** windows, then select **Properties**.</span></span> <span data-ttu-id="e6805-129">В текстовом поле **Целевая платформа** указано, что целевой платформой является .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="e6805-129">The **Target Framework** text box shows that we're targeting .NET Standard 2.0.</span></span>

   ![Свойства проекта для библиотеки классов](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="e6805-131">Замените код, отображаемый в окне кода, следующим текстом, а затем сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="e6805-131">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   <span data-ttu-id="e6805-132">Библиотека классов (`UtilityLibraries.StringLibrary`) содержит метод с именем `StartsWithUpper`, который возвращает значение <xref:System.Boolean>. Это значение указывает, является ли первым символом текущего экземпляра строки символ верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="e6805-132">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`, which returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="e6805-133">Символы верхнего регистра определяются по стандарту Юникод.</span><span class="sxs-lookup"><span data-stu-id="e6805-133">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="e6805-134">Метод <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> возвращает `true`, если символ является символом верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="e6805-134">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="e6805-135">В строке меню выберите **Сборка** > **Собрать решение**.</span><span class="sxs-lookup"><span data-stu-id="e6805-135">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="e6805-136">Проект должен скомпилироваться без ошибок.</span><span class="sxs-lookup"><span data-stu-id="e6805-136">The project should compile without error.</span></span>

   ![Область вывода, показывающая успешное завершение сборки](./media/library-with-visual-studio/output-pane-successful-build.png)

## <a name="next-step"></a><span data-ttu-id="e6805-138">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="e6805-138">Next step</span></span>

<span data-ttu-id="e6805-139">Итак, вы успешно создали библиотеку.</span><span class="sxs-lookup"><span data-stu-id="e6805-139">You've successfully built the library.</span></span> <span data-ttu-id="e6805-140">Пока вы еще не вызывали ее методов, поэтому нельзя быть уверенным, что все работает так, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="e6805-140">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="e6805-141">Следующий шаг в разработке библиотеки — тестирование с помощью [проекта модульного теста](testing-library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="e6805-141">The next step in developing your library is to test it by using a [Unit Test Project](testing-library-with-visual-studio.md).</span></span>