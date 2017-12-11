---
title: "Модульное тестирование .NET Core в Visual Basic с использованием dotnet test и NUnit"
description: "Сведения о концепциях модульного тестирования в .NET Core в рамках пошаговой процедуры по созданию примера Visual Basic решения с помощью NUnit."
author: rprouse
ms.date: 12/01/2017
ms.topic: article
dev_langs: vb
ms.prod: .net-core
ms.openlocfilehash: 2166da36fe9d0297f03e7c38249135d281b9a5d6
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/06/2017
---
# <a name="unit-testing-visual-basic-net-core-libraries-using-dotnet-test-and-nunit"></a>Модульное тестирование библиотек .NET Core в Visual Basic с использованием dotnet test и NUnit

Этот учебник описывает пошаговую процедуру по созданию примера решения для изучения концепций модульного тестирования. Если при изучении учебника вы предпочитаете использовать готовое решение, [просмотрите или скачайте пример кода](https://github.com/dotnet/docs/tree/master/samples/core/getting-started/unit-testing-vb-nunit/) перед началом работы. Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="creating-the-source-project"></a>Создание исходного проекта

Откройте окно оболочки. Создайте каталог с именем *unit-testing-vb-nunit* для хранения решения. В этом каталоге выполните команду выполните команду [`dotnet new sln`](../tools/dotnet-new.md), чтобы создать решение. Этот метод упрощает управление библиотекой классов и проектом модульного теста. В каталоге решения создайте каталог *PrimeService*. На данный момент структура каталогов и файлов выглядит следующим образом:

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
```

Перейдите в каталог *PrimeService* и выполните команду [`dotnet new classlib -lang VB`](../tools/dotnet-new.md), чтобы создать исходный проект. Переименуйте *Class1.VB* в *PrimeService.VB*. Чтобы использовать разработку на основе тестирования (TDD), требуется создать сбойную реализацию класса `PrimeService`:

```vb
Imports System

Namespace Prime.Services
    Public Class PrimeService
        Public Function IsPrime(candidate As Integer) As Boolean
            Throw New NotImplementedException("Please create a test first")
        End Function
    End Class
End Namespace
```

Вернитесь в каталог *unit-testing-vb-using-stest*. Чтобы добавить проект библиотеки классов в решение, выполните команду [`dotnet sln add .\PrimeService\PrimeService.vbproj`](../tools/dotnet-sln.md).

## <a name="install-the-nunit-project-template"></a>Установка шаблона проекта NUnit

Перед созданием тестового проекта необходимо установить шаблоны тестовых проектов NUnit. Это действие необходимо выполнить только один раз на каждом компьютере разработчика, где создаются новые проекты NUnit. Для установки шаблонов NUnit выполните [`dotnet new -i NUnit3.DotNetNew.Template`](../tools/dotnet-new.md).

 ```
 dotnet new -i NUnit3.DotNetNew.Template
 ```

## <a name="creating-the-test-project"></a>Создание тестового проекта

Затем создайте каталог *PrimeService.Tests*. Ниже представлена структура каталогов:

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
```

Перейдите в каталог *PrimeService.Tests* и создайте проект с помощью [`dotnet new nunit -lang VB`](../tools/dotnet-new.md). Эта команда создает тестовый проект, использующий NUnit в качестве библиотеки тестов. Созданный шаблон настраивает средство выполнения тестов в файле *PrimeServiceTests.vbproj*:

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.5.0" />
  <PackageReference Include="NUnit" Version="3.9.0" />
  <PackageReference Include="NUnit3TestAdapter" Version="3.9.0" />
</ItemGroup>
```

Тестовый проект требует других пакетов для создания и выполнения модульных тестов. Команда `dotnet new` на предыдущем шаге добавляет NUnit и адаптер тестирования NUnit. Теперь добавьте в проект библиотеку классов `PrimeService` в качестве еще одной зависимости. Используйте команду [`dotnet add reference`](../tools/dotnet-add-reference.md):

```
dotnet add reference ../PrimeService/PrimeService.vbproj
```

Все содержимое файла можно просмотреть в [репозитории образцов](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService.Tests.vbproj) на сайте GitHub.

Ниже показан окончательный макет решения:

```
/unit-testing-vb-nunit
    unit-testing-vb-nunit.sln
    /PrimeService
        Source Files
        PrimeService.vbproj
    /PrimeService.Tests
        Test Source Files
        PrimeServiceTests.vbproj
```

Выполните команду [`dotnet sln add .\PrimeService.Tests\PrimeService.Tests.vbproj`](../tools/dotnet-sln.md) в каталоге *unit-testing-vb-nunit*.

## <a name="creating-the-first-test"></a>Создание первого теста

Подход TDD предполагает создание теста, который завершается ошибкой, обеспечение его успешного выполнения и повтор этого процесса. Удалите файл *UnitTest1.vb* из каталога *PrimeService.Tests* и создайте файл Visual Basic с именем *PrimeService_IsPrimeShould.VB*. Добавьте следующий код:

```vb
Imports NUnit.Framework

Namespace PrimeService.Tests
    <TestFixture>
    Public Class PrimeService_IsPrimeShould
        Private _primeService As Prime.Services.PrimeService = New Prime.Services.PrimeService()

        <Test>
        Sub ReturnFalseGivenValueOf1()
            Dim result As Boolean = _primeService.IsPrime(1)

            Assert.False(result, "1 should not be prime")
        End Sub

    End Class
End Namespace
```

Атрибут `<TestFixture>` указывает класс, который содержит тесты. Атрибут `<Test>` обозначает метод, который выполняется с помощью средства выполнения тестов. Из каталога *unit-testing-vb-nunit* выполните команду [`dotnet test`](../tools/dotnet-test.md) для создания тестов и библиотеки классов, а затем выполните тесты. Средство запуска тестов NUnit содержит точку входа в программу для выполнения тестов. `dotnet test` запускает средство выполнения тестов с помощью проекта модульного теста, который вы создали.

Тест не будет пройден. Вы еще не создали реализацию. Чтобы тест был пройден, напишите простейший код в классе `PrimeService`, который работает:

```vb
Public Function IsPrime(candidate As Integer) As Boolean
    If candidate = 1 Then
        Return False
    End If
    Throw New NotImplementedException("Please create a test first")
End Function
```

Выполните команду `dotnet test` еще раз в каталоге *unit-testing-vb-nunit*. Команда `dotnet test` запускает сборку для проекта `PrimeService` и затем для проекта `PrimeService.Tests`. После сборки обоих проектов она запускает этот отдельный тест. Он выполняется.

## <a name="adding-more-features"></a>Добавление дополнительных возможностей

Теперь, когда тест проходит успешно, пора создать дополнительные тесты. Есть еще ряд элементарных случаев с простыми числами: 0, -1. Можно добавить их в качестве тестов с помощью атрибута `<Test>`, но это скоро станет утомительным. Есть другие атрибуты xUnit, которые позволяют создавать наборы похожих тестов.  Атрибут `<TestCase>` представляет набор тестов, которые выполняют один и тот же код, но имеют разные входные аргументы. С помощью атрибута `<TestCase>` можно указать значения для этих входных аргументов.

Вместо создания тестов примените эти два атрибута, чтобы создать последовательность тестов, которая проверяет несколько значений меньше 2, то есть наименьшего простого числа.

[!code-vb[Sample_TestCode](../../../samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb?name=Sample_TestCode)]

Выполните команду `dotnet test`, и два из этих тестов завершаются ошибкой. Для успешного выполнения всех тестов нужно изменить предложение `if` в начале метода:

```vb
if candidate < 2
```

Продолжайте итерации, добавляя тесты, алгоритмы и код в главной библиотеке. В результате вы получите [готовую версию тестов](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService.Tests/PrimeService_IsPrimeShould.vb) и [полную реализацию библиотеки](https://github.com/dotnet/docs/blob/master/samples/core/getting-started/unit-testing-vb-nunit/PrimeService/PrimeService.vb).

Вы создали небольшую библиотеку и набор модульных тестов для нее. Вы структурировали решение, чтобы сделать добавление новых пакетов и тестов частью обычного рабочего процесса и получить возможность сосредоточиться на задачах приложения.
