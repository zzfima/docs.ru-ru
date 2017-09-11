---
title: "Создание полного решения .NET Core в Windows с помощью Visual Studio 2017"
description: "Сведения о создании полного решения .NET Core с помощью Visual Studio 2017 в Windows."
keywords: .NET, .NET Core
author: bleroy
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ba7e082c-a7c8-431e-a342-f67734b660f6
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6b164198f5fbbae5ebc6164fc281dd7de8172b70
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="building-a-complete-net-core-solution-on-windows-using-visual-studio-2017"></a><span data-ttu-id="a8971-104">Создание полного решения .NET Core в Windows с помощью Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="a8971-104">Building a complete .NET Core solution on Windows, using Visual Studio 2017</span></span>

<span data-ttu-id="a8971-105">Visual Studio 2017 предоставляет полнофункциональную среду для разработки приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a8971-105">Visual Studio 2017 provides a full-featured development environment for developing .NET Core applications.</span></span> <span data-ttu-id="a8971-106">Процедуры в этом документе описывают шаги, необходимые для построения стандартного решения .NET Core, которое включает повторно используемые библиотеки, тестирование и использование сторонних библиотек.</span><span class="sxs-lookup"><span data-stu-id="a8971-106">The procedures in this document describe the steps necessary to build a typical .NET Core solution that includes reusable libraries, testing, and using third-party libraries.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a8971-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="a8971-107">Prerequisites</span></span>

<span data-ttu-id="a8971-108">Чтобы обновить среду, выполните инструкции на [странице с описанием предварительных требований](../windows-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="a8971-108">Follow the instructions on [our prerequisites page](../windows-prerequisites.md) to update your environment.</span></span>

## <a name="a-solution-using-only-net-core-projects"></a><span data-ttu-id="a8971-109">Решение на основе только проектов .NET Core</span><span class="sxs-lookup"><span data-stu-id="a8971-109">A solution using only .NET Core projects</span></span>

### <a name="writing-the-library"></a><span data-ttu-id="a8971-110">Написание библиотеки</span><span class="sxs-lookup"><span data-stu-id="a8971-110">Writing the library</span></span>

1. <span data-ttu-id="a8971-111">В Visual Studio последовательно щелкните **Файл**, **Создать**, **Проект**.</span><span class="sxs-lookup"><span data-stu-id="a8971-111">In Visual Studio, choose **File**, **New**, **Project**.</span></span> <span data-ttu-id="a8971-112">В диалоговом окне **Новый проект** разверните узел **Visual C#**, выберите узел **.NET Core**, а затем выберите шаблон **Библиотека классов (.NET Standard)**.</span><span class="sxs-lookup"><span data-stu-id="a8971-112">In the **New Project** dialog, expand the **Visual C#** node and choose the **.NET Core** node, and then choose **Class Library (.NET Standard)**.</span></span> 

2. <span data-ttu-id="a8971-113">Присвойте проекту имя Library, а решению — имя Golden.</span><span class="sxs-lookup"><span data-stu-id="a8971-113">Name the project "Library" and the solution "Golden".</span></span> <span data-ttu-id="a8971-114">Оставьте флажок **Создать каталог для решения** установленным.</span><span class="sxs-lookup"><span data-stu-id="a8971-114">Leave **Create directory for solution** checked.</span></span> <span data-ttu-id="a8971-115">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a8971-115">Click **OK**.</span></span>

3. <span data-ttu-id="a8971-116">В обозревателе решений откройте контекстное меню узла **Зависимости** и выберите пункт **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="a8971-116">In Solution Explorer, open the context menu for the **Dependencies** node and choose **Manage NuGet Packages**.</span></span>

4. <span data-ttu-id="a8971-117">Выберите nuget.org в качестве **источника пакета** и перейдите на вкладку **Обзор**.</span><span class="sxs-lookup"><span data-stu-id="a8971-117">Choose "nuget.org" as the **Package source**, and choose the **Browse** tab.</span></span> <span data-ttu-id="a8971-118">Найдите файл **Newtonsoft.Json**.</span><span class="sxs-lookup"><span data-stu-id="a8971-118">Browse for **Newtonsoft.Json**.</span></span> <span data-ttu-id="a8971-119">Нажмите кнопку **Установить** и примите условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="a8971-119">Click **Install**, and accept the license agreement.</span></span> <span data-ttu-id="a8971-120">Пакет должен появиться в разделе **Зависимости/NuGet** и автоматически восстановиться.</span><span class="sxs-lookup"><span data-stu-id="a8971-120">The package should now appear under **Dependencies/NuGet** and be automatically restored.</span></span>

5. <span data-ttu-id="a8971-121">Переименуйте файл `Class1.cs` в `Thing.cs`.</span><span class="sxs-lookup"><span data-stu-id="a8971-121">Rename the `Class1.cs` file to `Thing.cs`.</span></span> <span data-ttu-id="a8971-122">Подтвердите переименование класса.</span><span class="sxs-lookup"><span data-stu-id="a8971-122">Accept the rename of the class.</span></span> <span data-ttu-id="a8971-123">Добавьте метод: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`</span><span class="sxs-lookup"><span data-stu-id="a8971-123">Add a method: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`</span></span>

7. <span data-ttu-id="a8971-124">В меню **Построение** выберите **Построить решение**.</span><span class="sxs-lookup"><span data-stu-id="a8971-124">On the **Build** menu, choose **Build Solution**.</span></span>

   <span data-ttu-id="a8971-125">Решение должно быть собрано без ошибок.</span><span class="sxs-lookup"><span data-stu-id="a8971-125">The solution should build without error.</span></span>

### <a name="writing-the-test-project"></a><span data-ttu-id="a8971-126">Написание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="a8971-126">Writing the test project</span></span>

1. <span data-ttu-id="a8971-127">В обозревателе решений в контекстном меню узла **Решение** выберите **Добавить**, **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="a8971-127">In Solution Explorer, open the context menu for the **Solution** node and choose **Add**, **New Project**.</span></span> <span data-ttu-id="a8971-128">В диалоговом окне **Новый проект** в разделе **Visual C#/.NET Core** выберите **Проект модульного теста (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="a8971-128">In the **New Project** dialog, under **Visual C# / .NET Core**, choose **Unit Test Project (.NET Core)**.</span></span> <span data-ttu-id="a8971-129">Назовите его TestLibrary и нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="a8971-129">Name it "TestLibrary" and click OK.</span></span> 

2. <span data-ttu-id="a8971-130">В проекте **TestLibrary** откройте контекстное меню узла **Зависимости** и выберите пункт **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="a8971-130">In the **TestLibrary** project, open the context menu for the **Dependencies** node and choose **Add Reference**.</span></span> <span data-ttu-id="a8971-131">Щелкните **Проекты**, затем проверьте проект библиотеки и нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="a8971-131">Click **Projects**, then check the Library project and click OK.</span></span> <span data-ttu-id="a8971-132">После этого в библиотеку будет добавлена ссылка из тестового проекта.</span><span class="sxs-lookup"><span data-stu-id="a8971-132">This adds a reference to your library from the test project.</span></span>

3. <span data-ttu-id="a8971-133">Переименуйте файл `UnitTest1.cs` в `LibraryTests.cs` и примите переименование класса.</span><span class="sxs-lookup"><span data-stu-id="a8971-133">Rename the `UnitTest1.cs` file to `LibraryTests.cs` and accept the class rename.</span></span> <span data-ttu-id="a8971-134">Добавьте `using Library;` в верхнюю часть файла и замените метод `TestMethod1` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="a8971-134">Add `using Library;` to the top of the file, and replace the `TestMethod1` method with the following code:</span></span>
    ```csharp
    [TestMethod]
    public void ThingGetsObjectValFromNumber()
    {
        Assert.AreEqual(42, new Thing().Get(42));
    }
    ```

   <span data-ttu-id="a8971-135">Теперь вы можете выполнить сборку решения.</span><span class="sxs-lookup"><span data-stu-id="a8971-135">You should now be able to build the solution.</span></span> 
   
4. <span data-ttu-id="a8971-136">В меню **Тестирование** выберите **Окна**, **Обозреватель тестов**, чтобы открыть окно обозревателя тестов в рабочей области.</span><span class="sxs-lookup"><span data-stu-id="a8971-136">On the **Test** menu, choose **Windows**, **Test Explorer** in order to get the test explorer window into your workspace.</span></span> <span data-ttu-id="a8971-137">Через несколько секунд тест `ThingGetsObjectValFromNumber` появится в обозревателе тестов.</span><span class="sxs-lookup"><span data-stu-id="a8971-137">After a few seconds, the `ThingGetsObjectValFromNumber` test should appear in the test explorer.</span></span> <span data-ttu-id="a8971-138">Выберите **Запустить все**.</span><span class="sxs-lookup"><span data-stu-id="a8971-138">Choose **Run All**.</span></span>
   
   <span data-ttu-id="a8971-139">Тест должен быть пройден успешно.</span><span class="sxs-lookup"><span data-stu-id="a8971-139">The test should pass.</span></span>

### <a name="writing-the-console-app"></a><span data-ttu-id="a8971-140">Написание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="a8971-140">Writing the console app</span></span>

1. <span data-ttu-id="a8971-141">В обозревателе решений откройте контекстное меню решения и добавьте новый проект **Консольное приложение (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="a8971-141">In Solution Explorer, open the context menu for the solution, and add a new **Console App (.NET Core)** project.</span></span> <span data-ttu-id="a8971-142">Назовите его "App".</span><span class="sxs-lookup"><span data-stu-id="a8971-142">Name it "App".</span></span>

2. <span data-ttu-id="a8971-143">В проекте **App** откройте контекстное меню узла **Зависимости** и выберите пункты **Добавить**, **Ссылка**.</span><span class="sxs-lookup"><span data-stu-id="a8971-143">In the **App** project, open the context menu for the **Dependencies** node and choose **Add**,  **Reference**.</span></span> 

3. <span data-ttu-id="a8971-144">В диалоговом окне **Диспетчер ссылок** установите флажок **Библиотека** в узле **Проекты**, **Решение**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a8971-144">In the **Reference Manager** dialog, check **Library** under the **Projects**, **Solution** node, and then click **OK**</span></span>

6. <span data-ttu-id="a8971-145">Откройте контекстное меню узла **App** и выберите пункт **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="a8971-145">Open the context menu for the **App** node and choose **Set as StartUp Project**.</span></span> <span data-ttu-id="a8971-146">Теперь при нажатии клавиши F5 или сочетания клавиш CTRL+F5 будет открываться консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="a8971-146">This ensures that hitting F5 or CTRL+F5 will start the console app.</span></span>

7. <span data-ttu-id="a8971-147">Откройте файл `Program.cs`, добавьте директиву `using Library;` в начало файла, а затем добавьте строку `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` в метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="a8971-147">Open the `Program.cs` file, add a `using Library;` directive to the top of the file, and then add `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` to the `Main` method.</span></span>

8. <span data-ttu-id="a8971-148">Установите точку останова после только что добавленной строки.</span><span class="sxs-lookup"><span data-stu-id="a8971-148">Set a breakpoint after the line that you just added.</span></span>

9. <span data-ttu-id="a8971-149">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="a8971-149">Press F5 to run the application..</span></span>

   <span data-ttu-id="a8971-150">Сборка приложения должна быть выполнена без ошибок, и должна быть достигнута точка останова.</span><span class="sxs-lookup"><span data-stu-id="a8971-150">The application should build without error, and should hit the breakpoint.</span></span> <span data-ttu-id="a8971-151">Вы также можете проверить, выдает ли приложение результат The answer is 42.</span><span class="sxs-lookup"><span data-stu-id="a8971-151">You should also be able to check that the application output "The answer is 42.".</span></span>

