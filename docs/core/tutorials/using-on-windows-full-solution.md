---
title: Создание полного решения .NET Core в Windows с помощью Visual Studio 2017
description: Сведения о создании полного решения .NET Core с помощью Visual Studio 2017 в Windows.
author: bleroy
ms.author: mairaw
ms.date: 11/16/2016
ms.openlocfilehash: 52b8781cdc29ac776123402c982353ef437ce74f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33214397"
---
# <a name="building-a-complete-net-core-solution-on-windows-using-visual-studio-2017"></a><span data-ttu-id="8725f-103">Создание полного решения .NET Core в Windows с помощью Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="8725f-103">Building a complete .NET Core solution on Windows, using Visual Studio 2017</span></span>

<span data-ttu-id="8725f-104">Visual Studio 2017 предоставляет полнофункциональную среду для разработки приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8725f-104">Visual Studio 2017 provides a full-featured development environment for developing .NET Core applications.</span></span> <span data-ttu-id="8725f-105">Процедуры в этом документе описывают шаги, необходимые для построения стандартного решения .NET Core, которое включает повторно используемые библиотеки, тестирование и использование сторонних библиотек.</span><span class="sxs-lookup"><span data-stu-id="8725f-105">The procedures in this document describe the steps necessary to build a typical .NET Core solution that includes reusable libraries, testing, and using third-party libraries.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="8725f-106">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="8725f-106">Prerequisites</span></span>

