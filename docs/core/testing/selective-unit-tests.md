---
title: Выполнение выборочных модульных тестов в .NET Core
description: Как использовать выражения фильтра для выполнения выборочных модульных тестов с помощью команды dotnet test в .NET Core.
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.custom: seodec18
ms.openlocfilehash: 3c24fb8cc5024399ae523801373b0fd8eff85f45
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151750"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="cfe03-103">Выполнение выборочных модульных тестов</span><span class="sxs-lookup"><span data-stu-id="cfe03-103">Running selective unit tests</span></span>

<span data-ttu-id="cfe03-104">В следующих примерах используется `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-104">The following examples use `dotnet test`.</span></span> <span data-ttu-id="cfe03-105">Если вы используете `vstest.console.exe`, замените `--filter ` на `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-105">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="cfe03-106">MSTest</span><span class="sxs-lookup"><span data-stu-id="cfe03-106">MSTest</span></span>

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace MSTestNamespace
{
    [TestClass]
    public class UnitTest1
    {
        [TestCategory("CategoryA")]
        [Priority(1)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [Priority(2)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="cfe03-107">Выражение</span><span class="sxs-lookup"><span data-stu-id="cfe03-107">Expression</span></span> | <span data-ttu-id="cfe03-108">Результат</span><span class="sxs-lookup"><span data-stu-id="cfe03-108">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="cfe03-109">Выполняет тесты, `FullyQualifiedName` которых содержит `Method`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-109">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="cfe03-110">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-110">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="cfe03-111">Выполняет тесты, имя которых содержит `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-111">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="cfe03-112">Выполняет тесты, которые находятся в классе `MSTestNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-112">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="cfe03-113">**Примечание.** Значение `ClassName` должно иметь пространство имен, поэтому `ClassName=UnitTest1` не будет работать.</span><span class="sxs-lookup"><span data-stu-id="cfe03-113">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="cfe03-114">Выполняет все тесты, за исключением `MSTestNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-114">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="cfe03-115">Выполняет тесты, которые помечены атрибутом `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-115">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="cfe03-116">Выполняет тесты, которые помечены атрибутом `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-116">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="cfe03-117">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="cfe03-117">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="cfe03-118">Выражение</span><span class="sxs-lookup"><span data-stu-id="cfe03-118">Expression</span></span> | <span data-ttu-id="cfe03-119">Результат</span><span class="sxs-lookup"><span data-stu-id="cfe03-119">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="cfe03-120">Выполняет тесты, имеющие `UnitTest1` в `FullyQualifiedName` **или** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-120">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="cfe03-121">Выполняет тесты, имеющие `UnitTest1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-121">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="cfe03-122">Выполняет тесты, в которых либо `FullyQualifiedName` содержит `UnitTest1` **и** `TestCategory` является `CategoryA`, **либо** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="cfe03-122">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="cfe03-123">xUnit</span><span class="sxs-lookup"><span data-stu-id="cfe03-123">xUnit</span></span>

```csharp
using Xunit;

namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "CategoryA")]
        [Trait("Priority", "1")]
        [Fact]
        public void Test1()
        {
        }

        [Trait("Priority", "2")]
        [Fact]
        public void Test2()
        {
        }
    }
}
```

| <span data-ttu-id="cfe03-124">Выражение</span><span class="sxs-lookup"><span data-stu-id="cfe03-124">Expression</span></span> | <span data-ttu-id="cfe03-125">Результат</span><span class="sxs-lookup"><span data-stu-id="cfe03-125">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="cfe03-126">Выполняет только один тест — `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-126">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="cfe03-127">Выполняет все тесты, за исключением `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-127">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="cfe03-128">Выполняет тесты, отображаемое имя которых содержит `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-128">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="cfe03-129">В примере кода определенные характеристики с ключами `Category` и `Priority` можно использовать для фильтрации.</span><span class="sxs-lookup"><span data-stu-id="cfe03-129">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="cfe03-130">Выражение</span><span class="sxs-lookup"><span data-stu-id="cfe03-130">Expression</span></span> | <span data-ttu-id="cfe03-131">Результат</span><span class="sxs-lookup"><span data-stu-id="cfe03-131">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="cfe03-132">Выполняет тесты, `FullyQualifiedName` которых содержит `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-132">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="cfe03-133">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-133">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="cfe03-134">Выполняет тесты, имеющие `[Trait("Category", "CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-134">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="cfe03-135">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="cfe03-135">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="cfe03-136">Выражение</span><span class="sxs-lookup"><span data-stu-id="cfe03-136">Expression</span></span> | <span data-ttu-id="cfe03-137">Результат</span><span class="sxs-lookup"><span data-stu-id="cfe03-137">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="cfe03-138">Выполняет тесты, имеющие `TestClass1` в `FullyQualifiedName` **или** `Category` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-138">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="cfe03-139">Выполняет тесты, имеющие `TestClass1` в `FullyQualifiedName` **или** `Category` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-139">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="cfe03-140">Выполняет тесты, в которых либо `FullyQualifiedName` содержит `TestClass1` **и** `Category` является `CategoryA`, **либо** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="cfe03-140">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="cfe03-141">NUnit</span><span class="sxs-lookup"><span data-stu-id="cfe03-141">NUnit</span></span>

```csharp
using NUnit.Framework;

namespace NUnitNamespace
{
    public class UnitTest1
    {
        [Category("CategoryA")]
        [Property("Priority", 1)]
        [Test]
        public void TestMethod1()
        {
        }

        [Property("Priority", 2)]
        [Test]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="cfe03-142">Выражение</span><span class="sxs-lookup"><span data-stu-id="cfe03-142">Expression</span></span> | <span data-ttu-id="cfe03-143">Результат</span><span class="sxs-lookup"><span data-stu-id="cfe03-143">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="cfe03-144">Выполняет тесты, `FullyQualifiedName` которых содержит `Method`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-144">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="cfe03-145">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-145">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="cfe03-146">Выполняет тесты, имя которых содержит `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-146">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="cfe03-147">Выполняет тесты, которые находятся в классе `NUnitNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-147">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="cfe03-148">Выполняет все тесты, за исключением `NUnitNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-148">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="cfe03-149">Выполняет тесты, которые помечены атрибутом `[Category("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-149">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="cfe03-150">Выполняет тесты, которые помечены атрибутом `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-150">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="cfe03-151">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="cfe03-151">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="cfe03-152">Выражение</span><span class="sxs-lookup"><span data-stu-id="cfe03-152">Expression</span></span> | <span data-ttu-id="cfe03-153">Результат</span><span class="sxs-lookup"><span data-stu-id="cfe03-153">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="cfe03-154">Выполняет тесты, имеющие `UnitTest1` в `FullyQualifiedName` **или** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-154">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="cfe03-155">Выполняет тесты, имеющие `UnitTest1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="cfe03-155">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="cfe03-156">Выполняет тесты, в которых либо `FullyQualifiedName` содержит `UnitTest1` **и** `TestCategory` является `CategoryA`, **либо** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="cfe03-156">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
