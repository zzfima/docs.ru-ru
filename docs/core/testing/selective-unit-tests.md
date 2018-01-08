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
ms.workload: dotnetcore
ms.openlocfilehash: a650e971afd63171b0cc12f679d81bc222a609a5
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="ed904-104">Выполнение выборочных модульных тестов</span><span class="sxs-lookup"><span data-stu-id="ed904-104">Running selective unit tests</span></span>

<span data-ttu-id="ed904-105">В следующих примерах используется `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="ed904-105">The following examples use `dotnet test`.</span></span> <span data-ttu-id="ed904-106">Если вы используете `vstest.console.exe`, замените `--filter ` на `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="ed904-106">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="ed904-107">MSTest</span><span class="sxs-lookup"><span data-stu-id="ed904-107">MSTest</span></span>

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

| <span data-ttu-id="ed904-108">Выражение</span><span class="sxs-lookup"><span data-stu-id="ed904-108">Expression</span></span> | <span data-ttu-id="ed904-109">Результат</span><span class="sxs-lookup"><span data-stu-id="ed904-109">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="ed904-110">Выполняет тесты, `FullyQualifiedName` которых содержит `Method`.</span><span class="sxs-lookup"><span data-stu-id="ed904-110">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="ed904-111">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="ed904-111">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="ed904-112">Выполняет тесты, имя которых содержит `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="ed904-112">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | <span data-ttu-id="ed904-113">Выполняет тесты, которые находятся в классе `MSTestNamespace.UnitTestClass1`.</span><span class="sxs-lookup"><span data-stu-id="ed904-113">Runs tests which are in class `MSTestNamespace.UnitTestClass1`.</span></span><br><span data-ttu-id="ed904-114">**Примечание.** Значение `ClassName` должно иметь пространство имен, поэтому `ClassName=UnitTestClass1` не будет работать.</span><span class="sxs-lookup"><span data-stu-id="ed904-114">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTestClass1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | <span data-ttu-id="ed904-115">Выполняет все тесты, за исключением `MSTestNamespace.UnitTestClass1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="ed904-115">Runs all tests except `MSTestNamespace.UnitTestClass1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="ed904-116">Выполняет тесты, которые помечены атрибутом `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="ed904-116">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=3` | <span data-ttu-id="ed904-117">Выполняет тесты, которые помечены атрибутом `[Priority(3)]`.</span><span class="sxs-lookup"><span data-stu-id="ed904-117">Runs tests which are annotated with `[Priority(3)]`.</span></span><br><span data-ttu-id="ed904-118">**Примечание.** `Priority~3` — недопустимое значение, так как оно не является строкой.</span><span class="sxs-lookup"><span data-stu-id="ed904-118">**Note:** `Priority~3` is an invalid value, as it isn't a string.</span></span> |

<span data-ttu-id="ed904-119">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="ed904-119">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="ed904-120">Выражение</span><span class="sxs-lookup"><span data-stu-id="ed904-120">Expression</span></span> | <span data-ttu-id="ed904-121">Результат</span><span class="sxs-lookup"><span data-stu-id="ed904-121">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="ed904-122">Выполняет тесты, имеющие `UnitTestClass1` в `FullyQualifiedName` **или** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="ed904-122">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | <span data-ttu-id="ed904-123">Выполняет тесты, имеющие `UnitTestClass1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="ed904-123">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="ed904-124">Выполняет тесты, в которых либо `FullyQualifiedName` содержит `UnitTestClass1` **и** `TestCategory` является `CategoryA`, **либо** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="ed904-124">Runs tests which have either `FullyQualifiedName` containing `UnitTestClass1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="ed904-125">xUnit</span><span class="sxs-lookup"><span data-stu-id="ed904-125">xUnit</span></span>

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

| <span data-ttu-id="ed904-126">Выражение</span><span class="sxs-lookup"><span data-stu-id="ed904-126">Expression</span></span> | <span data-ttu-id="ed904-127">Результат</span><span class="sxs-lookup"><span data-stu-id="ed904-127">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="ed904-128">Выполняет только один тест — `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="ed904-128">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="ed904-129">Выполняет все тесты, за исключением `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="ed904-129">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="ed904-130">Выполняет тесты, отображаемое имя которых содержит `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="ed904-130">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="ed904-131">В примере кода определенные характеристики с ключами `Category` и `Priority` можно использовать для фильтрации.</span><span class="sxs-lookup"><span data-stu-id="ed904-131">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="ed904-132">Выражение</span><span class="sxs-lookup"><span data-stu-id="ed904-132">Expression</span></span> | <span data-ttu-id="ed904-133">Результат</span><span class="sxs-lookup"><span data-stu-id="ed904-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="ed904-134">Выполняет тесты, `FullyQualifiedName` которых содержит `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="ed904-134">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="ed904-135">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="ed904-135">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=bvt` | <span data-ttu-id="ed904-136">Выполняет тесты, имеющие `[Trait("Category", "bvt")]`.</span><span class="sxs-lookup"><span data-stu-id="ed904-136">Runs tests which have `[Trait("Category", "bvt")]`.</span></span> |

<span data-ttu-id="ed904-137">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="ed904-137">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="ed904-138">Выражение</span><span class="sxs-lookup"><span data-stu-id="ed904-138">Expression</span></span> | <span data-ttu-id="ed904-139">Результат</span><span class="sxs-lookup"><span data-stu-id="ed904-139">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | <span data-ttu-id="ed904-140">Выполняет тесты, имеющие `TestClass1` в `FullyQualifiedName` **или** `Category` является `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="ed904-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `Nightly`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | <span data-ttu-id="ed904-141">Выполняет тесты, имеющие `TestClass1` в `FullyQualifiedName` **или** `Category` является `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="ed904-141">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `Nightly`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | <span data-ttu-id="ed904-142">Выполняет тесты, в которых либо `FullyQualifiedName` содержит `TestClass1` **и** `Category` является `CategoryA`, **либо** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="ed904-142">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |
