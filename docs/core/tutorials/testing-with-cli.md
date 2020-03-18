---
title: Организация и тестирование проектов с помощью .NET Core CLI
description: В этом учебнике объясняется, как упорядочить и протестировать проекты .NET Core из командной строки.
author: cartermp
ms.date: 09/10/2018
ms.openlocfilehash: 0d61e0fc004cfcb6d78c49475c7b7f0f523aad2c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "78239915"
---
# <a name="organizing-and-testing-projects-with-the-net-core-cli"></a><span data-ttu-id="d30bc-103">Организация и тестирование проектов с помощью .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="d30bc-103">Organizing and testing projects with the .NET Core CLI</span></span>

<span data-ttu-id="d30bc-104">В этом руководстве мы продолжаем разрабатывать приложение, описанное в статье [Начало работы с .NET Core в Windows, Linux и Mac OS с помощью командной строки](cli-create-console-app.md), и переходим от простых консольных приложений к более сложным и структурированным приложениям.</span><span class="sxs-lookup"><span data-stu-id="d30bc-104">This tutorial follows [Get started with .NET Core on Windows/Linux/macOS using the command line](cli-create-console-app.md), taking you beyond the creation of a simple console app to develop advanced and well-organized applications.</span></span> <span data-ttu-id="d30bc-105">В этом руководстве будет описано, как упорядочить код с помощью папок и расширить консольное приложение с помощью платформы тестирования [xUnit](https://xunit.github.io/).</span><span class="sxs-lookup"><span data-stu-id="d30bc-105">After showing you how to use folders to organize your code, this tutorial shows you how to extend a console application with the [xUnit](https://xunit.github.io/) testing framework.</span></span>

## <a name="using-folders-to-organize-code"></a><span data-ttu-id="d30bc-106">Упорядочение кода с помощью папок</span><span class="sxs-lookup"><span data-stu-id="d30bc-106">Using folders to organize code</span></span>

<span data-ttu-id="d30bc-107">Если вы хотите добавить новые типы в консольное приложение, это можно сделать, добавив в приложение файлы, содержащие эти типы.</span><span class="sxs-lookup"><span data-stu-id="d30bc-107">If you want to introduce new types into a console app, you can do so by adding files containing the types to the app.</span></span> <span data-ttu-id="d30bc-108">Например, если добавить в проект файлы, содержащие типы `AccountInformation` и `MonthlyReportRecords`, это позволит получить плоскую и удобную для навигации структуру файлов проекта:</span><span class="sxs-lookup"><span data-stu-id="d30bc-108">For example if you add files containing `AccountInformation` and `MonthlyReportRecords` types to your project, the project file structure is flat and easy to navigate:</span></span>

```
/MyProject
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

<span data-ttu-id="d30bc-109">Однако этот подход можно применять только для относительно небольших проектов.</span><span class="sxs-lookup"><span data-stu-id="d30bc-109">However, this only works well when the size of your project is relatively small.</span></span> <span data-ttu-id="d30bc-110">Можете представить, что произойдет, если добавить в проект 20 типов?</span><span class="sxs-lookup"><span data-stu-id="d30bc-110">Can you imagine what will happen if you add 20 types to the project?</span></span> <span data-ttu-id="d30bc-111">С таким количеством файлов в корневом каталоге проекта навигация по проекту и поддержка проекта будут представлять трудности.</span><span class="sxs-lookup"><span data-stu-id="d30bc-111">The project definitely wouldn't be easy to navigate and maintain with that many files littering the project's root directory.</span></span>

<span data-ttu-id="d30bc-112">Чтобы упорядочить проект, создайте новую папку для файлов типов и назовите ее *Models*.</span><span class="sxs-lookup"><span data-stu-id="d30bc-112">To organize the project, create a new folder and name it *Models* to hold the type files.</span></span> <span data-ttu-id="d30bc-113">Поместите файлы типов в папку *Models*:</span><span class="sxs-lookup"><span data-stu-id="d30bc-113">Place the type files into the *Models* folder:</span></span>

```
/MyProject
|__/Models
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

<span data-ttu-id="d30bc-114">Проекты, в которых файлы логически упорядочены в папки, легко поддерживать. Они также отличаются удобной навигацией.</span><span class="sxs-lookup"><span data-stu-id="d30bc-114">Projects that logically group files into folders are easy to navigate and maintain.</span></span> <span data-ttu-id="d30bc-115">В следующем разделе мы создадим более сложный пример проекта с папками и модульным тестированием.</span><span class="sxs-lookup"><span data-stu-id="d30bc-115">In the next section, you create a more complex sample with folders and unit testing.</span></span>

## <a name="organizing-and-testing-using-the-newtypes-pets-sample"></a><span data-ttu-id="d30bc-116">Упорядочение и тестирование проекта на основе примера проекта с новыми типами для животных</span><span class="sxs-lookup"><span data-stu-id="d30bc-116">Organizing and testing using the NewTypes Pets Sample</span></span>

### <a name="building-the-sample"></a><span data-ttu-id="d30bc-117">Создание примера</span><span class="sxs-lookup"><span data-stu-id="d30bc-117">Building the sample</span></span>

<span data-ttu-id="d30bc-118">Для выполнения следующих действий можно воспользоваться [примером проекта с новыми типами для животных](https://github.com/dotnet/samples/tree/master/core/console-apps/NewTypesMsBuild) или создать собственные файлы и папки.</span><span class="sxs-lookup"><span data-stu-id="d30bc-118">For the following steps, you can either follow along using the [NewTypes Pets Sample](https://github.com/dotnet/samples/tree/master/core/console-apps/NewTypesMsBuild) or create your own files and folders.</span></span> <span data-ttu-id="d30bc-119">Типы логически организованы в структуру папок, которая позволяет добавлять дополнительные типы. Тесты также организованы в структуру папок, которая позволяет добавлять дополнительные тесты.</span><span class="sxs-lookup"><span data-stu-id="d30bc-119">The types are logically organized into a folder structure that permits the addition of more types later, and tests are also logically placed in folders permitting the addition of more tests later.</span></span>

<span data-ttu-id="d30bc-120">В этом примере используются два типа, `Dog` и `Cat`, которые реализуют общий интерфейс `IPet`.</span><span class="sxs-lookup"><span data-stu-id="d30bc-120">The sample contains two types, `Dog` and `Cat`, and has them implement a common interface, `IPet`.</span></span> <span data-ttu-id="d30bc-121">Цель проекта `NewTypes` — упорядочить типы, связанные с животными, в папку *Pets*.</span><span class="sxs-lookup"><span data-stu-id="d30bc-121">For the `NewTypes` project, your goal is to organize the pet-related types into a *Pets* folder.</span></span> <span data-ttu-id="d30bc-122">Если впоследствии добавляется другой набор типов *WildAnimals*, они помещаются в папку *NewTypes* вместе с папкой *Pets*.</span><span class="sxs-lookup"><span data-stu-id="d30bc-122">If another set of types is added later, *WildAnimals* for example, they're placed in the *NewTypes* folder alongside the *Pets* folder.</span></span> <span data-ttu-id="d30bc-123">Папка *WildAnimals* может содержать типы для животных, которые не являются домашними, например `Squirrel` и `Rabbit`.</span><span class="sxs-lookup"><span data-stu-id="d30bc-123">The *WildAnimals* folder may contain types for animals that aren't pets, such as `Squirrel` and `Rabbit` types.</span></span> <span data-ttu-id="d30bc-124">При таком добавлении типов структура проекта всегда остается хорошо упорядоченной.</span><span class="sxs-lookup"><span data-stu-id="d30bc-124">In this way as types are added, the project remains well organized.</span></span>

<span data-ttu-id="d30bc-125">Создайте следующую структуру папок, которая включает следующие файлы с указанным содержимым:</span><span class="sxs-lookup"><span data-stu-id="d30bc-125">Create the following folder structure with file content indicated:</span></span>

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
```

<span data-ttu-id="d30bc-126">*IPet.cs*:</span><span class="sxs-lookup"><span data-stu-id="d30bc-126">*IPet.cs*:</span></span>

[!code-csharp[IPet interface](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/Pets/IPet.cs)]

<span data-ttu-id="d30bc-127">*Dog.cs*:</span><span class="sxs-lookup"><span data-stu-id="d30bc-127">*Dog.cs*:</span></span>

[!code-csharp[Dog class](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/Pets/Dog.cs)]

<span data-ttu-id="d30bc-128">*Cat.cs*:</span><span class="sxs-lookup"><span data-stu-id="d30bc-128">*Cat.cs*:</span></span>

[!code-csharp[Cat class](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/Pets/Cat.cs)]

<span data-ttu-id="d30bc-129">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="d30bc-129">*Program.cs*:</span></span>

[!code-csharp[Main](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/Program.cs)]

<span data-ttu-id="d30bc-130">*NewTypes.csproj*:</span><span class="sxs-lookup"><span data-stu-id="d30bc-130">*NewTypes.csproj*:</span></span>

[!code-xml[NewTypes csproj](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/src/NewTypes/NewTypes.csproj)]

<span data-ttu-id="d30bc-131">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d30bc-131">Execute the following command:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="d30bc-132">Вы получите следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="d30bc-132">Obtain the following output:</span></span>

```console
Woof!
Meow!
```

<span data-ttu-id="d30bc-133">Необязательное упражнение: добавьте в проект новый тип животных, например `Bird`.</span><span class="sxs-lookup"><span data-stu-id="d30bc-133">Optional exercise: You can add a new pet type, such as a `Bird`, by extending this project.</span></span> <span data-ttu-id="d30bc-134">Сделайте так, чтобы метод `TalkToOwner` для птицы возвращал владельцу `Tweet!`.</span><span class="sxs-lookup"><span data-stu-id="d30bc-134">Make the bird's `TalkToOwner` method give a `Tweet!` to the owner.</span></span> <span data-ttu-id="d30bc-135">Снова запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="d30bc-135">Run the app again.</span></span> <span data-ttu-id="d30bc-136">Выходные данные будут включать `Tweet!`</span><span class="sxs-lookup"><span data-stu-id="d30bc-136">The output will include `Tweet!`</span></span>

### <a name="testing-the-sample"></a><span data-ttu-id="d30bc-137">Тестирование примера</span><span class="sxs-lookup"><span data-stu-id="d30bc-137">Testing the sample</span></span>

<span data-ttu-id="d30bc-138">Проект `NewTypes` развернут, и вы упорядочили типы, связанные с животными, в отдельную папку.</span><span class="sxs-lookup"><span data-stu-id="d30bc-138">The `NewTypes` project is in place, and you've organized it by keeping the pets-related types in a folder.</span></span> <span data-ttu-id="d30bc-139">Теперь давайте создадим тестовый проект и напишем тесты с помощью платформы тестирования [xUnit](https://xunit.github.io/).</span><span class="sxs-lookup"><span data-stu-id="d30bc-139">Next, create your test project and start writing tests with the [xUnit](https://xunit.github.io/) test framework.</span></span> <span data-ttu-id="d30bc-140">Модульное тестирование позволяет автоматически проверять правильную работу типов домашних животных.</span><span class="sxs-lookup"><span data-stu-id="d30bc-140">Unit testing allows you to automatically check the behavior of your pet types to confirm that they're operating properly.</span></span>

<span data-ttu-id="d30bc-141">Вернитесь в папку *src*, создайте папку *test*, а внутри нее — папку *NewTypesTests*.</span><span class="sxs-lookup"><span data-stu-id="d30bc-141">Navigate back to the *src* folder and create a *test* folder with a *NewTypesTests* folder within it.</span></span> <span data-ttu-id="d30bc-142">В командной строке перейдите в каталог *NewTypesTests* и выполните команду `dotnet new xunit`.</span><span class="sxs-lookup"><span data-stu-id="d30bc-142">At a command prompt from the *NewTypesTests* folder, execute `dotnet new xunit`.</span></span> <span data-ttu-id="d30bc-143">Эта команда создает два файла: *NewTypesTests.csproj* и *UnitTest1.cs*.</span><span class="sxs-lookup"><span data-stu-id="d30bc-143">This produces two files: *NewTypesTests.csproj* and *UnitTest1.cs*.</span></span>

<span data-ttu-id="d30bc-144">Сейчас в тестовом проекте нельзя проверять типы в `NewTypes`. Для этого необходимо добавить в проект `NewTypes` ссылку на проект.</span><span class="sxs-lookup"><span data-stu-id="d30bc-144">The test project cannot currently test the types in `NewTypes` and requires a project reference to the `NewTypes` project.</span></span> <span data-ttu-id="d30bc-145">Чтобы добавить ссылку на проект, выполните команду [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="d30bc-145">To add a project reference, use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add reference ../../src/NewTypes/NewTypes.csproj
```

<span data-ttu-id="d30bc-146">Также можно добавить ссылку на проект вручную. Для этого добавьте узел `<ItemGroup>` в файл *NewTypesTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="d30bc-146">Or, you also have the option of manually adding the project reference by adding an `<ItemGroup>` node to the *NewTypesTests.csproj* file:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="../../src/NewTypes/NewTypes.csproj" />
</ItemGroup>
```

<span data-ttu-id="d30bc-147">*NewTypesTests.csproj*:</span><span class="sxs-lookup"><span data-stu-id="d30bc-147">*NewTypesTests.csproj*:</span></span>

[!code-xml[NewTypesTests csproj](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/test/NewTypesTests/NewTypesTests.csproj)]

<span data-ttu-id="d30bc-148">Файл *NewTypesTests.csproj* содержит следующие элементы:</span><span class="sxs-lookup"><span data-stu-id="d30bc-148">The *NewTypesTests.csproj* file contains the following:</span></span>

* <span data-ttu-id="d30bc-149">Ссылка на пакет `Microsoft.NET.Test.Sdk`, инфраструктура тестирования .NET</span><span class="sxs-lookup"><span data-stu-id="d30bc-149">Package reference to `Microsoft.NET.Test.Sdk`, the .NET testing infrastructure</span></span>
* <span data-ttu-id="d30bc-150">Ссылка на пакет `xunit`, платформа тестирования xUnit</span><span class="sxs-lookup"><span data-stu-id="d30bc-150">Package reference to `xunit`, the xUnit testing framework</span></span>
* <span data-ttu-id="d30bc-151">Ссылка на пакет `xunit.runner.visualstudio`, средство выполнения тестов</span><span class="sxs-lookup"><span data-stu-id="d30bc-151">Package reference to `xunit.runner.visualstudio`, the test runner</span></span>
* <span data-ttu-id="d30bc-152">Ссылка на проект `NewTypes`, код для тестирования</span><span class="sxs-lookup"><span data-stu-id="d30bc-152">Project reference to `NewTypes`, the code to test</span></span>

<span data-ttu-id="d30bc-153">Переименуйте файл *UnitTest1.cs* в *PetTests.cs* и замените код в файле на следующий:</span><span class="sxs-lookup"><span data-stu-id="d30bc-153">Change the name of *UnitTest1.cs* to *PetTests.cs* and replace the code in the file with the following:</span></span>

```csharp
using System;
using Xunit;
using Pets;

public class PetTests
{
    [Fact]
    public void DogTalkToOwnerReturnsWoof()
    {
        string expected = "Woof!";
        string actual = new Dog().TalkToOwner();

        Assert.NotEqual(expected, actual);
    }

    [Fact]
    public void CatTalkToOwnerReturnsMeow()
    {
        string expected = "Meow!";
        string actual = new Cat().TalkToOwner();

        Assert.NotEqual(expected, actual);
    }
}
```

<span data-ttu-id="d30bc-154">Необязательное упражнение: если ранее был добавлен тип `Bird`, который предоставляет владельцу `Tweet!`, добавьте метод теста в файл *PetTests.cs*, `BirdTalkToOwnerReturnsTweet`, который проверит правильность работы метода `TalkToOwner` для типа `Bird`.</span><span class="sxs-lookup"><span data-stu-id="d30bc-154">Optional exercise: If you added a `Bird` type earlier that yields a `Tweet!` to the owner, add a test method to the *PetTests.cs* file, `BirdTalkToOwnerReturnsTweet`, to check that the `TalkToOwner` method works correctly for the `Bird` type.</span></span>

> [!NOTE]
> <span data-ttu-id="d30bc-155">Несмотря на то, что значения `expected` и `actual` должны быть равны, в начальных проверочных утверждениях с проверкой `Assert.NotEqual` указывается, что они *не равны*.</span><span class="sxs-lookup"><span data-stu-id="d30bc-155">Although you expect that the `expected` and `actual` values are equal, an initial assertion with the `Assert.NotEqual` check specifies that these values are *not equal*.</span></span> <span data-ttu-id="d30bc-156">Всегда создавайте тест таким образом, чтобы он завершался с ошибкой, чтобы проверить логику теста.</span><span class="sxs-lookup"><span data-stu-id="d30bc-156">Always initially create a test to fail in order to check the logic of the test.</span></span> <span data-ttu-id="d30bc-157">Убедившись, что тест не пройден, измените утверждение так, чтобы тест был пройден.</span><span class="sxs-lookup"><span data-stu-id="d30bc-157">After you confirm that the test fails, adjust the assertion to allow the test to pass.</span></span>

<span data-ttu-id="d30bc-158">Ниже показана полная структура проекта:</span><span class="sxs-lookup"><span data-stu-id="d30bc-158">The following shows the complete project structure:</span></span>

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
|__/test
   |__NewTypesTests
      |__PetTests.cs
      |__NewTypesTests.csproj
```

<span data-ttu-id="d30bc-159">Запустите тест в папке *test/NewTypesTests*.</span><span class="sxs-lookup"><span data-stu-id="d30bc-159">Start in the *test/NewTypesTests* directory.</span></span> <span data-ttu-id="d30bc-160">Восстановите тестовый проект, выполнив команду [`dotnet restore`](../tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="d30bc-160">Restore the test project with the [`dotnet restore`](../tools/dotnet-restore.md) command.</span></span> <span data-ttu-id="d30bc-161">Запустите тесты, выполнив команду [`dotnet test`](../tools/dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="d30bc-161">Run the tests with the [`dotnet test`](../tools/dotnet-test.md) command.</span></span> <span data-ttu-id="d30bc-162">Эта команда запускает средство запуска тестов, указанное в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="d30bc-162">This command starts the test runner specified in the project file.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="d30bc-163">Как и ожидалось, тест завершается с ошибкой, и в консоли отображаются следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="d30bc-163">As expected, testing fails, and the console displays the following output:</span></span>

```output
Test run for c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\bin\Debug\netcoreapp2.1\NewTypesTests.dll(.NETCoreApp,Version=v2.1)
Microsoft (R) Test Execution Command Line Tool Version 15.8.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.77]     PetTests.DogTalkToOwnerReturnsWoof [FAIL]
[xUnit.net 00:00:00.78]     PetTests.CatTalkToOwnerReturnsMeow [FAIL]
Failed   PetTests.DogTalkToOwnerReturnsWoof
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Woof!"
Actual:   "Woof!"
Stack Trace:
   at PetTests.DogTalkToOwnerReturnsWoof() in c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 13
Failed   PetTests.CatTalkToOwnerReturnsMeow
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Meow!"
Actual:   "Meow!"
Stack Trace:
   at PetTests.CatTalkToOwnerReturnsMeow() in c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 22

Total tests: 2. Passed: 0. Failed: 2. Skipped: 0.
Test Run Failed.
Test execution time: 1.7000 Seconds
```

<span data-ttu-id="d30bc-164">Измените проверочные утверждения в тестах с `Assert.NotEqual` на `Assert.Equal`:</span><span class="sxs-lookup"><span data-stu-id="d30bc-164">Change the assertions of your tests from `Assert.NotEqual` to `Assert.Equal`:</span></span>

[!code-csharp[PetTests class](../../../samples/snippets/core/tutorials/testing-with-cli/csharp/test/NewTypesTests/PetTests.cs)]

<span data-ttu-id="d30bc-165">Повторно запустите тесты, выполнив `dotnet test` команду, и получите следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="d30bc-165">Re-run the tests with the `dotnet test` command and obtain the following output:</span></span>

```output
Test run for c:\Users\ronpet\repos\samples\core\console-apps\NewTypesMsBuild\test\NewTypesTests\bin\Debug\netcoreapp2.1\NewTypesTests.dll(.NETCoreApp,Version=v2.1)
Microsoft (R) Test Execution Command Line Tool Version 15.8.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...

Total tests: 2. Passed: 2. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.6029 Seconds
```

<span data-ttu-id="d30bc-166">Тесты завершены успешно.</span><span class="sxs-lookup"><span data-stu-id="d30bc-166">Testing passes.</span></span> <span data-ttu-id="d30bc-167">Методы типов животных возвращают правильные значения при взаимодействии с владельцем.</span><span class="sxs-lookup"><span data-stu-id="d30bc-167">The pet types' methods return the correct values when talking to the owner.</span></span>

<span data-ttu-id="d30bc-168">Вы познакомились с тем, как упорядочить и тестировать проекты с помощью xUnit.</span><span class="sxs-lookup"><span data-stu-id="d30bc-168">You've learned techniques for organizing and testing projects using xUnit.</span></span> <span data-ttu-id="d30bc-169">Теперь вы можете приметь эти методы в собственных проектах.</span><span class="sxs-lookup"><span data-stu-id="d30bc-169">Go forward with these techniques applying them in your own projects.</span></span> <span data-ttu-id="d30bc-170">*Удачного программирования!*</span><span class="sxs-lookup"><span data-stu-id="d30bc-170">*Happy coding!*</span></span>
