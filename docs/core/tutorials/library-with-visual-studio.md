---
title: Создание библиотеки классов .NET Standard в Visual Studio
description: Узнайте, как создать библиотеку классов .NET Standard, написанную на языке C# или Visual Basic, с помощью Visual Studio
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 748a1499e0c3a4a41613a69b715dbcfbd585bfe3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714010"
---
# <a name="build-a-net-standard-library-in-visual-studio"></a><span data-ttu-id="20611-103">Создание библиотеки .NET Standard в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="20611-103">Build a .NET Standard library in Visual Studio</span></span>

<span data-ttu-id="20611-104">*Библиотека классов* определяет типы и методы, которые могут быть вызваны из любого приложения.</span><span class="sxs-lookup"><span data-stu-id="20611-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="20611-105">Библиотеку классов, предназначенную для .NET Standard 2.0, можно вызывать из любой реализации .NET, которая поддерживает эту версию .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="20611-105">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="20611-106">Когда вы завершите создание библиотеки классов, вы сможете по своему усмотрению распространять ее как независимый компонент или включить в состав одного или нескольких приложений.</span><span class="sxs-lookup"><span data-stu-id="20611-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="20611-107">Список версий .NET Standard и поддерживаемых ими платформ см. в разделе [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="20611-107">For a list of .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="20611-108">В этой статье вы создадите простую служебную библиотеку с одним методом для обработки строк.</span><span class="sxs-lookup"><span data-stu-id="20611-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="20611-109">Вы реализуете его как [метод расширения](../../csharp/programming-guide/classes-and-structs/extension-methods.md), чтобы вызывать его так же, как любой член класса <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="20611-109">You'll implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="create-a-visual-studio-solution"></a><span data-ttu-id="20611-110">Создание решения Visual Studio</span><span class="sxs-lookup"><span data-stu-id="20611-110">Create a Visual Studio solution</span></span>

<span data-ttu-id="20611-111">Начните с создания пустого решения для размещения проекта библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="20611-111">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="20611-112">Решение Visual Studio служит контейнером для одного или нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="20611-112">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="20611-113">Продолжая работу с этой серией учебников, вы будете добавлять дополнительные связанные проекты в одно решение.</span><span class="sxs-lookup"><span data-stu-id="20611-113">You'll add additional, related projects to the same solution if you continue on with the tutorial series.</span></span>

<span data-ttu-id="20611-114">Чтобы создать пустое решение, сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="20611-114">To create the blank solution:</span></span>

1. <span data-ttu-id="20611-115">Запустите Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="20611-115">Open Visual Studio.</span></span>

2. <span data-ttu-id="20611-116">На начальном экране выберите **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="20611-116">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="20611-117">В поле поиска на странице **Создание проекта** введите **решение**.</span><span class="sxs-lookup"><span data-stu-id="20611-117">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="20611-118">Выберите шаблон **Пустое решение** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="20611-118">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   ![Шаблон пустого решения в Visual Studio](media/library-with-visual-studio/blank-solution.png)

4. <span data-ttu-id="20611-120">На странице **настройки нового проекта** введите **ClassLibraryProjects** в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="20611-120">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="20611-121">Затем нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="20611-121">Then, choose **Create**.</span></span>

> [!TIP]
> <span data-ttu-id="20611-122">Вы также можете пропустить этот шаг и позволить Visual Studio автоматически создать решение, когда вы будете создавать проект на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="20611-122">You can also skip this step and let Visual Studio create the solution for you when you create the project in the next step.</span></span> <span data-ttu-id="20611-123">Найдите параметры решения на странице **настройки нового проекта**.</span><span class="sxs-lookup"><span data-stu-id="20611-123">Look for the solution options on the **Configure your new project** page.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="20611-124">Создание проекта библиотеки классов</span><span class="sxs-lookup"><span data-stu-id="20611-124">Create a class library project</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[<span data-ttu-id="20611-125">C#</span><span class="sxs-lookup"><span data-stu-id="20611-125">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="20611-126">Добавьте в решение новый проект библиотеки классов .NET Standard на C# с именем StringLibrary.</span><span class="sxs-lookup"><span data-stu-id="20611-126">Add a new C# .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="20611-127">Щелкните решение в **обозревателе решений** правой кнопкой мыши и выберите **Добавить** > **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="20611-127">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="20611-128">На странице **добавления нового проекта** введите в поле поиска **библиотека**.</span><span class="sxs-lookup"><span data-stu-id="20611-128">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="20611-129">Затем выберите **C#** в списке языков и **Все платформы** в списке платформ.</span><span class="sxs-lookup"><span data-stu-id="20611-129">Choose **C#** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="20611-130">Выберите шаблон **Библиотека классов (.NET Standard)** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="20611-130">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="20611-131">На странице **настройки нового проекта** введите **StringLibrary** в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="20611-131">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="20611-132">Затем нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="20611-132">Then, choose **Create**.</span></span>

1. <span data-ttu-id="20611-133">Проверьте, предназначена ли библиотека для правильной версии .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="20611-133">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="20611-134">В **обозревателе решений** щелкните проект библиотеки правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="20611-134">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="20611-135">В текстовом поле **Целевая платформа** указано, что целевой платформой проекта является .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="20611-135">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![Свойства проекта для библиотеки классов](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="20611-137">Замените код, отображаемый в окне кода, следующим текстом, а затем сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="20611-137">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   <span data-ttu-id="20611-138">Библиотека классов `UtilityLibraries.StringLibrary` содержит метод `StartsWithUpper`,</span><span class="sxs-lookup"><span data-stu-id="20611-138">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="20611-139">который возвращает значение <xref:System.Boolean>, указывающее, является ли первым символом текущего экземпляра строки символ верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="20611-139">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="20611-140">Символы верхнего регистра определяются по стандарту Юникод.</span><span class="sxs-lookup"><span data-stu-id="20611-140">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="20611-141">Метод <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> возвращает `true`, если символ является символом верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="20611-141">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="20611-142">В строке меню выберите **Сборка** > **Собрать решение**.</span><span class="sxs-lookup"><span data-stu-id="20611-142">On the menu bar, select **Build** > **Build Solution**.</span></span>

# <a name="visual-basic"></a>[<span data-ttu-id="20611-143">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20611-143">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="20611-144">Добавьте в решение новый проект библиотеки классов Visual Basic .NET Standard с именем StringLibrary.</span><span class="sxs-lookup"><span data-stu-id="20611-144">Add a new Visual Basic .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="20611-145">Щелкните решение в **обозревателе решений** правой кнопкой мыши и выберите **Добавить** > **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="20611-145">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="20611-146">На странице **добавления нового проекта** введите в поле поиска **библиотека**.</span><span class="sxs-lookup"><span data-stu-id="20611-146">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="20611-147">Выберите **Visual Basic** в списке языков и **Все платформы** в списке платформ.</span><span class="sxs-lookup"><span data-stu-id="20611-147">Choose **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="20611-148">Выберите шаблон **Библиотека классов (.NET Standard)** , а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="20611-148">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="20611-149">На странице **настройки нового проекта** введите **StringLibrary** в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="20611-149">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="20611-150">Затем нажмите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="20611-150">Then, choose **Create**.</span></span>

1. <span data-ttu-id="20611-151">Проверьте, предназначена ли библиотека для правильной версии .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="20611-151">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="20611-152">В **обозревателе решений** щелкните проект библиотеки правой кнопкой мыши и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="20611-152">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="20611-153">В текстовом поле **Целевая платформа** указано, что целевой платформой проекта является .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="20611-153">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![Свойства проекта для библиотеки классов](./media/library-with-visual-studio/vb/library-project-properties.png)

1. <span data-ttu-id="20611-155">В диалоговом окне **Свойства** удалите текст в поле **Корневое пространство имен**.</span><span class="sxs-lookup"><span data-stu-id="20611-155">In the **Properties** dialog, clear the text in the **Root namespace** text box.</span></span> <span data-ttu-id="20611-156">Для каждого проекта Visual Basic автоматически создает пространство имен, соответствующее имени проекта.</span><span class="sxs-lookup"><span data-stu-id="20611-156">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="20611-157">В этом учебнике вы определите пространство имен верхнего уровня с помощью ключевого слова [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) в файле кода.</span><span class="sxs-lookup"><span data-stu-id="20611-157">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="20611-158">Замените код, отображаемый в окне кода, следующим текстом, а затем сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="20611-158">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   <span data-ttu-id="20611-159">Библиотека классов `UtilityLibraries.StringLibrary` содержит метод `StartsWithUpper`,</span><span class="sxs-lookup"><span data-stu-id="20611-159">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="20611-160">который возвращает значение <xref:System.Boolean>, указывающее, является ли первым символом текущего экземпляра строки символ верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="20611-160">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="20611-161">Символы верхнего регистра определяются по стандарту Юникод.</span><span class="sxs-lookup"><span data-stu-id="20611-161">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="20611-162">Метод <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> возвращает `true`, если символ является символом верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="20611-162">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="20611-163">В строке меню выберите **Сборка** > **Собрать решение**.</span><span class="sxs-lookup"><span data-stu-id="20611-163">On the menu bar, select **Build** > **Build Solution**.</span></span>

---

   <span data-ttu-id="20611-164">Проект должен скомпилироваться без ошибок.</span><span class="sxs-lookup"><span data-stu-id="20611-164">The project should compile without error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="20611-165">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="20611-165">Next steps</span></span>

<span data-ttu-id="20611-166">Итак, вы успешно создали библиотеку.</span><span class="sxs-lookup"><span data-stu-id="20611-166">You've successfully built the library.</span></span> <span data-ttu-id="20611-167">Пока вы еще не вызывали ее методов, поэтому нельзя быть уверенным, что все работает так, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="20611-167">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="20611-168">Следующий шаг в разработке библиотеки — ее тестирование.</span><span class="sxs-lookup"><span data-stu-id="20611-168">The next step in developing your library is to test it.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="20611-169">Создание проекта модульного теста</span><span class="sxs-lookup"><span data-stu-id="20611-169">Create a unit test project</span></span>](testing-library-with-visual-studio.md)