<span data-ttu-id="8725f-107">Чтобы обновить среду, выполните инструкции на [странице с описанием предварительных требований](../windows-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="8725f-107">Follow the instructions on [our prerequisites page](../windows-prerequisites.md) to update your environment.</span></span>

## <a name="a-solution-using-only-net-core-projects"></a><span data-ttu-id="8725f-108">Решение на основе только проектов .NET Core</span><span class="sxs-lookup"><span data-stu-id="8725f-108">A solution using only .NET Core projects</span></span>

### <a name="writing-the-library"></a><span data-ttu-id="8725f-109">Написание библиотеки</span><span class="sxs-lookup"><span data-stu-id="8725f-109">Writing the library</span></span>

1. <span data-ttu-id="8725f-110">В Visual Studio последовательно щелкните **Файл**, **Создать**, **Проект**.</span><span class="sxs-lookup"><span data-stu-id="8725f-110">In Visual Studio, choose **File**, **New**, **Project**.</span></span> <span data-ttu-id="8725f-111">В диалоговом окне **Новый проект** разверните узел **Visual C#**, выберите узел **.NET Standard**, а затем выберите шаблон **Библиотека классов (.NET Standard)**.</span><span class="sxs-lookup"><span data-stu-id="8725f-111">In the **New Project** dialog, expand the **Visual C#** node and choose the **.NET Standard** node, and then choose **Class Library (.NET Standard)**.</span></span> 

2. <span data-ttu-id="8725f-112">Присвойте проекту имя Library, а решению — имя Golden.</span><span class="sxs-lookup"><span data-stu-id="8725f-112">Name the project "Library" and the solution "Golden".</span></span> <span data-ttu-id="8725f-113">Оставьте флажок **Создать каталог для решения** установленным.</span><span class="sxs-lookup"><span data-stu-id="8725f-113">Leave **Create directory for solution** checked.</span></span> <span data-ttu-id="8725f-114">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8725f-114">Click **OK**.</span></span>

3. <span data-ttu-id="8725f-115">В обозревателе решений откройте контекстное меню узла **Зависимости** и выберите пункт **Управление пакетами NuGet**.</span><span class="sxs-lookup"><span data-stu-id="8725f-115">In Solution Explorer, open the context menu for the **Dependencies** node and choose **Manage NuGet Packages**.</span></span>

4. <span data-ttu-id="8725f-116">Выберите nuget.org в качестве **источника пакета** и перейдите на вкладку **Обзор**. Найдите файл **Newtonsoft.Json**.</span><span class="sxs-lookup"><span data-stu-id="8725f-116">Choose "nuget.org" as the **Package source**, and choose the **Browse** tab. Browse for **Newtonsoft.Json**.</span></span> <span data-ttu-id="8725f-117">Нажмите кнопку **Установить** и примите условия лицензионного соглашения.</span><span class="sxs-lookup"><span data-stu-id="8725f-117">Click **Install**, and accept the license agreement.</span></span> <span data-ttu-id="8725f-118">Пакет должен появиться в разделе **Зависимости/NuGet** и автоматически восстановиться.</span><span class="sxs-lookup"><span data-stu-id="8725f-118">The package should now appear under **Dependencies/NuGet** and be automatically restored.</span></span>

5. <span data-ttu-id="8725f-119">Переименуйте файл `Class1.cs` в `Thing.cs`.</span><span class="sxs-lookup"><span data-stu-id="8725f-119">Rename the `Class1.cs` file to `Thing.cs`.</span></span> <span data-ttu-id="8725f-120">Подтвердите переименование класса.</span><span class="sxs-lookup"><span data-stu-id="8725f-120">Accept the rename of the class.</span></span> <span data-ttu-id="8725f-121">Добавьте метод: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`</span><span class="sxs-lookup"><span data-stu-id="8725f-121">Add a method: `public int Get(int number) => Newtonsoft.Json.JsonConvert.DeserializeObject<int>($"{number}");`</span></span>

7. <span data-ttu-id="8725f-122">В меню **Построение** выберите **Построить решение**.</span><span class="sxs-lookup"><span data-stu-id="8725f-122">On the **Build** menu, choose **Build Solution**.</span></span>

   <span data-ttu-id="8725f-123">Решение должно быть собрано без ошибок.</span><span class="sxs-lookup"><span data-stu-id="8725f-123">The solution should build without error.</span></span>

### <a name="writing-the-test-project"></a><span data-ttu-id="8725f-124">Написание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="8725f-124">Writing the test project</span></span>

1. <span data-ttu-id="8725f-125">В обозревателе решений в контекстном меню узла **Решение** выберите **Добавить**, **Новый проект**.</span><span class="sxs-lookup"><span data-stu-id="8725f-125">In Solution Explorer, open the context menu for the **Solution** node and choose **Add**, **New Project**.</span></span> <span data-ttu-id="8725f-126">В диалоговом окне **Новый проект** в разделе **Visual C#/.NET Core** выберите **Проект модульного теста (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="8725f-126">In the **New Project** dialog, under **Visual C# / .NET Core**, choose **Unit Test Project (.NET Core)**.</span></span> <span data-ttu-id="8725f-127">Назовите его TestLibrary и нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="8725f-127">Name it "TestLibrary" and click OK.</span></span> 

2. <span data-ttu-id="8725f-128">В проекте **TestLibrary** откройте контекстное меню узла **Зависимости** и выберите пункт **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="8725f-128">In the **TestLibrary** project, open the context menu for the **Dependencies** node and choose **Add Reference**.</span></span> <span data-ttu-id="8725f-129">Щелкните **Проекты**, затем проверьте проект библиотеки и нажмите кнопку "ОК".</span><span class="sxs-lookup"><span data-stu-id="8725f-129">Click **Projects**, then check the Library project and click OK.</span></span> <span data-ttu-id="8725f-130">После этого в библиотеку будет добавлена ссылка из тестового проекта.</span><span class="sxs-lookup"><span data-stu-id="8725f-130">This adds a reference to your library from the test project.</span></span>

3. <span data-ttu-id="8725f-131">Переименуйте файл `UnitTest1.cs` в `LibraryTests.cs` и примите переименование класса.</span><span class="sxs-lookup"><span data-stu-id="8725f-131">Rename the `UnitTest1.cs` file to `LibraryTests.cs` and accept the class rename.</span></span> <span data-ttu-id="8725f-132">Добавьте `using Library;` в верхнюю часть файла и замените метод `TestMethod1` следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="8725f-132">Add `using Library;` to the top of the file, and replace the `TestMethod1` method with the following code:</span></span>
    ```csharp
    [TestMethod]
    public void ThingGetsObjectValFromNumber()
    {
        Assert.AreEqual(42, new Thing().Get(42));
    }
    ```

   <span data-ttu-id="8725f-133">Теперь вы можете выполнить сборку решения.</span><span class="sxs-lookup"><span data-stu-id="8725f-133">You should now be able to build the solution.</span></span> 
   
4. <span data-ttu-id="8725f-134">В меню **Тестирование** выберите **Окна**, **Обозреватель тестов**, чтобы открыть окно обозревателя тестов в рабочей области.</span><span class="sxs-lookup"><span data-stu-id="8725f-134">On the **Test** menu, choose **Windows**, **Test Explorer** in order to get the test explorer window into your workspace.</span></span> <span data-ttu-id="8725f-135">Через несколько секунд тест `ThingGetsObjectValFromNumber` появится в обозревателе тестов.</span><span class="sxs-lookup"><span data-stu-id="8725f-135">After a few seconds, the `ThingGetsObjectValFromNumber` test should appear in the test explorer.</span></span> <span data-ttu-id="8725f-136">Выберите **Запустить все**.</span><span class="sxs-lookup"><span data-stu-id="8725f-136">Choose **Run All**.</span></span>
   
   <span data-ttu-id="8725f-137">Тест должен быть пройден успешно.</span><span class="sxs-lookup"><span data-stu-id="8725f-137">The test should pass.</span></span>

### <a name="writing-the-console-app"></a><span data-ttu-id="8725f-138">Написание консольного приложения</span><span class="sxs-lookup"><span data-stu-id="8725f-138">Writing the console app</span></span>

1. <span data-ttu-id="8725f-139">В обозревателе решений откройте контекстное меню решения и добавьте новый проект **Консольное приложение (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="8725f-139">In Solution Explorer, open the context menu for the solution, and add a new **Console App (.NET Core)** project.</span></span> <span data-ttu-id="8725f-140">Назовите его "App".</span><span class="sxs-lookup"><span data-stu-id="8725f-140">Name it "App".</span></span>

2. <span data-ttu-id="8725f-141">В проекте **App** откройте контекстное меню узла **Зависимости** и выберите пункты **Добавить**, **Ссылка**.</span><span class="sxs-lookup"><span data-stu-id="8725f-141">In the **App** project, open the context menu for the **Dependencies** node and choose **Add**,  **Reference**.</span></span> 

3. <span data-ttu-id="8725f-142">В диалоговом окне **Диспетчер ссылок** установите флажок **Библиотека** в узле **Проекты**, **Решение**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8725f-142">In the **Reference Manager** dialog, check **Library** under the **Projects**, **Solution** node, and then click **OK**</span></span>

6. <span data-ttu-id="8725f-143">Откройте контекстное меню узла **App** и выберите пункт **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="8725f-143">Open the context menu for the **App** node and choose **Set as StartUp Project**.</span></span> <span data-ttu-id="8725f-144">Теперь при нажатии клавиши F5 или сочетания клавиш CTRL+F5 будет открываться консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="8725f-144">This ensures that hitting F5 or CTRL+F5 will start the console app.</span></span>

7. <span data-ttu-id="8725f-145">Откройте файл `Program.cs`, добавьте директиву `using Library;` в начало файла, а затем добавьте строку `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` в метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="8725f-145">Open the `Program.cs` file, add a `using Library;` directive to the top of the file, and then add `Console.WriteLine($"The answer is {new Thing().Get(42)}.");` to the `Main` method.</span></span>

8. <span data-ttu-id="8725f-146">Установите точку останова после только что добавленной строки.</span><span class="sxs-lookup"><span data-stu-id="8725f-146">Set a breakpoint after the line that you just added.</span></span>

9. <span data-ttu-id="8725f-147">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="8725f-147">Press F5 to run the application..</span></span>

   <span data-ttu-id="8725f-148">Сборка приложения должна быть выполнена без ошибок, и должна быть достигнута точка останова.</span><span class="sxs-lookup"><span data-stu-id="8725f-148">The application should build without error, and should hit the breakpoint.</span></span> <span data-ttu-id="8725f-149">Вы также можете проверить, выдает ли приложение результат The answer is 42.</span><span class="sxs-lookup"><span data-stu-id="8725f-149">You should also be able to check that the application output "The answer is 42.".</span></span>
