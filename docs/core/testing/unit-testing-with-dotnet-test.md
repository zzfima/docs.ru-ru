---
title: "Модульное тестирование в .NET Core с помощью команды dotnet-test | Документы Майкрософт"
description: "Тестирование модулей в .NET Core с помощью команды dotnet-test"
keywords: .NET, .NET Core
author: ardalis
ms.author: wiwagn
ms.date: 002/02/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdcdb812-6f13-4f20-9e90-0c0977937142
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: cd860241f5f20b6a4f1ccfec60e0c9cd5079152a
ms.lasthandoff: 03/07/2017

---

# <a name="unit-testing-in-net-core-using-dotnet-test"></a>Тестирование модулей в .NET Core с помощью команды dotnet-test

Авторы: [Стив Смит](http://ardalis.com) (Steve Smith) и [Билл Вагнер](https://github.com/BillWagner) (Bill Wagner)

[Просмотреть или скачать образец кода](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test)

## <a name="creating-the-projects"></a>Создание проектов

В разделе [Написание библиотек с помощью кроссплатформенных средств](../tutorials/libraries.md) приводятся сведения об организации исходного кода и тестов для решений, состоящих из нескольких проектов. В этой статье используются эти соглашения. Итоговая структура проекта будет похожа на следующую:

```
/unit-testing-using-dotnet-test
|__/PrimeService
   |__Source Files
   |__PrimeService.csproj
|__/PrimeService.Tests
   |__Test Files
   |__PrimeService.csproj
```

### <a name="creating-the-source-project"></a>Создание исходного проекта

Перейдите в каталог `unit-testing-using-dotnet-test` и создайте каталог `PrimeService`.
Перейдите в этот каталог и выполните команду `dotnet new classib`, чтобы создать исходный проект.


Переименуйте `Class1.cs` в `PrimeService.cs`. Чтобы использовать разработку на основе тестирования (TDD), вы создадите сбойную реализацию класса `PrimeService`:

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

Далее вернитесь в каталог "unit-testing-using-dotnet-test" и создайте каталог `PrimeServices.Tests`.
Перейдите в каталог `PrimeService.Tests` и создайте проект с помощью команды `dotnet new xunit`. `dotnet xunit` создает тестовый проект, который использует xUnit в качестве библиотеки тестов. 

Созданный шаблон настроил средство запуска тестов в файле PrimeServiceTests.csproj:

```xml
  <ItemGroup>
    <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-preview-20170125-04" />
    <PackageReference Include="xunit" Version="2.2.0-beta5-build3474" />
    <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0-beta5-build1225" />
  </ItemGroup>
```

Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда
`dotnet new` добавила пакет xUnit и средство запуска xUnit. Вам нужно добавить пакет PrimeService в проект в качестве еще одной зависимости. Для этого можно использовать CLI `dotnet`:

```
dotnet add reference ../PrimeService/PrimeService.csproj
```

Либо можно отредактировать непосредственно файл `PrimeService.Tests.csproj`.
Сразу после первого узла `<ItemGroup>` добавьте еще один узел `<ItemGroup>` со ссылкой на проект библиотеки:

```xml
  <ItemGroup>
    <ProjectReference Include="..\PrimeService\PrimeService.csproj" />
  </ItemGroup>
```

Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService.Tests.csproj) на сайте GitHub.

Создав эту начальную структуру, вы можете написать первый тест.
Успешная проверка этого первого модульного теста означает, что все настроено и дальнейшее добавление компонентов и тестов должно происходить без проблем.

## <a name="creating-the-first-test"></a>Создание первого теста

Перед созданием библиотеки или тестов нужно запустить `dotnet restore` в обоих каталогах `PrimeService` и `PrimeService.Tests`. Эта команда восстанавливает все необходимые пакеты NuGet для каждого проекта.

Подход TDD предполагает создание теста, который завершается ошибкой, обеспечение его успешного выполнения и повтор этого процесса. Итак, создадим этот тест, завершающийся ошибкой. Удалите файл `UnitTest1.cs` из каталога `PrimeService.Tests` и создайте файл C# `PrimeService_IsPrimeShould.cs` со следующим содержимым:

```cs
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

            Assert.False(result, $"1 should not be prime");
        }
    }
}
```

Атрибут `[Fact]` означает, что метод используется как отдельный тест. 

Сохраните этот файл, а затем выполните команду `dotnet build` для сборки тестового проекта.
Если вы еще не выполнили сборку проекта `PrimeService`, система сборки обнаружит это и выполнит ее, так как это зависимость тестового проекта.

Теперь выполните команду `dotnet test`, чтобы запустить тесты из консоли.
Средство запуска тестов xUnit имеет точку входа в программу для выполнения тестов из консоли. `dotnet test` запускает средство запуска тестов и передает ему аргумент командной строки, который указывает на сборку, содержащую тесты.

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

### <a name="adding-more-features"></a>Добавление дополнительных возможностей

Теперь, когда этот тест проходит успешно, пора создать дополнительные тесты.
Есть еще ряд элементарных случаев с простыми числами: 0, -1. Можно добавить их в качестве тестов с помощью атрибутов `[Fact]`, но это скоро станет утомительным. Есть другие атрибуты xUnit, которые позволяют создавать наборы похожих тестов.  `Theory` представляет набор тестов, которые выполняют один и тот же код, но имеют разные входные аргументы.
С помощью атрибута `[InlineData]` можно указать значения для этих входных аргументов. 
 
 Вместо создания новых тестов используйте эти два атрибута, чтобы создать единый алгоритм, который проверяет некоторые значения менее 2, то есть наименьшего простого числа:

[!code-csharp[Sample_TestCode](../../../samples/core/getting-started/unit-testing-using-dotnet-test/PrimeService.Tests/PrimeService_IsPrimeShould.cs#Sample_TestCode "Первые тесты")]
```

Run `dotnet test` and you'll see that two of these tests fail.
You can make them pass by changing the service. You need to change
the `if` clause at the beginning of the method:

```cs
if(candidate < 2)
```

Теперь все эти тесты проходят успешно.

Вы можете продолжать итерации, добавляя тесты, алгоритмы и код в главной библиотеке. Вскоре вы получите [готовую версию тестов](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/test/PrimeService.Tests/PrimeService_IsPrimeShould.cs) и [полную реализацию библиотеки](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/src/PrimeService/PrimeService.cs).

Вы создали небольшую библиотеку и набор модульных тестов для нее.
Вы структурировали решение, чтобы упростить добавление новых пакетов и тестов и получить возможность сосредоточиться на основной проблеме. Средства будут выполняться автоматически.

