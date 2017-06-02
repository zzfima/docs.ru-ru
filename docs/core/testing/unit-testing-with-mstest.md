---
title: "Модульное тестирование с использованием MSTest и .NET Core | Документы Майкрософт"
description: "Использование MSTest с .NET Core"
keywords: MSTest, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 03/21/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 5c6382ee0de3cba950b4585b05f10b4682f9a797
ms.contentlocale: ru-ru
ms.lasthandoff: 05/10/2017

---

# <a name="unit-testing-with-mstest-and-net-core"></a>Модульное тестирование с использованием MSTest и .NET Core

Этот учебник описывает пошаговую процедуру по созданию примера решения для изучения концепций модульного тестирования. Если при изучении учебника вы предпочитаете использовать готовое решение, [просмотрите или скачайте пример кода](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/) перед началом работы. Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

### <a name="creating-the-source-project"></a>Создание исходного проекта

Откройте окно оболочки. Создайте каталог с именем *unit-testing-using-dotnet-test* для хранения решения. Внутри него создайте каталог *PrimeService*. Актуальная структура каталогов приведена ниже:

```
/unit-testing-using-mstest
    /PrimeService
```

Перейдите в каталог *PrimeService* и выполните команду [`dotnet new classlib`](../tools/dotnet-new.md), чтобы создать исходный проект. Переименуйте *Class1.cs* в *PrimeService.cs*. Чтобы использовать разработку на основе тестирования (TDD), вы создадите сбойную реализацию класса `PrimeService`:

```csharp
using System;

namespace Prime.Services
{
    public class PrimeService
    {
        public bool IsPrime(int candidate) 
        {
            throw new NotImplementedException("Please create a test first");
        } 
    }
}
```

### <a name="creating-the-test-project"></a>Создание тестового проекта

Вернитесь в каталог *unit-testing-using-mstest* и создайте каталог *PrimeService.Tests*. Соответствующая структура каталогов приведена ниже:

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

Перейдите в каталог *PrimeService.Tests* и создайте проект с помощью [`dotnet new mstest`](../tools/dotnet-new.md). При этом создается тестовый проект, который использует MStest в качестве библиотеки тестов. Созданный шаблон настраивает средство запуска тестов в файле *PrimeServiceTests.csproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.11" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.11" />
</ItemGroup>
```

Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда Команда `dotnet new` в предыдущем шаге добавила пакет SDK MSTest, платформу тестирования MSTest и средство запуска MSTest. Теперь добавьте в проект библиотеку классов `PrimeService` в качестве еще одной зависимости. Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

Можно также вручную изменить файл *PrimeService.Tests.csproj*. Сразу после первого узла `<ItemGroup>` добавьте еще один узел `<ItemGroup>` со ссылкой на проект библиотеки:

```xml
<ItemGroup>
  <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
</ItemGroup>
```

Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) на сайте GitHub.

Ниже показан окончательный макет решения:

```
/unit-testing-using-mstest
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        PrimeService
        PrimeServiceTests.csproj
```

## <a name="creating-the-first-test"></a>Создание первого теста

Перед созданием библиотеки или тестов запустите [`dotnet restore`](../tools/dotnet-restore.md) в каталоге *PrimeService.Tests*. Эта команда восстанавливает все необходимые пакеты NuGet для каждого проекта.

Подход TDD предполагает создание теста, который завершается ошибкой, обеспечение его успешного выполнения и повтор этого процесса. Удалите *UnitTest1.cs* из каталога *PrimeService.Tests* и создайте файл C# *PrimeService_IsPrimeShould.cs* со следующим содержимым:

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    [TestClass]
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [TestMethod]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.IsFalse(result, $"1 should not be prime");
        }
    }
}
```

Атрибут `[TestClass]` обозначает класс, содержащий модульные тесты. Атрибут `[TestMethod]` означает, что метод используется как отдельный тест. 

Сохраните этот файл и выполните [`dotnet test`](../tools/dotnet-test.md), чтобы создать тесты и библиотеку классов, а затем запустите тесты. Средство запуска тестов MSTest содержит точку входа в программу для выполнения тестов. `dotnet test` запускает средство запуска тестов и передает ему аргумент командной строки, который указывает на сборку, содержащую тесты.

Тест не будет пройден. Вы еще не создали реализацию. Напишите простейший код в классе `PrimeService`, чтобы тест выполнялся успешно:

```csharp
public bool IsPrime(int candidate) 
{
    if (candidate == 1) 
    { 
        return false;
    } 
    throw new NotImplementedException("Please create a test first");
} 
```

В каталоге *PrimeService.Tests* выполните `dotnet test` еще раз. Команда `dotnet test` запускает сборку для проекта `PrimeService` и затем для проекта `PrimeService.Tests`. После сборки обоих проектов она запускает этот отдельный тест. Он выполняется.

## <a name="adding-more-features"></a>Добавление дополнительных возможностей

Теперь, когда тест проходит успешно, пора создать дополнительные тесты. Есть еще ряд элементарных случаев с простыми числами: 0, -1. Можно добавить их в качестве тестов с помощью атрибута `[TestMethod]`, но это скоро станет утомительным. Есть другие атрибуты MSTest, которые позволяют создавать наборы похожих тестов.  Атрибут `[DataTestMethod]` представляет набор тестов, которые выполняют один и тот же код, но имеют разные входные аргументы. С помощью атрибута `[DataRow]` можно указать значения для этих входных аргументов. 
 
Вместо создания тестов используйте эти два атрибута, чтобы создать единый метод тестирования данных, который проверяет несколько значений меньше 2, то есть наименьшего простого числа:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Выполните команду `dotnet test`, и два из этих тестов завершаются ошибкой. Для успешного выполнения всех тестов нужно изменить предложение `if` в начале метода:

```csharp
if (candidate < 2)
```

Продолжайте итерации, добавляя тесты, алгоритмы и код в главной библиотеке. В результате вы получите [готовую версию тестов](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) и [полную реализацию библиотеки](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).

Вы создали небольшую библиотеку и набор модульных тестов для нее. Вы структурировали решение, чтобы упростить добавление новых пакетов и тестов, и теперь можете посвятить больше времени и сил решению основных задач для приложения.

