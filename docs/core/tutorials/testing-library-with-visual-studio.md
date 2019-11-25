---
title: Тестирование библиотеки классов .NET Standard с помощью .NET Core в Visual Studio 2017
description: Создайте проект модульного теста для библиотеки классов .NET Core. Проверьте правильность работы библиотеки классов .NET Core с помощью модульных тестов.
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet, seodoc18
ms.openlocfilehash: 242234d93bc1b8f9b88749f2e3bcfb37c2bde86d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73037964"
---
# <a name="test-a-net-standard-library-with-net-core-in-visual-studio-2017"></a><span data-ttu-id="71d4b-104">Тестирование библиотеки .NET Standard с помощью .NET Core в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="71d4b-104">Test a .NET Standard library with .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="71d4b-105">При работе с руководствами по созданию библиотеки с помощью .NET Standard в Visual Studio 2017 на [C# ](library-with-visual-studio.md) или [Visual Basic](vb-library-with-visual-studio.md) вы уже создали простую библиотеку классов, которая добавляет метод расширения к классу <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="71d4b-105">In [Build a .NET Standard library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio.md) or [Build a .NET Standard library with Visual Basic and .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md), you created a simple class library that adds an extension method to the <xref:System.String> class.</span></span> <span data-ttu-id="71d4b-106">Теперь вы создадите модульный тест и убедитесь, что все работает правильно.</span><span class="sxs-lookup"><span data-stu-id="71d4b-106">Now, you'll create a unit test to make sure that it works as expected.</span></span> <span data-ttu-id="71d4b-107">Новый проект модульного теста вы добавите к решению, созданному при работе с предыдущей статьей.</span><span class="sxs-lookup"><span data-stu-id="71d4b-107">You'll add your unit test project to the solution you created in the previous article.</span></span>

## <a name="creating-a-unit-test-project"></a><span data-ttu-id="71d4b-108">Создание проекта модульного теста</span><span class="sxs-lookup"><span data-stu-id="71d4b-108">Creating a unit test project</span></span>

