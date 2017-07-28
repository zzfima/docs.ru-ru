---
title: "Выполнение выборочных модульных тестов"
description: "Демонстрация использования выражения фильтра для выполнения выборочных модульных тестов с помощью команды dotnet test."
keywords: ".NET, .NET Core, модульный тест, выборочный тест"
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 13d01272-bbf8-456c-a97a-560001d1a7f2
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: af832d04d2cba530a93710a90701ab119a66deef
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="running-selective-unit-tests"></a>Выполнение выборочных модульных тестов

В следующих примерах используется `dotnet test`. Если вы используете `vstest.console.exe`, замените `--filter ` на `--testcasefilter:`.

## <a name="mstest"></a>MSTest

```csharp
namespace MSTestNamespace
{
    using Microsoft.VisualStudio.TestTools.UnitTesting;

    [TestClass]
    public class UnitTestClass1
    {
        [Priority(2)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [TestCategory("CategoryA")]
        [Priority(3)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| Выражение | Результат |
| ---------- | ------ |
| `dotnet test --filter Method` | Выполняет тесты, `FullyQualifiedName` которых содержит `Method`. Доступно в `vstest 15.1+`. |
| `dotnet test --filter Name~TestMethod1` | Выполняет тесты, имя которых содержит `TestMethod1`. |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | Выполняет тесты, которые находятся в классе `MSTestNamespace.UnitTestClass1`.<br>**Примечание.** Значение `ClassName` должно иметь пространство имен, поэтому `ClassName=UnitTestClass1` не будет работать. |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | Выполняет все тесты, за исключением `MSTestNamespace.UnitTestClass1.TestMethod1`. |
| `dotnet test --filter TestCategory=CategoryA` | Выполняет тесты, которые помечены атрибутом `[TestCategory("CategoryA")]`. |
| `dotnet test --filter Priority=3` | Выполняет тесты, которые помечены атрибутом `[Priority(3)]`.<br>**Примечание.** `Priority~3` — недопустимое значение, так как оно не является строкой. |

**Использование условных операторов | и &amp;**

| Выражение | Результат |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | Выполняет тесты, имеющие `UnitTestClass1` в `FullyQualifiedName` **или** `TestCategory` является `CategoryA`. |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | Выполняет тесты, имеющие `UnitTestClass1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA`. |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | Выполняет тесты, в которых либо `FullyQualifiedName` содержит `UnitTestClass1` **и** `TestCategory` является `CategoryA`, **либо** `Priority` равно 1. |

## <a name="xunit"></a>xUnit

```csharp
namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "bvt")]
        [Trait("Priority", "1")]
        [Fact]
        public void foo()
        {
        }

        [Trait("Category", "Nightly")]
        [Trait("Priority", "2")]
        [Fact]
        public void bar()
        {
        }
    }
}
```

| Выражение | Результат |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | Выполняет только один тест — `XUnitNamespace.TestClass1.Test1`. |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | Выполняет все тесты, за исключением `XUnitNamespace.TestClass1.Test1`. |
| `dotnet test --filter DisplayName~TestClass1` | Выполняет тесты, отображаемое имя которых содержит `TestClass1`. |

В примере кода определенные характеристики с ключами `Category` и `Priority` можно использовать для фильтрации.

| Выражение | Результат |
| ---------- | ------ |
| `dotnet test --filter XUnit` | Выполняет тесты, `FullyQualifiedName` которых содержит `XUnit`.  Доступно в `vstest 15.1+`. |
| `dotnet test --filter Category=bvt` | Выполняет тесты, имеющие `[Trait("Category", "bvt")]`. |

**Использование условных операторов | и &amp;**

| Выражение | Результат |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | Выполняет тесты, имеющие `TestClass1` в `FullyQualifiedName` **или** `Category` является `Nightly`. |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | Выполняет тесты, имеющие `TestClass1` в `FullyQualifiedName` **или** `Category` является `Nightly`. |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | Выполняет тесты, в которых либо `FullyQualifiedName` содержит `TestClass1` **и** `Category` является `CategoryA`, **либо** `Priority` равно 1. |

