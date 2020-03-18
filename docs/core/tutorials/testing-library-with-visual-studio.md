---
title: Тестирование библиотеки классов .NET Standard с помощью .NET Core в Visual Studio
description: Создайте проект модульного теста для библиотеки классов .NET Core. Проверьте правильность работы библиотеки классов .NET Core с помощью модульных тестов.
ms.date: 12/24/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet, seodoc18
ms.openlocfilehash: 307261088f5c7c69c0e69fbd6b99940c04842eec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156625"
---
# <a name="test-a-net-standard-library-with-net-core-in-visual-studio"></a><span data-ttu-id="48616-104">Тестирование библиотеки .NET Standard с помощью .NET Core в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="48616-104">Test a .NET Standard library with .NET Core in Visual Studio</span></span>

<span data-ttu-id="48616-105">Работая со статьей [Создание библиотеки .NET Standard на C# с помощью пакета SDK для .NET Core в Visual Studio 2017](library-with-visual-studio.md), вы уже создали простую библиотеку классов, которая добавляет метод расширения к классу <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="48616-105">In [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md), you created a simple class library that adds an extension method to the <xref:System.String> class.</span></span> <span data-ttu-id="48616-106">Теперь вы создадите модульный тест и убедитесь, что все работает правильно.</span><span class="sxs-lookup"><span data-stu-id="48616-106">Now, you'll create a unit test to make sure that it works as expected.</span></span> <span data-ttu-id="48616-107">Новый проект модульного теста вы добавите к решению, созданному при работе с предыдущей статьей.</span><span class="sxs-lookup"><span data-stu-id="48616-107">You'll add your unit test project to the solution you created in the previous article.</span></span>

## <a name="create-a-unit-test-project"></a><span data-ttu-id="48616-108">Создание проекта модульного теста</span><span class="sxs-lookup"><span data-stu-id="48616-108">Create a unit test project</span></span>

<span data-ttu-id="48616-109">Чтобы создать проект модульного теста, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="48616-109">To create the unit test project, do the following:</span></span>

1. <span data-ttu-id="48616-110">Откройте решение`ClassLibraryProjects`, созданное при работе со статьей [Создание библиотеки .NET Standard на C# с помощью пакета SDK для .NET Core в Visual Studio 2017](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="48616-110">Open the `ClassLibraryProjects` solution you created in the [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md) article.</span></span>

1. <span data-ttu-id="48616-111">Добавьте в решение новый проект модульного теста с именем StringLibraryTest.</span><span class="sxs-lookup"><span data-stu-id="48616-111">Add a new unit test project named "StringLibraryTest" to the solution.</span></span>

   1. <span data-ttu-id="48616-112">Щелкните решение в **обозревателе решений** правой кнопкой мыши и выберите **Добавить** > **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="48616-112">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="48616-113">На странице **Добавить новый проект** введите в поле поиска **mstest**.</span><span class="sxs-lookup"><span data-stu-id="48616-113">On the **Add a new project** page, enter **mstest** in the search box.</span></span> <span data-ttu-id="48616-114">Выберите **C#** или **Visual Basic** из списка языков, а затем — **Все платформы** из списка платформ.</span><span class="sxs-lookup"><span data-stu-id="48616-114">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="48616-115">Выберите шаблон **Проект тестов MSTest (.NET Core)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="48616-115">Choose the **MsTest Test Project (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="48616-116">На странице **Настроить новый проект** введите **StringLibraryTest** в поле **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="48616-116">On the **Configure your new project** page, enter **StringLibraryTest** in the **Project name** box.</span></span> <span data-ttu-id="48616-117">Щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="48616-117">Then choose **Create**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="48616-118">Кроме MSTest, можно также создать тестовые проекты xUnit и nUnit для .NET Core в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="48616-118">In addition to an MSTest, you can also create xUnit and nUnit test projects for .NET Core in Visual Studio.</span></span>

1. <span data-ttu-id="48616-119">Visual Studio создаст проект и откроет файл класса в окне кода с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="48616-119">Visual Studio creates the project and opens the class file in the code window with the following code:</span></span>

   ```csharp
   using Microsoft.VisualStudio.TestTools.UnitTesting;

    namespace StringLibraryTest
    {
        [TestClass]
        public class UnitTest1
        {
            [TestMethod]
            public void TestMethod1()
            {
            }
        }
    }
    ```

    ```vb
    Imports Microsoft.VisualStudio.TestTools.UnitTesting

    Namespace StringLibraryTest
        <TestClass>
        Public Class UnitTest1
            <TestMethod>
            Sub TestSub()

            End Sub
        End Class
    End Namespace
    ```

   <span data-ttu-id="48616-120">Исходный код, созданный шаблоном модульного теста, выполняет следующие действия.</span><span class="sxs-lookup"><span data-stu-id="48616-120">The source code created by the unit test template does the following:</span></span>

   - <span data-ttu-id="48616-121">Он импортирует пространство имен <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType>, которое содержит типы, используемые для модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="48616-121">It imports the <xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=nameWithType> namespace, which contains the types used for unit testing.</span></span>

   - <span data-ttu-id="48616-122">Он применяет атрибут [TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) к классу `UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="48616-122">It applies the [TestClass](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute) attribute to the `UnitTest1` class.</span></span> <span data-ttu-id="48616-123">При запуске модульного теста автоматически выполняются все методы теста в тестовом классе, помеченные атрибутом [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute).</span><span class="sxs-lookup"><span data-stu-id="48616-123">Each test method in a test class tagged with the [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) attribute is executed automatically when the unit test is run.</span></span>

   - <span data-ttu-id="48616-124">Атрибут [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) определяет `TestMethod1` в C# или `TestSub` в Visual Basic как метод теста, который будет автоматически выполняться при запуске модульного теста.</span><span class="sxs-lookup"><span data-stu-id="48616-124">It applies the [TestMethod](xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute) attribute to define `TestMethod1` in C# or `TestSub` in Visual Basic as a test method for automatic execution when the unit test is run.</span></span>

1. <span data-ttu-id="48616-125">В **обозревателе решений** щелкните узел **Зависимости** в проекте **StringLibraryTest** правой кнопкой мыши и выберите в контекстном меню пункт **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="48616-125">In **Solution Explorer**, right-click the **Dependencies** node of the **StringLibraryTest** project and select **Add Reference** from the context menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48616-126">![Контекстное меню узла "Зависимости" в проекте StringLibraryTest](./media/testing-library-with-visual-studio/add-reference-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="48616-126">![Context menu of StringLibraryTest dependencies](./media/testing-library-with-visual-studio/add-reference-context-menu.png)</span></span>

1. <span data-ttu-id="48616-127">В диалоговом окне **Диспетчер ссылок** разверните узел **Проекты** и установите флажок рядом с пунктом **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="48616-127">In the **Reference Manager** dialog, expand the **Projects** node and check the box next to **StringLibrary**.</span></span> <span data-ttu-id="48616-128">Добавление ссылки на сборку `StringLibrary` позволяет компилятору находить методы **StringLibrary**.</span><span class="sxs-lookup"><span data-stu-id="48616-128">Adding a reference to the `StringLibrary` assembly allows the compiler to find **StringLibrary** methods.</span></span> <span data-ttu-id="48616-129">Нажмите кнопку **OK**.</span><span class="sxs-lookup"><span data-stu-id="48616-129">Select the **OK** button.</span></span> <span data-ttu-id="48616-130">Добавляется ссылка на ваш проект библиотеки классов `StringLibrary`.</span><span class="sxs-lookup"><span data-stu-id="48616-130">A reference is added to your class library project, `StringLibrary`.</span></span>

   ![Диалоговое окно "Диспетчер ссылок" в Visual Studio](./media/testing-library-with-visual-studio/project-reference-manager.png)

## <a name="add-and-run-unit-test-methods"></a><span data-ttu-id="48616-132">Добавление и выполнение методов модульного теста</span><span class="sxs-lookup"><span data-stu-id="48616-132">Add and run unit test methods</span></span>

<span data-ttu-id="48616-133">При запуске модульного теста Visual Studio выполняет каждый метод, помеченный атрибутом <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute>, из класса модульных тестов (это класс, к которому применяется атрибут <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>).</span><span class="sxs-lookup"><span data-stu-id="48616-133">When Visual Studio runs a unit test, it executes each method that is marked with the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute> attribute in a unit test class, the class to which the  <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute> attribute is applied.</span></span> <span data-ttu-id="48616-134">Метод теста завершается, когда происходит первый сбой или когда все тесты, содержащиеся в методе, будут успешно выполнены.</span><span class="sxs-lookup"><span data-stu-id="48616-134">A test method ends when the first failure is found or when all tests contained in the method have succeeded.</span></span>

<span data-ttu-id="48616-135">В самых распространенных тестах вызываются члены класса <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>.</span><span class="sxs-lookup"><span data-stu-id="48616-135">The most common tests call members of the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> class.</span></span> <span data-ttu-id="48616-136">Многие методы утверждения (Assert) принимают по крайней мере два параметра, из которых один представляет ожидаемый результат теста, а второй — фактический результат теста.</span><span class="sxs-lookup"><span data-stu-id="48616-136">Many assert methods include at least two parameters, one of which is the expected test result and the other of which is the actual test result.</span></span> <span data-ttu-id="48616-137">Наиболее популярные из этих методов класса `Assert` перечислены в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="48616-137">Some of the `Assert` class's most frequently called methods are shown in the following table:</span></span>

| <span data-ttu-id="48616-138">Методы утверждения</span><span class="sxs-lookup"><span data-stu-id="48616-138">Assert methods</span></span>     | <span data-ttu-id="48616-139">Компонент</span><span class="sxs-lookup"><span data-stu-id="48616-139">Function</span></span> |
| ------------------ | -------- |
| `Assert.AreEqual`  | <span data-ttu-id="48616-140">Проверяет равенство двух значений или объектов.</span><span class="sxs-lookup"><span data-stu-id="48616-140">Verifies that two values or objects are equal.</span></span> <span data-ttu-id="48616-141">Утверждение не выполняется, если значения или объекты не равны.</span><span class="sxs-lookup"><span data-stu-id="48616-141">The assert fails if the values or objects aren't equal.</span></span> |
| `Assert.AreSame`   | <span data-ttu-id="48616-142">Проверяет, что две объектные переменные ссылаются на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="48616-142">Verifies that two object variables refer to the same object.</span></span> <span data-ttu-id="48616-143">Утверждение не выполняется, если переменные ссылаются на разные объекты.</span><span class="sxs-lookup"><span data-stu-id="48616-143">The assert fails if the variables refer to different objects.</span></span> |
| `Assert.IsFalse`   | <span data-ttu-id="48616-144">Проверяет, что условие имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="48616-144">Verifies that a condition is `false`.</span></span> <span data-ttu-id="48616-145">Утверждение не выполняется, если условие имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="48616-145">The assert fails if the condition is `true`.</span></span> |
| `Assert.IsNotNull` | <span data-ttu-id="48616-146">Проверяет, что объект не имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="48616-146">Verifies that an object isn't `null`.</span></span> <span data-ttu-id="48616-147">Утверждение не выполняется, если объект является `null`.</span><span class="sxs-lookup"><span data-stu-id="48616-147">The assert fails if the object is `null`.</span></span> |

<span data-ttu-id="48616-148">Вы можете также использовать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A> в методе теста, чтобы указать тип исключения, которое он должен создавать.</span><span class="sxs-lookup"><span data-stu-id="48616-148">You can also use the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A> method in a test method to indicate the type of exception it's expected to throw.</span></span> <span data-ttu-id="48616-149">Такой тест считается не выполненным, если заявленное исключение не было создано.</span><span class="sxs-lookup"><span data-stu-id="48616-149">The test fails if the specified exception isn't thrown.</span></span>

<span data-ttu-id="48616-150">Для тестирования метода `StringLibrary.StartsWithUpper` необходимо предоставить несколько строк, которые начинаются с символов верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="48616-150">In testing the `StringLibrary.StartsWithUpper` method, you want to provide a number of strings that begin with an uppercase character.</span></span> <span data-ttu-id="48616-151">Предполагается, что в этих случаях метод возвратит `true`, поэтому можно вызвать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A>.</span><span class="sxs-lookup"><span data-stu-id="48616-151">You expect the method to return `true` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue%2A> method.</span></span> <span data-ttu-id="48616-152">Представьте также несколько строк, которые не начинаются с символов верхнего регистра.</span><span class="sxs-lookup"><span data-stu-id="48616-152">Similarly, you want to provide a number of strings that begin with something other than an uppercase character.</span></span> <span data-ttu-id="48616-153">Предполагается, что в этих случаях метод возвратит `false`, поэтому можно вызвать метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A>.</span><span class="sxs-lookup"><span data-stu-id="48616-153">You expect the method to return `false` in these cases, so you can call the <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse%2A> method.</span></span>

<span data-ttu-id="48616-154">Так как ваш метод библиотеки обрабатывает строки, нам нужно проверить правильность обработки [пустых строк (`String.Empty`)](xref:System.String.Empty) (так называется допустимая строка, которая не содержит символов и для которой свойство <xref:System.String.Length> имеет значение 0) и строки `null`, которая не была инициализирована.</span><span class="sxs-lookup"><span data-stu-id="48616-154">Since your library method handles strings, you also want to make sure that it successfully handles an [empty string (`String.Empty`)](xref:System.String.Empty), a valid string that has no characters and whose <xref:System.String.Length> is 0, and a `null` string that hasn't been initialized.</span></span> <span data-ttu-id="48616-155">Если `StartsWithUpper` вызывается в качестве метода расширения для экземпляра <xref:System.String>, ему нельзя передавать строку `null`.</span><span class="sxs-lookup"><span data-stu-id="48616-155">If `StartsWithUpper` is called as an extension method on a <xref:System.String> instance, it can't be passed a `null` string.</span></span> <span data-ttu-id="48616-156">Однако его можно вызвать напрямую как статический метод и передать ему один аргумент типа <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="48616-156">However, you can also call it directly as a static method and pass a single <xref:System.String> argument.</span></span>

<span data-ttu-id="48616-157">Вы определите три метода, каждый из которых поочередно вызывает метод <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> для каждого элемента в массиве строк.</span><span class="sxs-lookup"><span data-stu-id="48616-157">You'll define three methods, each of which calls an <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> method repeatedly for each element in a string array.</span></span> <span data-ttu-id="48616-158">Так как метод теста завершается ошибкой при первом же сбое, вы вызовете перегруженную версию метода, которая позволяет передать строку и указать строковое значение, используемое в вызове метода.</span><span class="sxs-lookup"><span data-stu-id="48616-158">Because the test method fails as soon as it finds the first failure, you'll call a method overload that allows you to pass a string that indicates the string value used in the method call.</span></span>

<span data-ttu-id="48616-159">Создание методов теста:</span><span class="sxs-lookup"><span data-stu-id="48616-159">To create the test methods:</span></span>

1. <span data-ttu-id="48616-160">В окне кода *UnitTest1.cs* или *UnitTest1.vb* замените отображаемый код на следующий текст:</span><span class="sxs-lookup"><span data-stu-id="48616-160">In the *UnitTest1.cs* or *UnitTest1.vb* code window, replace the code with the following code:</span></span>

   [!code-csharp[Test#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs)]
   [!code-vb[Test#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/testlib.vb)]

   <span data-ttu-id="48616-161">Тест на символы верхнего регистра в методе `TestStartsWithUpper` включает заглавную греческую букву "альфа" (U+0391) и заглавную кириллическую букву "М" (U+041C).</span><span class="sxs-lookup"><span data-stu-id="48616-161">The test of uppercase characters in the `TestStartsWithUpper` method includes the Greek capital letter alpha (U+0391) and the Cyrillic capital letter EM (U+041C).</span></span> <span data-ttu-id="48616-162">Тест на символы нижнего регистра в методе `TestDoesNotStartWithUpper` включает строчную греческую букву "альфа" (U+03B1) и строчную кириллическую букву "г" (U+0433).</span><span class="sxs-lookup"><span data-stu-id="48616-162">The test of lowercase characters in the `TestDoesNotStartWithUpper` method includes the Greek small letter alpha (U+03B1) and the Cyrillic small letter Ghe (U+0433).</span></span>

1. <span data-ttu-id="48616-163">В строке меню выберите **Файл** > **Сохранить UnitTest1.cs как** или **Файл** > **Сохранить UnitTest1.vb как**.</span><span class="sxs-lookup"><span data-stu-id="48616-163">On the menu bar, select **File** > **Save UnitTest1.cs As** or **File** > **Save UnitTest1.vb As**.</span></span> <span data-ttu-id="48616-164">В диалоговом окне **Сохранить файл как** щелкните стрелку рядом с кнопкой **Сохранить** и выберите вариант **Сохранить с кодировкой**.</span><span class="sxs-lookup"><span data-stu-id="48616-164">In the **Save File As** dialog, select the arrow beside the **Save** button, and select **Save with Encoding**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48616-165">![Диалоговое окно "Сохранить файл как" в Visual Studio](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="48616-165">![Visual Studio Save File As dialog](./media/testing-library-with-visual-studio/save-file-as-dialog.png)</span></span>

1. <span data-ttu-id="48616-166">В диалоговом окне **Подтверждение сохранения** нажмите кнопку **Да**, чтобы сохранить файл.</span><span class="sxs-lookup"><span data-stu-id="48616-166">In the **Confirm Save As** dialog, select the **Yes** button to save the file.</span></span>

1. <span data-ttu-id="48616-167">В диалоговом окне **Дополнительные параметры сохранения** выберите в раскрывающемся списка **Кодировка** вариант **Юникод (UTF-8, с сигнатурой), кодовая страница 65001** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="48616-167">In the **Advanced Save Options** dialog, select **Unicode (UTF-8 with signature) - Codepage 65001** from the **Encoding** drop-down list and select **OK**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48616-168">![Диалоговое окно "Дополнительные параметры сохранения" в Visual Studio](./media/testing-library-with-visual-studio/advanced-save-options.png)</span><span class="sxs-lookup"><span data-stu-id="48616-168">![Visual Studio Advanced Save Options dialog](./media/testing-library-with-visual-studio/advanced-save-options.png)</span></span>

   <span data-ttu-id="48616-169">Если вы не сохраните исходный код в кодировке UTF8, Visual Studio может сохранить его как файл ASCII.</span><span class="sxs-lookup"><span data-stu-id="48616-169">If you fail to save your source code as a UTF8-encoded file, Visual Studio may save it as an ASCII file.</span></span> <span data-ttu-id="48616-170">В этом случае среде выполнения не удастся правильно раскодировать символы UTF8 за пределами стандартного диапазона ASCII, и результаты теста будут неправильными.</span><span class="sxs-lookup"><span data-stu-id="48616-170">When that happens, the runtime doesn't accurately decode the UTF8 characters outside of the ASCII range, and the test results won't be correct.</span></span>

1. <span data-ttu-id="48616-171">В строке меню выберите **Тест** > **Выполнить** > **Все тесты**.</span><span class="sxs-lookup"><span data-stu-id="48616-171">On the menu bar, select **Test** > **Run** > **All Tests**.</span></span> <span data-ttu-id="48616-172">Откроется окно **Обозреватель тестов**, и появится сообщение о том, что тесты успешно выполнены.</span><span class="sxs-lookup"><span data-stu-id="48616-172">The **Test Explorer** window opens and shows that the tests ran successfully.</span></span> <span data-ttu-id="48616-173">В разделе **Пройденные тесты** перечислены три теста, а раздел **Сводка** содержит результат тестового запуска.</span><span class="sxs-lookup"><span data-stu-id="48616-173">The three tests are listed in the **Passed Tests** section, and the **Summary** section reports the result of the test run.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48616-174">![Окно "Обозреватель тестов" с пройденными тестами](./media/testing-library-with-visual-studio/test-explorer-window.png)</span><span class="sxs-lookup"><span data-stu-id="48616-174">![Test Explorer window with passing tests](./media/testing-library-with-visual-studio/test-explorer-window.png)</span></span>

## <a name="handle-test-failures"></a><span data-ttu-id="48616-175">Обработка сбоев теста</span><span class="sxs-lookup"><span data-stu-id="48616-175">Handle test failures</span></span>

<span data-ttu-id="48616-176">Тестовый запуск прошел без ошибок, а теперь давайте немного изменим его, чтобы один из методов теста завершался сбоем:</span><span class="sxs-lookup"><span data-stu-id="48616-176">Your test run had no failures, but change it slightly so that one of the test methods fails:</span></span>

1. <span data-ttu-id="48616-177">Измените массив `words` в методе `TestDoesNotStartWithUpper`, включив в него строку "Error".</span><span class="sxs-lookup"><span data-stu-id="48616-177">Modify the `words` array in the `TestDoesNotStartWithUpper` method to include the string "Error".</span></span> <span data-ttu-id="48616-178">Сохранять файл не требуется, поскольку при сборке решения для выполнения тестов Visual Studio автоматически сохраняет открытые файлы.</span><span class="sxs-lookup"><span data-stu-id="48616-178">You don't need to save the file because Visual Studio automatically saves open files when a solution is built to run tests.</span></span>

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

   ```vb
   Dim words() As String = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " }

   ```

1. <span data-ttu-id="48616-179">Выполните тест, последовательно выбрав в строке меню пункты **Тест** > **Выполнить** > **Все тесты**.</span><span class="sxs-lookup"><span data-stu-id="48616-179">Run the test by selecting **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="48616-180">В окне **Обозреватель тестов** будет указано, что два теста выполнены успешно, а третий завершился ошибкой.</span><span class="sxs-lookup"><span data-stu-id="48616-180">The **Test Explorer** window indicates that two tests succeeded and one failed.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48616-181">![Окно "Обозреватель тестов" с тестами, которые завершились ошибкой](./media/testing-library-with-visual-studio/failed-test-window.png)</span><span class="sxs-lookup"><span data-stu-id="48616-181">![Test Explorer window with failing tests](./media/testing-library-with-visual-studio/failed-test-window.png)</span></span>

1. <span data-ttu-id="48616-182">Выберите непройденный тест `TestDoesNotStartWith`.</span><span class="sxs-lookup"><span data-stu-id="48616-182">Select the failed test, `TestDoesNotStartWith`.</span></span> <span data-ttu-id="48616-183">В окне **Обозреватель тестов** появится сообщение, созданное методом утверждения: "Assert.IsFalse failed.</span><span class="sxs-lookup"><span data-stu-id="48616-183">The **Test Explorer** window displays the message produced by the assert: "Assert.IsFalse failed.</span></span> <span data-ttu-id="48616-184">Expected for 'Error': false; actual: True".</span><span class="sxs-lookup"><span data-stu-id="48616-184">Expected for 'Error': false; actual: True".</span></span> <span data-ttu-id="48616-185">Из-за этого сбоя все строки в массиве, расположенные после слова Error, не проверялись.</span><span class="sxs-lookup"><span data-stu-id="48616-185">Because of the failure, all strings in the array after "Error" weren't tested.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48616-186">![Окно "Обозреватель тестов" с сообщением о том, что утверждение IsFalse ошибочно](./media/testing-library-with-visual-studio/failed-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="48616-186">![Test Explorer window showing the IsFalse assertion failure](./media/testing-library-with-visual-studio/failed-test-detail.png)</span></span>

1. <span data-ttu-id="48616-187">Отмените изменение, которое вы внесли на шаге 1, и удалите строку "Error".</span><span class="sxs-lookup"><span data-stu-id="48616-187">Undo the modification you did in step 1 and remove the string "Error".</span></span> <span data-ttu-id="48616-188">Еще раз запустите тест. Теперь тесты будут пройдены.</span><span class="sxs-lookup"><span data-stu-id="48616-188">Rerun the test and the tests will pass.</span></span>

## <a name="test-the-release-version-of-the-library"></a><span data-ttu-id="48616-189">Тестирование версии выпуска для библиотеки</span><span class="sxs-lookup"><span data-stu-id="48616-189">Test the Release version of the library</span></span>

<span data-ttu-id="48616-190">До сих пор вы выполняли тесты с отладочной версией библиотеки.</span><span class="sxs-lookup"><span data-stu-id="48616-190">You've been running your tests against the Debug version of the library.</span></span> <span data-ttu-id="48616-191">Теперь, когда все созданные тесты пройдены и вы достаточно подробно проверили работу библиотеки, выполните все тесты еще раз, теперь уже для сборки выпуска библиотеки.</span><span class="sxs-lookup"><span data-stu-id="48616-191">Now that your tests have all passed and you've adequately tested your library, you should run the tests an additional time against the Release build of the library.</span></span> <span data-ttu-id="48616-192">Некоторые факторы, например оптимизации компилятора, иногда могут вызывать разное поведение сборки в режимах отладки и выпуска.</span><span class="sxs-lookup"><span data-stu-id="48616-192">A number of factors, including compiler optimizations, can sometimes produce different behavior between Debug and Release builds.</span></span>

<span data-ttu-id="48616-193">Протестируйте сборку выпуска следующим образом.</span><span class="sxs-lookup"><span data-stu-id="48616-193">To test the Release build:</span></span>

1. <span data-ttu-id="48616-194">В панели инструментов Visual Studio измените конфигурацию сборки с режима **Отладка** на **Выпуск**.</span><span class="sxs-lookup"><span data-stu-id="48616-194">In the Visual Studio toolbar, change the build configuration from **Debug** to **Release**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48616-195">![Панель инструментов Visual Studio с выделенной сборкой выпуска](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span><span class="sxs-lookup"><span data-stu-id="48616-195">![Visual Studio toolbar with release build highlighted](./media/testing-library-with-visual-studio/visual-studio-toolbar-release.png)</span></span>

1. <span data-ttu-id="48616-196">В **обозревателе решений** щелкните проект **StringLibrary** правой кнопкой мыши и выберите в контекстном меню пункт **Сборка**, чтобы выполнить повторную компиляцию библиотеки.</span><span class="sxs-lookup"><span data-stu-id="48616-196">In **Solution Explorer**, right-click the **StringLibrary** project and select **Build** from the context menu to recompile the library.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="48616-197">![Контекстное меню проекта StringLibrary с командой сборки](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span><span class="sxs-lookup"><span data-stu-id="48616-197">![StringLibrary context menu with build command](./media/testing-library-with-visual-studio/build-library-context-menu.png)</span></span>

1. <span data-ttu-id="48616-198">Выполните модульные тесты, выбрав в строке меню **Тест** > **Выполнить** > **Все тесты**.</span><span class="sxs-lookup"><span data-stu-id="48616-198">Run the unit tests by choosing **Test** > **Run** > **All Tests** from the menu bar.</span></span> <span data-ttu-id="48616-199">Все тесты будут пройдены.</span><span class="sxs-lookup"><span data-stu-id="48616-199">The tests pass.</span></span>

<span data-ttu-id="48616-200">Теперь вы полностью завершили тестирование библиотеки, и ее можно предоставить пользователям.</span><span class="sxs-lookup"><span data-stu-id="48616-200">Now that you've finished testing your library, the next step is to make it available to callers.</span></span> <span data-ttu-id="48616-201">Ее можно включить в состав любого приложения или нескольких приложений, а также предоставить в виде пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="48616-201">You can bundle it with one or more applications, or you can distribute it as a NuGet package.</span></span> <span data-ttu-id="48616-202">Дополнительные сведения см. в статье [Использование стандартной библиотеки классов для .NET Core в Visual Studio](consuming-library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="48616-202">For more information, see [Consuming a .NET Standard Class Library](consuming-library-with-visual-studio.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="48616-203">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="48616-203">See also</span></span>

- [<span data-ttu-id="48616-204">Основные сведения о модульных тестах</span><span class="sxs-lookup"><span data-stu-id="48616-204">Unit test basics - Visual Studio</span></span>](/visualstudio/test/unit-test-basics)
