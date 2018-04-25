---
title: Организация и тестирование проектов с использованием командной строки .NET Core
description: В этом учебнике объясняется, как упорядочить и протестировать проекты .NET Core из командной строки.
keywords: .NET, .NET Core, модульное тестирование, интерфейс командной строки .NET Core, xUnit
author: cartermp
ms.author: mairaw
ms.date: 05/16/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 52ff1be3-d92e-4477-9c84-8c1771e87ab5
ms.workload:
- dotnetcore
ms.openlocfilehash: c68b7cb7dac069093e2e849543c5b5c21b4ffe3a
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2018
---
# <a name="organizing-and-testing-projects-with-the-net-core-command-line"></a>Организация и тестирование проектов с использованием командной строки .NET Core

В этом руководстве мы продолжаем разрабатывать приложение, описанное в статье [Начало работы с .NET Core в Windows, Linux и Mac OS с помощью командной строки](using-with-xplat-cli.md), и переходим от простых консольных приложений к более сложным и хорошо организованным приложениям. В этом руководстве будет описано, как упорядочить код с помощью папок и расширить консольное приложение с помощью платформы тестирования [xUnit](https://xunit.github.io/).

## <a name="using-folders-to-organize-code"></a>Упорядочение кода с помощью папок

Если вы хотите добавить новые типы в консольное приложение, это можно сделать, добавив в приложение файлы, содержащие эти типы. Например, если добавить в проект файлы, содержащие типы `AccountInformation` и `MonthlyReportRecords`, это позволит получить плоскую и удобную для навигации структуру файлов проекта:

```
/MyProject
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

Однако этот подход можно применять только для относительно небольших проектов. Можете представить, что произойдет, если добавить в проект 20 типов? С таким количеством файлов в корневом каталоге проекта навигация по проекту и поддержка проекта будут представлять трудности.

Чтобы упорядочить проект, создайте новую папку для файлов типов и назовите ее *Models*. Поместите файлы типов в папку *Models*:

```
/MyProject
|__/Models
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__MyProject.csproj
|__Program.cs
```

Проекты, в которых файлы логически упорядочены в папки, легко поддерживать. Они также отличаются удобной навигацией. В следующем разделе мы создадим более сложный пример проекта с папками и модульным тестированием.

## <a name="organizing-and-testing-using-the-newtypes-pets-sample"></a>Упорядочение и тестирование проекта на основе примера проекта с новыми типами для животных

### <a name="building-the-sample"></a>Создание примера

Для выполнения следующих действий можно воспользоваться [примером проекта с новыми типами для животных](https://github.com/dotnet/samples/tree/master/core/console-apps/NewTypesMsBuild) или создать собственные файлы и папки. Типы логически организованы в структуру папок, которая позволяет добавлять дополнительные типы. Тесты также организованы в структуру папок, которая позволяет добавлять дополнительные тесты.

В этом примере используются два типа, `Dog` и `Cat`, которые реализуют общий интерфейс `IPet`. Цель проекта `NewTypes` — упорядочить типы, связанные с животными, в папку *Pets*. Если впоследствии добавляется другой набор типов *WildAnimals*, они помещаются в папку *NewTypes* вместе с папкой *Pets*. Папка *WildAnimals* может содержать типы для животных, которые не являются домашними, например `Squirrel` и `Rabbit`. При таком добавлении типов структура проекта всегда остается хорошо упорядоченной. 

Создайте следующую структуру папок, которая включает следующие файлы с указанным содержимым:

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

*IPet.cs*:

[!code-csharp[IPet interface](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/IPet.cs)]

*Dog.cs*:

[!code-csharp[Dog class](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/Dog.cs)]

*Cat.cs*:

[!code-csharp[Cat class](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Pets/Cat.cs)]

*Program.cs*:

[!code-csharp[Main](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/Program.cs)]

*NewTypes.csproj*:

[!code-xml[NewTypes csproj](../../../samples/core/console-apps/NewTypesMsBuild/src/NewTypes/NewTypes.csproj)]

Выполните следующие команды:

```console
dotnet run
```

Вы получите следующие выходные данные:

```console
Woof!
Meow!
```

Необязательное упражнение: добавьте в проект новый тип животных, например `Bird`. Сделайте так, чтобы метод `TalkToOwner` для птицы возвращал владельцу `Tweet!`. Снова запустите приложение. Выходные данные будут включать `Tweet!`

### <a name="testing-the-sample"></a>Тестирование примера

Проект `NewTypes` развернут, и вы упорядочили типы, связанные с животными, в отдельную папку. Теперь давайте создадим тестовый проект и напишем тесты с помощью платформы тестирования [xUnit](https://xunit.github.io/). Модульное тестирование позволяет автоматически проверять правильную работу типов домашних животных.

Создайте папку *test*, а внутри нее — папку *NewTypesTests*. В командной строке перейдите в каталог *NewTypesTests* и выполните команду `dotnet new xunit`. Эта команда создает два файла: *NewTypesTests.csproj* и *UnitTest1.cs*.

Сейчас в тестовом проекте нельзя проверять типы в `NewTypes`. Для этого необходимо добавить в проект `NewTypes` ссылку на проект. Чтобы добавить ссылку на проект, выполните команду [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../../src/NewTypes/NewTypes.csproj
```

Также можно добавить ссылку на проект вручную. Для этого добавьте узел `<ItemGroup>` в проект *NewTypesTests.csproj*:

```xml
<ItemGroup>
  <ProjectReference Include="../../src/NewTypes/NewTypes.csproj" />
</ItemGroup>
```

*NewTypesTests.csproj*:

[!code-xml[NewTypesTests csproj](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/NewTypesTests.csproj)]

Файл *NewTypesTests.csproj* содержит следующие элементы:

* Ссылка на пакет `Microsoft.NET.Test.Sdk`, инфраструктура тестирования .NET
* Ссылка на пакет `xunit`, платформа тестирования xUnit
* Ссылка на пакет `xunit.runner.visualstudio`, средство выполнения тестов
* Ссылка на проект `NewTypes`, код для тестирования

Переименуйте файл *UnitTest1.cs* в *PetTests.cs* и замените код в файле на следующий:

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

Необязательное упражнение: если ранее был добавлен тип `Bird`, который предоставляет владельцу `Tweet!`, добавьте метод теста в файл *PetTests.cs*, `BirdTalkToOwnerReturnsTweet`, который проверит правильность работы метода `TalkToOwner` для типа `Bird`.

> [!NOTE]
> Несмотря на то, что значения `expected` и `actual` должны быть равны, в начальных проверочных утверждениях с проверками `Assert.NotEqual` указывается, что они *не равны*. Всегда создавайте свои тесты таким образом, чтобы они завершались с ошибкой один раз, чтобы проверить логику тестов. Это важный шаг в методологии разработки через тестирование (TDD). После того как тест завершается с ошибкой, измените проверочные утверждения, чтобы тест завершился успешно.

Ниже показана полная структура проекта:

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

Запустите тест в папке *test/NewTypesTests*. Восстановите тестовый проект, выполнив команду [`dotnet restore`](../tools/dotnet-restore.md). Запустите тесты, выполнив команду [`dotnet test`](../tools/dotnet-test.md). Эта команда запускает средство запуска тестов, указанное в файле проекта.

 [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

 
Как и ожидалось, тест завершается с ошибкой, и в консоли отображаются следующие выходные данные:
 
```
Test run for C:\NewTypesMsBuild\test\NewTypesTests\bin\Debug\netcoreapp1.1\NewTypesTests.dll(.NETCoreApp,Version=v1.1)
Microsoft (R) Test Execution Command Line Tool Version 15.0.0.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:00.7271827]   Discovering: NewTypesTests
[xUnit.net 00:00:00.8258687]   Discovered:  NewTypesTests
[xUnit.net 00:00:00.8663545]   Starting:    NewTypesTests
[xUnit.net 00:00:01.0109236]     PetTests.CatTalkToOwnerReturnsMeow [FAIL]
[xUnit.net 00:00:01.0119107]       Assert.NotEqual() Failure
[xUnit.net 00:00:01.0120278]       Expected: Not "Meow!"
[xUnit.net 00:00:01.0120968]       Actual:   "Meow!"
[xUnit.net 00:00:01.0130500]       Stack Trace:
[xUnit.net 00:00:01.0141240]         C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs(22,0): at PetTests.CatTalkToOwnerReturnsMeow()
[xUnit.net 00:00:01.0272364]     PetTests.DogTalkToOwnerReturnsWoof [FAIL]
[xUnit.net 00:00:01.0273649]       Assert.NotEqual() Failure
[xUnit.net 00:00:01.0274166]       Expected: Not "Woof!"
[xUnit.net 00:00:01.0274690]       Actual:   "Woof!"
[xUnit.net 00:00:01.0275264]       Stack Trace:
[xUnit.net 00:00:01.0275960]         C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs(13,0): at PetTests.DogTalkToOwnerReturnsWoof()
[xUnit.net 00:00:01.0294509]   Finished:    NewTypesTests
Failed   PetTests.CatTalkToOwnerReturnsMeow
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Meow!"
Actual:   "Meow!"
Stack Trace:
   at PetTests.CatTalkToOwnerReturnsMeow() in C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 22
Failed   PetTests.DogTalkToOwnerReturnsWoof
Error Message:
 Assert.NotEqual() Failure
Expected: Not "Woof!"
Actual:   "Woof!"
Stack Trace:
   at PetTests.DogTalkToOwnerReturnsWoof() in C:\NewTypesMsBuild\test\NewTypesTests\PetTests.cs:line 13

Total tests: 2. Passed: 0. Failed: 2. Skipped: 0.
Test Run Failed.
Test execution time: 2.1371 Seconds
```

Измените проверочные утверждения в тестах с `Assert.NotEqual` на `Assert.Equal`:

[!code-csharp[PetTests class](../../../samples/core/console-apps/NewTypesMsBuild/test/NewTypesTests/PetTests.cs)]

Повторно запустите тесты, выполнив `dotnet test` команду, и получите следующие выходные данные:

```
Microsoft (R) Test Execution Command Line Tool Version 15.0.0.0
Copyright (c) Microsoft Corporation.  All rights reserved.

Starting test execution, please wait...
[xUnit.net 00:00:01.3882374]   Discovering: NewTypesTests
[xUnit.net 00:00:01.4767970]   Discovered:  NewTypesTests
[xUnit.net 00:00:01.5157667]   Starting:    NewTypesTests
[xUnit.net 00:00:01.6408870]   Finished:    NewTypesTests

Total tests: 2. Passed: 2. Failed: 0. Skipped: 0.
Test Run Successful.
Test execution time: 1.6634 Seconds
```

Тесты завершены успешно. Методы типов животных возвращают правильные значения при взаимодействии с владельцем.

Вы познакомились с тем, как упорядочить и тестировать проекты с помощью xUnit. Теперь вы можете приметь эти методы в собственных проектах. *Удачного программирования!*