<span data-ttu-id="71d4b-109">Чтобы создать проект модульного теста, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="71d4b-109">To create the unit test project, do the following:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[<span data-ttu-id="71d4b-110">C#</span><span class="sxs-lookup"><span data-stu-id="71d4b-110">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="71d4b-111">В **обозревателе решений** откройте контекстное меню для узла решения **ClassLibraryProjects** и выберите **Добавить** > **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-111">In **Solution Explorer**, open the context menu for the **ClassLibraryProjects** solution node and select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="71d4b-112">В диалоговом окне **Добавление нового проекта** разверните узел **Visual C#** .</span><span class="sxs-lookup"><span data-stu-id="71d4b-112">In the **Add New Project** dialog, select the **Visual C#** node.</span></span> <span data-ttu-id="71d4b-113">Выберите узел **.NET Core**, а затем — шаблон проекта **Проект теста MSTest (.NET Core)** .</span><span class="sxs-lookup"><span data-stu-id="71d4b-113">Then select the **.NET Core** node followed by the **MSTest Test Project (.NET Core)** project template.</span></span> <span data-ttu-id="71d4b-114">В текстовом поле **Имя** введите имя проекта StringLibraryTest.</span><span class="sxs-lookup"><span data-stu-id="71d4b-114">In the **Name** text box, enter "StringLibraryTest" as the name of the project.</span></span> <span data-ttu-id="71d4b-115">Нажмите кнопку **ОК**, чтобы создать проект модульного теста.</span><span class="sxs-lookup"><span data-stu-id="71d4b-115">Select **OK** to create the unit test project.</span></span>

   ![Диалоговое окно "Добавление нового проекта", в котором отображается проект модульного теста (C#)](./media/testing-library-with-visual-studio/create-new-test-project.png)

   > [!NOTE]  
   > <span data-ttu-id="71d4b-117">Кроме проекта теста MSTest, с помощью Visual Studio можно также создать тестовый проект xUnit для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="71d4b-117">In addition to an MSTest Test project, you can also use Visual Studio to create an xUnit test project for .NET Core.</span></span>

1. <span data-ttu-id="71d4b-118">Visual Studio создаст проект и откроет файл *UnitTest1.cs* в окне кода.</span><span class="sxs-lookup"><span data-stu-id="71d4b-118">Visual Studio creates the project and opens the *UnitTest1.cs* file in the code window.</span></span>

   ![Окно кода Visual Studio, в котором указаны класс и метод проекта модульного теста (C#)](./media/testing-library-with-visual-studio/unit-test-editor-window.png)

   <span data-ttu-id="71d4b-120">Исходный код, созданный шаблоном модульного теста, выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="71d4b-120">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="71d4b-121">Он импортирует пространство имен <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, которое содержит типы, используемые для модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="71d4b-121">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>

   - <span data-ttu-id="71d4b-122">Он применяет атрибут <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> к классу `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="71d4b-122">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span> <span data-ttu-id="71d4b-123">При запуске модульного теста автоматически выполняются все методы теста в тестовом классе, помеченные атрибутом \[TestMethod\].</span><span class="sxs-lookup"><span data-stu-id="71d4b-123">Each test method in a test class tagged with the \[TestMethod\] attribute is executed automatically when the unit test is run.</span></span>

   - <span data-ttu-id="71d4b-124">Атрибут <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> определяет `TestMethod1` как метод теста, который будет автоматически выполняться при запуске модульного теста.</span><span class="sxs-lookup"><span data-stu-id="71d4b-124">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` as a test method for automatic execution when the unit test is run.</span></span>

1. <span data-ttu-id="71d4b-125">В **обозревателе решений** щелкните узел **Зависимости** в проекте **StringLibraryTest** правой кнопкой мыши и выберите в контекстном меню пункт **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-125">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Reference** from the context menu.</span></span>

   ![Контекстное меню узла "Зависимости" в проекте StringLibraryTest (C#)](./media/testing-library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="71d4b-127">В диалоговом окне **Диспетчер ссылок** разверните узел **Проекты** и установите флажок рядом с пунктом **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-127">In the **Reference Manager** dialog, expand the **Projects** node and check the box next to **StringLibrary**.</span></span> <span data-ttu-id="71d4b-128">Добавление ссылки на сборку `StringLibrary` позволяет компилятору находить методы **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-128">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods.</span></span> <span data-ttu-id="71d4b-129">Нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-129">Select the **OK** button.</span></span> <span data-ttu-id="71d4b-130">Это действие добавляет ссылку на ваш проект библиотеки классов (`StringLibrary`).</span><span class="sxs-lookup"><span data-stu-id="71d4b-130">This adds a reference to your class library project, `StringLibrary`.</span></span>

   ![Диалоговое окно добавления ссылок на проект в Visual Studio](./media/testing-library-with-visual-studio/project-reference-manager.png)

# <a name="visual-basictabvb"></a>[<span data-ttu-id="71d4b-132">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="71d4b-132">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="71d4b-133">В **обозревателе решений** откройте контекстное меню для узла решения **ClassLibraryProjects** и выберите **Добавить** > **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-133">In **Solution Explorer**, open the context menu for the **ClassLibraryProjects** solution node and select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="71d4b-134">В диалоговом окне **Добавление нового проекта** разверните узел **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-134">In the **Add New Project** dialog, select the **Visual Basic** node.</span></span> <span data-ttu-id="71d4b-135">Выберите узел **.NET Core**, а затем — шаблон проекта **Проект теста MSTest (.NET Core)** .</span><span class="sxs-lookup"><span data-stu-id="71d4b-135">Then select the **.NET Core** node followed by the **MSTest Test Project (.NET Core)** project template.</span></span> <span data-ttu-id="71d4b-136">В текстовом поле **Имя** введите имя проекта StringLibraryTest.</span><span class="sxs-lookup"><span data-stu-id="71d4b-136">In the **Name** text box, enter "StringLibraryTest" as the name of the project.</span></span> <span data-ttu-id="71d4b-137">Нажмите кнопку **ОК**, чтобы создать проект модульного теста.</span><span class="sxs-lookup"><span data-stu-id="71d4b-137">Select **OK** to create the unit test project.</span></span>

   ![Диалоговое окно "Добавление нового проекта", в котором отображается проект модульного теста (Visual Basic)](./media/testing-library-with-visual-studio/vb-create-new-test-project.png)

   > [!NOTE]  
   > <span data-ttu-id="71d4b-139">Кроме проекта теста MSTest, с помощью Visual Studio можно также создать тестовый проект xUnit для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="71d4b-139">In addition to an MSTest Test project, you can also use Visual Studio to create an xUnit test project for .NET Core.</span></span>

1. <span data-ttu-id="71d4b-140">Visual Studio создаст проект и откроет файл *UnitTest1.vb* в окне кода.</span><span class="sxs-lookup"><span data-stu-id="71d4b-140">Visual Studio creates the project and opens the *UnitTest1.vb* file in the code window.</span></span>

   ![Окно кода Visual Studio, в котором указаны класс и метод проекта модульного теста (Visual Basic)](./media/testing-library-with-visual-studio/vb-unit-test-editor-window.png)

   <span data-ttu-id="71d4b-142">Исходный код, созданный шаблоном модульного теста, выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="71d4b-142">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="71d4b-143">Он импортирует пространство имен <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, которое содержит типы, используемые для модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="71d4b-143">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>

   - <span data-ttu-id="71d4b-144">Он применяет атрибут <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> к классу `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="71d4b-144">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute to the `UnitTest1` class.</span></span> <span data-ttu-id="71d4b-145">При запуске модульного теста автоматически выполняются все методы теста в классе теста, помеченные атрибутом <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="71d4b-145">Each test method in a test class tagged with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute is executed automatically when the unit test is run.</span></span>

   - <span data-ttu-id="71d4b-146">Атрибут <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> определяет `TestMethod1` как метод теста, который будет автоматически выполняться при запуске модульного теста.</span><span class="sxs-lookup"><span data-stu-id="71d4b-146">It applies the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute to define `TestMethod1` as a test method for automatic execution when the unit test is run.</span></span>

1. <span data-ttu-id="71d4b-147">В **обозревателе решений** щелкните узел **Зависимости** в проекте **StringLibraryTest** правой кнопкой мыши и выберите в контекстном меню пункт **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-147">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Reference** from the context menu.</span></span>

   ![Контекстное меню узла "Зависимости" в проекте StringLibraryTest](./media/testing-library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="71d4b-149">В диалоговом окне **Диспетчер ссылок** разверните узел **Проекты** и установите флажок рядом с пунктом **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-149">In the **Reference Manager** dialog, expand the **Projects** node and check the box next to **StringLibrary**.</span></span> <span data-ttu-id="71d4b-150">Добавление ссылки на сборку `StringLibrary` позволяет компилятору находить методы **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-150">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods.</span></span> <span data-ttu-id="71d4b-151">Нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-151">Select the **OK** button.</span></span> <span data-ttu-id="71d4b-152">Это действие добавляет ссылку на ваш проект библиотеки классов (`StringLibrary`).</span><span class="sxs-lookup"><span data-stu-id="71d4b-152">This adds a reference to your class library project, `StringLibrary`.</span></span>

   ![Диалоговое окно добавления ссылок на проект в Visual Studio (Visual Basic)](./media/testing-library-with-visual-studio/project-reference-manager.png)

---

## <a name="adding-and-running-unit-test-methods"></a><span data-ttu-id="71d4b-154">Добавление и выполнение методов модульных тестов</span><span class="sxs-lookup"><span data-stu-id="71d4b-154">Adding and running unit test methods</span></span>

<span data-ttu-id="71d4b-155">При запуске модульного теста Visual Studio выполняет каждый метод, помеченный атрибутом <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute>, из класса модульных тестов (это класс, к которому применяется атрибут <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>).</span><span class="sxs-lookup"><span data-stu-id="71d4b-155">When Visual Studio runs a unit test, it executes each method marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a unit test class, the class to which the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute is applied.</span></span> <span data-ttu-id="71d4b-156">Метод теста завершается, когда происходит первый сбой или когда все тесты, содержащиеся в методе, будут успешно выполнены.</span><span class="sxs-lookup"><span data-stu-id="71d4b-156">A test method ends when the first failure is encountered or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="71d4b-157">В самых распространенных тестах вызываются члены класса <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="71d4b-157">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="71d4b-158">Многие методы утверждения (Assert) принимают по крайней мере два параметра, из которых один представляет ожидаемый результат теста, а второй — фактический результат теста.</span><span class="sxs-lookup"><span data-stu-id="71d4b-158">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="71d4b-159">Наиболее популярные из этих методов перечислены в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="71d4b-159">Some of its most frequently called methods are shown in the following table:</span></span>

<span data-ttu-id="71d4b-160">Методы утверждения</span><span class="sxs-lookup"><span data-stu-id="71d4b-160">Assert methods</span></span> | <span data-ttu-id="71d4b-161">Функция</span><span class="sxs-lookup"><span data-stu-id="71d4b-161">Function</span></span>
--- | ---
`Assert.AreEqual` | <span data-ttu-id="71d4b-162">Проверяет равенство двух значений или объектов.</span><span class="sxs-lookup"><span data-stu-id="71d4b-162">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="71d4b-163">Утверждение не выполняется, если значения или объекты не равны.</span><span class="sxs-lookup"><span data-stu-id="71d4b-163">The assert fails if the values or objects are not equal.</span></span>
`Assert.AreSame` | <span data-ttu-id="71d4b-164">Проверяет, что две объектные переменные ссылаются на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="71d4b-164">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="71d4b-165">Утверждение не выполняется, если переменные ссылаются на разные объекты.</span><span class="sxs-lookup"><span data-stu-id="71d4b-165">The assert fails if the variables refer to different objects.</span></span>
`Assert.IsFalse` | <span data-ttu-id="71d4b-166">Проверяет, что условие имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="71d4b-166">Verifies that a condition is `false`.</span></span> <span data-ttu-id="71d4b-167">Утверждение не выполняется, если условие имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="71d4b-167">The assert fails if the condition is `true`.</span></span>
`Assert.IsNotNull` | <span data-ttu-id="71d4b-168">Проверяет, что объект не имеет значения `null`.</span><span class="sxs-lookup"><span data-stu-id="71d4b-168">Verifies that an object is not `null`.</span></span> <span data-ttu-id="71d4b-169">Утверждение не выполняется, если объект является `null`.</span><span class="sxs-lookup"><span data-stu-id="71d4b-169">The assert fails if the object is `null`.</span></span>

<span data-ttu-id="71d4b-170">К методу теста также можно применить атрибут <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="71d4b-170">You can also apply the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute> attribute to a test method.</span></span> <span data-ttu-id="71d4b-171">Он указывает тип исключения, который должен вызывать метод теста.</span><span class="sxs-lookup"><span data-stu-id="71d4b-171">It indicates the type of exception a test method is expected to throw.</span></span> <span data-ttu-id="71d4b-172">Такой тест считается не выполненным, если заявленное исключение не было создано.</span><span class="sxs-lookup"><span data-stu-id="71d4b-172">The test fails if the specified exception is not thrown.</span></span>

<span data-ttu-id="71d4b-173">Для тестирования метода `StringLibrary.StartsWithUpper` необходимо предоставить несколько строк, которые начинаются с символов верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="71d4b-173">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="71d4b-174">Предполагается, что в этих случаях метод возвратит `true`, поэтому можно вызвать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A>.</span><span class="sxs-lookup"><span data-stu-id="71d4b-174">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A> method.</span></span> <span data-ttu-id="71d4b-175">Представьте также несколько строк, которые не начинаются с символов верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="71d4b-175">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="71d4b-176">Предполагается, что в этих случаях метод возвратит `false`, поэтому можно вызвать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A>.</span><span class="sxs-lookup"><span data-stu-id="71d4b-176">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A> method.</span></span>

<span data-ttu-id="71d4b-177">Так как ваш метод библиотеки обрабатывает строки, нам нужно проверить правильность обработки [пустых строк (`String.Empty`)](xref:System.String.Empty) (так называется допустимая строка, которая не содержит символов и для которой свойство <xref:System.String.Length> имеет значение 0) и строки `null`, которая не была инициализирована.</span><span class="sxs-lookup"><span data-stu-id="71d4b-177">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that has not been initialized.</span></span> <span data-ttu-id="71d4b-178">Если `StartsWithUpper` вызывается в качестве метода расширения для экземпляра <xref:System.String>, ему нельзя передавать строку `null`.</span><span class="sxs-lookup"><span data-stu-id="71d4b-178">If `StartsWithUpper` is called as an extension method on a <xref:System.String> instance, it cannot be passed a `null` string.</span></span> <span data-ttu-id="71d4b-179">Однако его можно вызвать напрямую как статический метод и передать ему один аргумент типа <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="71d4b-179">However, you can also call it directly as a static method and pass a single <xref:System.String> argument.</span></span>

<span data-ttu-id="71d4b-180">Вы определите три метода, каждый из которых поочередно вызывает метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> для каждого элемента в массиве строк.</span><span class="sxs-lookup"><span data-stu-id="71d4b-180">You'll define three methods, each of which calls its <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="71d4b-181">Поскольку метод теста завершается ошибкой при первом же сбое, вы вызовете перегруженную версию метода, которая позволяет передать строку и указать строковое значение, используемое в вызове метода.</span><span class="sxs-lookup"><span data-stu-id="71d4b-181">Because the test method fails as soon as it encounters the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="71d4b-182">Создание методов теста:</span><span class="sxs-lookup"><span data-stu-id="71d4b-182">To create the test methods:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="71d4b-183">C#</span><span class="sxs-lookup"><span data-stu-id="71d4b-183">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="71d4b-184">В окне кода *UnitTest1.cs* замените отображаемый код на следующий текст:</span><span class="sxs-lookup"><span data-stu-id="71d4b-184">In the *UnitTest1.cs* code window, replace the code with the following code:</span></span>

   [!code-csharp[Test#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]

   <span data-ttu-id="71d4b-185">Обратите внимание, что наш тест на символы верхнего регистра в методе `TestStartsWithUpper` включает заглавную греческую букву "альфа" (U+0391) и заглавную кириллическую букву "М" (U+041C). Тест на символы нижнего регистра в методе `TestDoesNotStartWithUpper` включает строчную греческую букву "альфа" (U+03B1) и строчную кириллическую букву "г" (U+0433).</span><span class="sxs-lookup"><span data-stu-id="71d4b-185">Note that your test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C), and the test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="71d4b-186">В строке меню выберите **Файл** > **Сохранить UnitTest1.cs как**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-186">On the menu bar, select **File** > **Save UnitTest1.cs As**.</span></span> <span data-ttu-id="71d4b-187">В диалоговом окне **Сохранить файл как** щелкните стрелку рядом с кнопкой **Сохранить** и выберите вариант **Сохранить с кодировкой**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-187">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   ![Диалоговое окно "Сохранить файл как" в Visual Studio (C#)](./media/testing-library-with-visual-studio/save-file-as-dialog.png)

# <a name="visual-basictabvb"></a>[<span data-ttu-id="71d4b-189">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="71d4b-189">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="71d4b-190">В окне кода *UnitTest1.vb* замените отображаемый код на следующий текст:</span><span class="sxs-lookup"><span data-stu-id="71d4b-190">In the *UnitTest1.vb* code window, replace the code with the following code:</span></span>

    [!code-vb[Test#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   <span data-ttu-id="71d4b-191">Обратите внимание, что наш тест на символы верхнего регистра в методе `TestStartsWithUpper` включает заглавную греческую букву "альфа" (U+0391) и заглавную кириллическую букву "М" (U+041C). Тест на символы нижнего регистра в методе `TestDoesNotStartWithUpper` включает строчную греческую букву "альфа" (U+03B1) и строчную кириллическую букву "г" (U+0433).</span><span class="sxs-lookup"><span data-stu-id="71d4b-191">Note that your test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C), and the test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="71d4b-192">В строке меню выберите **Файл** > **Сохранить UnitTest1.vb как**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-192">On the menu bar, select **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="71d4b-193">В диалоговом окне **Сохранить файл как** щелкните стрелку рядом с кнопкой **Сохранить** и выберите вариант **Сохранить с кодировкой**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-193">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   ![Диалоговое окно "Сохранить файл как" в Visual Studio (Visual Basic)](./media/testing-library-with-visual-studio/save-file-as-dialog.png)

---

1. <span data-ttu-id="71d4b-195">В диалоговом окне **Подтверждение сохранения** нажмите кнопку **Да**, чтобы сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="71d4b-195">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="71d4b-196">В диалоговом окне **Дополнительные параметры сохранения** выберите в раскрывающемся списка **Кодировка** вариант **Юникод (UTF-8, с сигнатурой), кодовая страница 65001** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-196">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   ![Диалоговое окно "Дополнительные параметры сохранения" в Visual Studio](./media/testing-library-with-visual-studio/advanced-save-options.png)

   <span data-ttu-id="71d4b-198">Если вы не сохраните исходный код в кодировке UTF8, Visual Studio может сохранить его как файл ASCII.</span><span class="sxs-lookup"><span data-stu-id="71d4b-198">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="71d4b-199">В этом случае среде выполнения не удастся правильно раскодировать символы UTF8 за пределами стандартного диапазона ASCII, и результаты теста будут неточными.</span><span class="sxs-lookup"><span data-stu-id="71d4b-199">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be accurate.</span></span>

1. <span data-ttu-id="71d4b-200">В строке меню выберите **Тест** > **Выполнить** > **Все тесты**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-200">On the menu bar, select **Test** > **Run** > **All Tests**.</span></span> <span data-ttu-id="71d4b-201">Откроется окно **Обозреватель тестов**, и появится сообщение о том, что тесты успешно выполнены.</span><span class="sxs-lookup"><span data-stu-id="71d4b-201">The **Test Explorer** window opens and shows that the tests ran successfully.</span></span> <span data-ttu-id="71d4b-202">В разделе **Пройденные тесты** перечислены три теста, а раздел **Сводка** содержит результат тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="71d4b-202">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   ![Окно "Обозреватель тестов" с пройденными тестами](./media/testing-library-with-visual-studio/test-explorer-window.png)

## <a name="handling-test-failures"></a><span data-ttu-id="71d4b-204">Обработка сбоев при тестах</span><span class="sxs-lookup"><span data-stu-id="71d4b-204">Handling test failures</span></span>

<span data-ttu-id="71d4b-205">Тестовый запуск прошел без ошибок, а теперь давайте немного изменим его, чтобы один из методов теста завершался сбоем:</span><span class="sxs-lookup"><span data-stu-id="71d4b-205">Your test run had no failures, but change it slightly so that one of the test methods fails:</span></span>

1. <span data-ttu-id="71d4b-206">Измените массив `words` в методе `TestDoesNotStartWithUpper`, включив в него строку "Error".</span><span class="sxs-lookup"><span data-stu-id="71d4b-206">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="71d4b-207">Сохранять файл не требуется, поскольку при сборке решения для выполнения тестов Visual Studio автоматически сохраняет открытые файлы.</span><span class="sxs-lookup"><span data-stu-id="71d4b-207">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="71d4b-208">Выполните тест, последовательно выбрав в строке меню пункты **Тест** > **Выполнить** > **Все тесты**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-208">Run the test by selecting **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="71d4b-209">В окне **Обозреватель тестов** будет указано, что два теста выполнены успешно, а третий завершился ошибкой.</span><span class="sxs-lookup"><span data-stu-id="71d4b-209">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   ![Окно "Обозреватель тестов" с тестами, которые завершились ошибкой](./media/testing-library-with-visual-studio/failed-test-window.png)

1. <span data-ttu-id="71d4b-211">Выберите в разделе **Неудачные тесты** тест `TestDoesNotStartWith`, который завершился ошибкой.</span><span class="sxs-lookup"><span data-stu-id="71d4b-211">In the **Failed Tests** section, select the failed test, `TestDoesNotStartWith`.</span></span> <span data-ttu-id="71d4b-212">В окне **Обозреватель тестов** появится сообщение, созданное методом утверждения "Assert.IsFalse failed.</span><span class="sxs-lookup"><span data-stu-id="71d4b-212">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="71d4b-213">Expected for 'Error': false; actual: True".</span><span class="sxs-lookup"><span data-stu-id="71d4b-213">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="71d4b-214">Из-за этого сбоя все строки в массиве, расположенные после слова "Error", не проверялись.</span><span class="sxs-lookup"><span data-stu-id="71d4b-214">Because of the failure, all strings in the array after "Error" were not tested.</span></span>

   ![Окно "Обозреватель тестов" с сообщением о том, что утверждение Is False ошибочно](./media/testing-library-with-visual-studio/failed-test-detail.png)

1. <span data-ttu-id="71d4b-216">Отмените изменение, которое вы внесли на шаге 1, и удалите строку "Error".</span><span class="sxs-lookup"><span data-stu-id="71d4b-216">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="71d4b-217">Еще раз запустите тест. Теперь тесты будут пройдены.</span><span class="sxs-lookup"><span data-stu-id="71d4b-217">Rerun the test and the tests will pass.</span></span>

## <a name="testing-the-release-version-of-the-library"></a><span data-ttu-id="71d4b-218">Тестирование версии выпуска для библиотеки</span><span class="sxs-lookup"><span data-stu-id="71d4b-218">Testing the Release version of the library</span></span>

<span data-ttu-id="71d4b-219">До сих пор вы выполняли тесты с отладочной версией библиотеки.</span><span class="sxs-lookup"><span data-stu-id="71d4b-219">You've been running your tests against the Debug version of the library.</span></span> <span data-ttu-id="71d4b-220">Теперь, когда все созданные тесты пройдены и вы достаточно подробно проверили работу библиотеки, выполните все тесты еще раз, теперь уже для сборки выпуска библиотеки.</span><span class="sxs-lookup"><span data-stu-id="71d4b-220">Now that your tests have all passed and you've adequately tested your library, you should run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="71d4b-221">Некоторые факторы, например оптимизации компилятора, иногда могут вызывать разное поведение сборки в режимах отладки и выпуска.</span><span class="sxs-lookup"><span data-stu-id="71d4b-221">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="71d4b-222">Протестируйте сборку выпуска следующим образом.</span><span class="sxs-lookup"><span data-stu-id="71d4b-222">To test the Release build:</span></span>

1. <span data-ttu-id="71d4b-223">В панели инструментов Visual Studio измените конфигурацию сборки с режима **Отладка** на **Выпуск**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-223">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   ![Панель инструментов Visual Studio с выделенной сборкой выпуска](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="71d4b-225">В **обозревателе решений** щелкните проект **StringLibrary** правой кнопкой мыши и выберите в контекстном меню пункт **Сборка**, чтобы выполнить повторную компиляцию библиотеки.</span><span class="sxs-lookup"><span data-stu-id="71d4b-225">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   ![Контекстное меню проекта StringLibrary с командой сборки](./media/testing-library-with-visual-studio/build-library-context-menu.png)

1. <span data-ttu-id="71d4b-227">Выполните модульные тесты, выбрав в строке меню **Тест** > **Выполнить** > **Все тесты**.</span><span class="sxs-lookup"><span data-stu-id="71d4b-227">Run the unit tests by choosing **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="71d4b-228">Все тесты будут пройдены.</span><span class="sxs-lookup"><span data-stu-id="71d4b-228">The tests pass.</span></span>

<span data-ttu-id="71d4b-229">Теперь вы полностью завершили тестирование библиотеки, и ее можно предоставить пользователям.</span><span class="sxs-lookup"><span data-stu-id="71d4b-229">Now that you've finished testing your library, the next step is to make it available to callers.</span></span> <span data-ttu-id="71d4b-230">Ее можно включить в состав любого приложения или нескольких приложений, а также предоставить в виде пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="71d4b-230">You can bundle it with one or more applications, or you can distribute it as a NuGet package.</span></span> <span data-ttu-id="71d4b-231">Дополнительные сведения см. в статье [Использование стандартной библиотеки классов для .NET Core в Visual Studio](./consuming-library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="71d4b-231">For more information, see [Consuming a .NET Standard Class Library](./consuming-library-with-visual-studio.md).</span></span>
