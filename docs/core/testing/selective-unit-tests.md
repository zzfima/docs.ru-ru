---
title: Выполнение выборочных модульных тестов
description: Демонстрация использования выражения фильтра для выполнения выборочных модульных тестов с помощью команды dotnet test.
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 77ac7ab5a46150bd3654d50e6686087c804b8440
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="051d4-103">Выполнение выборочных модульных тестов</span><span class="sxs-lookup"><span data-stu-id="051d4-103">Running selective unit tests</span></span>

<span data-ttu-id="051d4-104">В следующих примерах используется `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="051d4-104">The following examples use `dotnet test`.</span></span> <span data-ttu-id="051d4-105">Если вы используете `vstest.console.exe`, замените `--filter ` на `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="051d4-105">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="051d4-106">MSTest</span><span class="sxs-lookup"><span data-stu-id="051d4-106">MSTest</span></span>

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

| <span data-ttu-id="051d4-107">Выражение</span><span class="sxs-lookup"><span data-stu-id="051d4-107">Expression</span></span> | <span data-ttu-id="051d4-108">Результат</span><span class="sxs-lookup"><span data-stu-id="051d4-108">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="051d4-109">Выполняет тесты, `FullyQualifiedName` которых содержит `Method`.</span><span class="sxs-lookup"><span data-stu-id="051d4-109">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="051d4-110">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="051d4-110">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="051d4-111">Выполняет тесты, имя которых содержит `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="051d4-111">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | <span data-ttu-id="051d4-112">Выполняет тесты, которые находятся в классе `MSTestNamespace.UnitTestClass1`.</span><span class="sxs-lookup"><span data-stu-id="051d4-112">Runs tests which are in class `MSTestNamespace.UnitTestClass1`.</span></span><br><span data-ttu-id="051d4-113">**Примечание.** Значение `ClassName` должно иметь пространство имен, поэтому `ClassName=UnitTestClass1` не будет работать.</span><span class="sxs-lookup"><span data-stu-id="051d4-113">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTestClass1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | <span data-ttu-id="051d4-114">Выполняет все тесты, за исключением `MSTestNamespace.UnitTestClass1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="051d4-114">Runs all tests except `MSTestNamespace.UnitTestClass1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="051d4-115">Выполняет тесты, которые помечены атрибутом `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="051d4-115">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=3` | <span data-ttu-id="051d4-116">Выполняет тесты, которые помечены атрибутом `[Priority(3)]`.</span><span class="sxs-lookup"><span data-stu-id="051d4-116">Runs tests which are annotated with `[Priority(3)]`.</span></span><br><span data-ttu-id="051d4-117">**Примечание.** `Priority~3` — недопустимое значение, так как оно не является строкой.</span><span class="sxs-lookup"><span data-stu-id="051d4-117">**Note:** `Priority~3` is an invalid value, as it isn't a string.</span></span> |

<span data-ttu-id="051d4-118">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="051d4-118">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="051d4-119">Выражение</span><span class="sxs-lookup"><span data-stu-id="051d4-119">Expression</span></span> | <span data-ttu-id="051d4-120">Результат</span><span class="sxs-lookup"><span data-stu-id="051d4-120">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="051d4-121">Выполняет тесты, имеющие `UnitTestClass1` в `FullyQualifiedName` **или** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="051d4-121">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | <span data-ttu-id="051d4-122">Выполняет тесты, имеющие `UnitTestClass1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="051d4-122">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="051d4-123">Выполняет тесты, в которых либо `FullyQualifiedName` содержит `UnitTestClass1` **и** `TestCategory` является `CategoryA`, **либо** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="051d4-123">Runs tests which have either `FullyQualifiedName` containing `UnitTestClass1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="051d4-124">xUnit</span><span class="sxs-lookup"><span data-stu-id="051d4-124">xUnit</span></span>

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

| <span data-ttu-id="051d4-125">Выражение</span><span class="sxs-lookup"><span data-stu-id="051d4-125">Expression</span></span> | <span data-ttu-id="051d4-126">Результат</span><span class="sxs-lookup"><span data-stu-id="051d4-126">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="051d4-127">Выполняет только один тест — `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="051d4-127">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="051d4-128">Выполняет все тесты, за исключением `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="051d4-128">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="051d4-129">Выполняет тесты, отображаемое имя которых содержит `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="051d4-129">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="051d4-130">В примере кода определенные характеристики с ключами `Category` и `Priority` можно использовать для фильтрации.</span><span class="sxs-lookup"><span data-stu-id="051d4-130">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="051d4-131">Выражение</span><span class="sxs-lookup"><span data-stu-id="051d4-131">Expression</span></span> | <span data-ttu-id="051d4-132">Результат</span><span class="sxs-lookup"><span data-stu-id="051d4-132">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="051d4-133">Выполняет тесты, `FullyQualifiedName` которых содержит `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="051d4-133">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="051d4-134">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="051d4-134">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=bvt` | <span data-ttu-id="051d4-135">Выполняет тесты, имеющие `[Trait("Category", "bvt")]`.</span><span class="sxs-lookup"><span data-stu-id="051d4-135">Runs tests which have `[Trait("Category", "bvt")]`.</span></span> |

<span data-ttu-id="051d4-136">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="051d4-136">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="051d4-137">Выражение</span><span class="sxs-lookup"><span data-stu-id="051d4-137">Expression</span></span> | <span data-ttu-id="051d4-138">Результат</span><span class="sxs-lookup"><span data-stu-id="051d4-138">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | <span data-ttu-id="051d4-139">Выполняет тесты, имеющие `TestClass1` в `FullyQualifiedName` **или** `Category` является `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="051d4-139">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `Nightly`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | <span data-ttu-id="051d4-140">Выполняет тесты, имеющие `TestClass1` в `FullyQualifiedName` **или** `Category` является `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="051d4-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `Nightly`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | <span data-ttu-id="051d4-141">Выполняет тесты, в которых либо `FullyQualifiedName` содержит `TestClass1` **и** `Category` является `CategoryA`, **либо** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="051d4-141">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |
