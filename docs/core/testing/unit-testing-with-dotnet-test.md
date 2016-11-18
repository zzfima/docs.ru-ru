---
title: "Тестирование модулей в .NET Core с помощью команды dotnet-test"
description: "Тестирование модулей в .NET Core с помощью команды dotnet-test"
keywords: .NET, .NET Core
author: ardalis
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: bdcdb812-6f13-4f20-9e90-0c0977937142
translationtype: Human Translation
ms.sourcegitcommit: 15c55a87beb64f265a164db918c7721c7690fadf
ms.openlocfilehash: 0c98084786408a285111ae724ed404ce32160aea

---

# <a name="unit-testing-in-net-core-using-dotnet-test"></a>Тестирование модулей в .NET Core с помощью команды dotnet-test

Авторы: [Стив Смит](http://ardalis.com) (Steve Smith) и [Билл Вагнер](https://github.com/BillWagner) (Bill Wagner)

[Просмотреть или скачать образец кода](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-using-dotnet-test)

## <a name="creating-the-projects"></a>Создание проектов

В разделе [Написание библиотек с помощью кроссплатформенных средств](../tutorials/libraries.md) приводятся сведения об организации исходного кода и тестов для решений, состоящих из нескольких проектов. В этой статье используются эти соглашения. Итоговая структура проекта будет похожа на следующую:

```
/unit-testing-using-dotnet-test
|__global.json
|__/src
   |__/PrimeService
      |__Source Files
      |__project.json
|__/test
   |__/PrimeService.Tests
      |__Test Files
      |__project.json
```

В корневом каталоге необходимо создать файл `global.json`, содержащий имена каталогов `src` и `test`:

```json
{
    "projects": [
        "src",
        "test"
    ]
}
```

### <a name="creating-the-source-project"></a>Создание исходного проекта

Затем в каталоге `src` создайте каталог `PrimeService`.
Перейдите в этот каталог и выполните команду `dotnet new -t lib`, чтобы создать исходный проект.


Переименуйте `Library.cs` в `PrimeService.cs`. Чтобы использовать разработку на основе тестирования (TDD), вы создадите сбойную реализацию класса `PrimeService`:

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

Далее перейдите в каталог test и создайте каталог `PrimeServices.Tests`.
Перейдите в каталог `PrimeServices.Tests` и создайте проект с помощью команды `dotnet new -t xunittest`. `dotnet new -t xunittest` создает тестовый проект, который использует XUnit в качестве библиотеки тестов. 

Созданный шаблон настроил средство запуска тестов в корне `project.json`:

```json
{
  "version": "1.0.0-*",
  "testRunner": "xunit",
  // ...
}
```

Шаблон также задает использование `netcoreapp1.0` в узле платформы и включает в него необходимые директивы import, обеспечивающие работу xUnit.net с .NET Core RTM:

```json
  "frameworks": {
    "netcoreapp1.0": {
      "imports": [
        "dotnet54",
        "portable-net45+win8" 
      ]
    }
  }
```

Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда
`dotnet new` добавляет пакет xUnit и средство запуска xUnit. Вам необходимо добавить пакет PrimeService в проект в качестве еще одной зависимости:

```json
"dependencies": {
  "Microsoft.NETCore.App": {
    "type":"platform",
    "version": "1.0.0"
  },
  "xunit":"2.1.0",
  "dotnet-test-xunit": "1.0.0-rc2-192208-24",
  "PrimeService": {
    "target": "project"
  }
}
```

Обратите внимание на то, что проект `PrimeService` не содержит сведений о путях к каталогам. Так как структура проекта соответствует ожидаемой организации папок `src` и `test`, что указано в файле `global.json`, система сборки правильно определит расположение проекта. Добавляя элемент `"target": "project"`, вы сообщаете NuGet, что поиск необходимо осуществлять в каталогах проекта, а не в канале NuGet. При отсутствии этого ключа вы можете скачать пакет с тем же именем, что и у внутренней библиотеки.

Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/test/PrimeService.Tests/project.json) на сайте GitHub.

Создав эту начальную структуру, вы можете написать первый тест.
Успешная проверка этого первого модульного теста означает, что все настроено и дальнейшее добавление компонентов и тестов должно происходить без проблем.

## <a name="creating-the-first-test"></a>Создание первого теста

Подход TDD предполагает создание теста, который завершается ошибкой, обеспечение его успешного выполнения и повтор этого процесса. Итак, создадим этот тест, завершающийся ошибкой. Удалите файл `program.cs` из каталога `PrimeService.Tests` и создайте файл C# со следующим содержимым:

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

```cs
[Theory]
[InlineData(-1)]
[InlineData(0)]
[InlineData(1)]
public void ReturnFalseGivenValuesLessThan2(int value)
{
    var result = _primeService.IsPrime(value);

    Assert.False(result, $"{value} should not be prime");
}
```

Выполните команду `dotnet test`, и вы увидите, что два из этих тестов завершились ошибкой.
Чтобы они проходили успешно, измените код. Вам необходимо изменить предложение `if` в начале метода:

```cs
if(candidate < 2)
```

Теперь все эти тесты проходят успешно.

Вы можете продолжать итерации, добавляя тесты, алгоритмы и код в главной библиотеке. Вскоре вы получите [готовую версию тестов](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/test/PrimeService.Tests/PrimeServie_IsPrimeShould.cs) и [полную реализацию библиотеки](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-using-dotnet-test/src/PrimeService/PrimeService.cs).

Вы создали небольшую библиотеку и набор модульных тестов для нее.
Вы структурировали решение, чтобы упростить добавление новых пакетов и тестов и получить возможность сосредоточиться на основной проблеме. Средства будут выполняться автоматически.
   
   > [!TIP]
   > На платформе Windows можно использовать средство MSTest. Узнайте больше об [использовании MSTest в документе Windows](./using-mstest-on-windows.md).



<!--HONumber=Nov16_HO3-->


