---
title: "Использование MSTest с .NET Core | Документы Майкрософт"
description: "Использование MSTest с .NET Core"
keywords: MSTest, .NET, .NET Core
author: ncarandini
ms.author: wiwagn
ms.date: 02/10/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: ed447641-3e85-4e50-b7ed-004630048a3e
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 4ffc7dd4e11820a3c50ca83847a7ab418bf2faf3
ms.lasthandoff: 03/07/2017

---

# <a name="unit-testing-with-mstest-and-net-core"></a>Модульное тестирование с использованием MSTest и .NET Core

## <a name="creating-the-projects"></a>Создание проектов

В разделе [Написание библиотек с помощью кроссплатформенных средств](../tutorials/libraries.md) приводятся сведения об организации исходного кода и тестов для решений, состоящих из нескольких проектов. В этой статье используются эти соглашения. Итоговая структура проекта будет похожа на следующую:

```
/unit-testing-using-mstest
|__/PrimeService
   |__Source Files
   |__PrimeService.csproj
|__/PrimeService.Tests
   |__Test Files
   |__PrimeService.csproj
```

### <a name="creating-the-source-project"></a>Создание исходного проекта

Откройте окно оболочки. Перейдите в каталог *unit-testing-using-mstest* и создайте каталог *PrimeService*.
Перейдите в каталог *PrimeService* и выполните команду `dotnet new classlib`, чтобы создать исходный проект.

Переименуйте *Class1.cs* в *PrimeService.cs*. Чтобы использовать разработку на основе тестирования (TDD), вы создадите сбойную реализацию класса `PrimeService`:

```cs
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

Вернитесь в каталог *unit-testing-using-mstest* и создайте каталог *PrimeServices.Tests*.
Перейдите в каталог *PrimeService.Tests* и создайте новый с помощью `dotnet new mstest`. При этом создается тестовый проект, который использует MStest в качестве библиотеки тестов. 

Созданный шаблон настроил средство запуска тестов в файле *PrimeServiceTests.csproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-preview-20170123-02" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.10-rc2" />
  <PackageReference Include="MSTest.TestFramework" Version="1.0.8-rc2" />
</ItemGroup>
```

Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда
`dotnet new` добавил пакет SDK MSTest, платформа тестирования MSTest и средство запуска MSTest. Вам нужно добавить пакет PrimeService в проект в качестве еще одной зависимости. Для этого можно использовать CLI `dotnet`:

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

Либо можно вручную изменить файл *PrimeService.Tests.csproj*.
Сразу после первого узла `<ItemGroup>` добавьте еще один узел `<ItemGroup>` со ссылкой на проект библиотеки:

```xml
  <ItemGroup>
    <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
  </ItemGroup>
```

Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService.Tests.csproj) на сайте GitHub.

Создав эту начальную структуру, вы можете написать первый тест.
Успешная проверка этого первого модульного теста означает, что все настроено и дальнейшее добавление компонентов и тестов должно происходить без проблем.

## <a name="creating-the-first-test"></a>Создание первого теста

Перед созданием библиотеки или тестов нужно запустить `dotnet restore` в обоих каталогах *PrimeService* и *PrimeService.Tests*. Эта команда восстанавливает все необходимые пакеты NuGet для каждого проекта.

Подход TDD предполагает создание теста, который завершается ошибкой, обеспечение его успешного выполнения и повтор этого процесса. Итак, создадим этот тест, завершающийся ошибкой. Удалите *UnitTest1.cs* из каталога *PrimeService.Tests* и создайте файл C# *PrimeService_IsPrimeShould.cs* со следующим содержимым.

```cs
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

Сохраните этот файл, а затем выполните команду `dotnet build` для сборки тестового проекта.
Если вы еще не выполнили сборку проекта `PrimeService`, система сборки обнаружит это и выполнит ее, так как это зависимость тестового проекта.

Теперь выполните команду `dotnet test`, чтобы запустить тесты из консоли.
Средство запуска тестов MSTest имеет точку входа в программу для выполнения тестов из консоли. `dotnet test` запускает средство запуска тестов и передает ему аргумент командной строки, который указывает на сборку, содержащую тесты.

Тест не будет пройден. Вы еще не создали реализацию.
Напишите простейший код, чтобы тест выполнялся успешно:

```cs
public bool IsPrime(int candidate) 
{
    if(candidate == 1) 
    { 
        return false;
    } 
    throw new NotImplementedException("Please create a test first");
} 
```

В каталоге *PrimeService.Tests* выполните `dotnet test` еще раз. Команда `dotnet test` сначала запускает сборку для проекта Prime.Services, а затем для проекта PrimeService.Tests. После сборки обоих проектов она запускает этот отдельный тест. Он выполняется.

## <a name="adding-more-features"></a>Добавление дополнительных возможностей

Теперь, когда этот тест проходит успешно, пора создать дополнительные тесты.
Есть еще ряд элементарных случаев с простыми числами: 0, -1. Можно добавить их в качестве тестов с помощью атрибутов `[TestMethod]`, но это скоро станет утомительным. Есть другие атрибуты MSTest, которые позволяют создавать наборы похожих тестов.  `DataTestMethod` представляет набор тестов, которые выполняют один и тот же код, но имеют разные входные аргументы.
С помощью атрибута `[DataRow]` можно указать значения для этих входных аргументов. 
 
 Вместо создания новых тестов используйте эти два атрибута, чтобы создать единый метод тестирования данных, который проверяет некоторые значения менее 2, то есть наименьшего простого числа:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs#Sample_TestCode "Первые тесты")]

Выполните команду `dotnet test`, и вы увидите, что два из этих тестов завершились ошибкой.
Чтобы они проходили успешно, измените код. Вам необходимо изменить предложение `if` в начале метода:

```cs
if(candidate < 2)
```

Теперь все эти тесты проходят успешно.

Вы можете продолжать итерации, добавляя тесты, алгоритмы и код в главной библиотеке. Вскоре вы получите [готовую версию тестов](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService.Tests/PrimeService_IsPrimeShould.cs) и [полную реализацию библиотеки](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-mstest/PrimeService/PrimeService.cs).

Вы создали небольшую библиотеку и набор модульных тестов для нее.
Вы структурировали решение, чтобы упростить добавление новых пакетов и тестов и получить возможность сосредоточиться на основной проблеме. Средства будут выполняться автоматически.
