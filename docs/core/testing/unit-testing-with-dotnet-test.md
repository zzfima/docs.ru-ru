---
title: Модульное тестирование кода C# в .NET Core с использованием dotnet test и xUnit
description: Сведения о концепциях модульного тестирования в C# и .NET Core в рамках пошаговой процедуры по созданию примера решения с помощью команды dotnet test и xUnit.
author: ardalis
ms.author: wiwagn
ms.date: 11/29/2017
ms.custom: seodec18
ms.openlocfilehash: af2ae5e1b0f9e6146975c6838cca8b22837bb012
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168992"
---
# <a name="unit-testing-c-in-net-core-using-dotnet-test-and-xunit"></a>Модульное тестирование C# в .NET Core с использованием dotnet test и xUnit

Этот учебник описывает пошаговую процедуру по созданию примера решения для изучения концепций модульного тестирования. Если при изучении учебника вы предпочитаете использовать готовое решение, [просмотрите или скачайте пример кода](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-using-dotnet-test/) перед началом работы. Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="creating-the-source-project"></a>Создание исходного проекта

Откройте окно оболочки. Создайте каталог с именем *unit-testing-using-dotnet-test* для хранения решения.
В этом каталоге выполните команду выполните команду [`dotnet new sln`](../tools/dotnet-new.md), чтобы создать решение. С помощью решения упрощается управление библиотекой классов и проектом модульного теста.
В каталоге решения создайте каталог *PrimeService*. Актуальная структура каталогов и файлов должны иметь следующий вид:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
```

Перейдите в каталог *PrimeService* и выполните команду [`dotnet new classlib`](../tools/dotnet-new.md), чтобы создать исходный проект. Переименуйте *Class1.cs* в *PrimeService.cs*. Чтобы использовать разработку на основе тестирования (TDD), сначала требуется создать сбойную реализацию класса `PrimeService`:

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

Вернитесь в каталог *unit-testing-using-dotnet-test*.

Чтобы добавить проект библиотеки классов в решение, выполните команду [dotnet sln](../tools/dotnet-sln.md):

```
dotnet sln add .\PrimeService\PrimeService.csproj
```

## <a name="creating-the-test-project"></a>Создание тестового проекта

Затем создайте каталог *PrimeService.Tests*. Ниже представлена структура каталогов:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
```

Перейдите в каталог *PrimeService.Tests* и создайте проект с помощью [`dotnet new xunit`](../tools/dotnet-new.md). Эта команда создает тестовый проект, использующий xUnit в качестве библиотеки тестов. Созданный шаблон настраивает средство запуска тестов в файле *PrimeServiceTests.csproj*, как показано в следующем коде:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда В предыдущем шаге `dotnet new` добавила пакет xUnit и средство запуска xUnit. Теперь добавьте в проект библиотеку классов `PrimeService` в качестве еще одной зависимости. Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) на сайте GitHub.

Ниже показан окончательный макет решения:

```
/unit-testing-using-dotnet-test
    unit-testing-using-dotnet-test.sln
    /PrimeService
        Source Files
        PrimeService.csproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.csproj
```

Чтобы добавить тестовый проект в решение, выполните команду [dotnet sln](../tools/dotnet-sln.md) в каталоге *unit-testing-using-dotnet-test*:

```
dotnet sln add .\PrimeService.Tests\PrimeService.Tests.csproj
```

## <a name="creating-the-first-test"></a>Создание первого теста

Подход TDD предполагает создание теста, который завершается ошибкой, обеспечение его успешного выполнения и повтор этого процесса. Удалите файл *UnitTest1.cs* из каталога *PrimeService.Tests* и создайте новый файл C# с именем *PrimeService_IsPrimeShould.cs*. Добавьте следующий код:

```csharp
using Xunit;
using Prime.Services;

namespace Prime.UnitTests.Services
{
    public class PrimeService_IsPrimeShould
    {
        private readonly PrimeService _primeService;

        public PrimeService_IsPrimeShould()
        {
            _primeService = new PrimeService();
        }

        [Fact]
        public void ReturnFalseGivenValueOf1()
        {
            var result = _primeService.IsPrime(1);

            Assert.False(result, "1 should not be prime");
        }
    }
}
```

Атрибут `[Fact]` обозначает метод теста, который выполняется с помощью средства выполнения тестов. Из папки *PrimeService.Tests* выполните команду [`dotnet test`](../tools/dotnet-test.md) для создания тестов и библиотеки классов, а затем выполните тесты. Средство запуска тестов xUnit содержит точку входа в программу для выполнения тестов. `dotnet test` запускает средство выполнения тестов с помощью проекта модульного теста, который вы создали.

Тест не будет пройден. Вы еще не создали реализацию. Чтобы тест был пройден, напишите простейший код в классе `PrimeService`, который работает. Замените существующую реализацию метода `IsPrime` следующим кодом:

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

Теперь, когда тест проходит успешно, пора создать дополнительные тесты. Есть еще ряд элементарных случаев с простыми числами 0, -1. Можно добавить их в качестве тестов с помощью атрибута `[Fact]`, но это скоро станет утомительным. Есть другие атрибуты xUnit, которые позволяют создавать наборы похожих тестов.

- `[Theory]` представляет набор тестов, которые выполняют один и тот же код, но имеют разные входные аргументы.

- Атрибут `[InlineData]` задает значения для этих входных данных.

Вместо того чтобы создавать новые тесты, используйте эти два атрибута, `[Theory]` и `[InlineData]`, чтобы создать в файле *PrimeService_IsPrimeShould.cs* единый алгоритм, который проверяет несколько значений меньше 2, то есть наименьшего простого числа:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs?name=Sample_TestCode)]

Выполните `dotnet test` повторно. Два из этих тестов должны завершиться ошибкой. Для успешного выполнения всех тестов нужно изменить предложение `if` в начале метода `IsPrime` в файле *PrimeService.cs*:

```csharp
if (candidate < 2)
```

Продолжайте итерации, добавляя тесты, алгоритмы и код в главной библиотеке. В результате вы получите [готовую версию тестов](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) и [полную реализацию библиотеки](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-using-dotnet-test/PrimeService/PrimeService.cs).

### <a name="additional-resources"></a>Дополнительные ресурсы

- [Тестирование логики контроллера в ASP.NET Core](/aspnet/core/mvc/controllers/testing)
