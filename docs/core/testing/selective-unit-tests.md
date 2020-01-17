---
title: Выполнение выборочных модульных тестов
description: Как использовать выражения фильтра для выполнения выборочных модульных тестов с помощью команды dotnet test в .NET Core.
author: smadala
ms.date: 03/22/2017
ms.openlocfilehash: 57428dad2de6c2507ca2cdc42e3df9e83a1edd69
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715463"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="3bef1-103">Выполнение выборочных модульных тестов</span><span class="sxs-lookup"><span data-stu-id="3bef1-103">Running selective unit tests</span></span>

<span data-ttu-id="3bef1-104">Использовать выражения фильтра для выполнения выборочных модульных тестов можно с помощью команды `dotnet test` в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3bef1-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="3bef1-105">В этой статье показано, как отфильтровывать модульные тесты для выполнения.</span><span class="sxs-lookup"><span data-stu-id="3bef1-105">This article demonstrates how to filter which test are run.</span></span> <span data-ttu-id="3bef1-106">В следующих примерах используется `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="3bef1-107">Если вы используете `vstest.console.exe`, замените `--filter` на `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="3bef1-108">MSTest</span><span class="sxs-lookup"><span data-stu-id="3bef1-108">MSTest</span></span>

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

| <span data-ttu-id="3bef1-109">Выражение</span><span class="sxs-lookup"><span data-stu-id="3bef1-109">Expression</span></span> | <span data-ttu-id="3bef1-110">Результат</span><span class="sxs-lookup"><span data-stu-id="3bef1-110">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="3bef1-111">Выполняет тесты, `FullyQualifiedName` которых содержит `Method`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-111">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="3bef1-112">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-112">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="3bef1-113">Выполняет тесты, имя которых содержит `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-113">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="3bef1-114">Выполняет тесты, которые находятся в классе `MSTestNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-114">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="3bef1-115">**Примечание.** Значение `ClassName` должно иметь пространство имен, поэтому `ClassName=UnitTest1` не будет работать.</span><span class="sxs-lookup"><span data-stu-id="3bef1-115">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="3bef1-116">Выполняет все тесты, за исключением `MSTestNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-116">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="3bef1-117">Выполняет тесты, которые помечены атрибутом `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-117">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="3bef1-118">Выполняет тесты, которые помечены атрибутом `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-118">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="3bef1-119">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="3bef1-119">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="3bef1-120">Выражение</span><span class="sxs-lookup"><span data-stu-id="3bef1-120">Expression</span></span> | <span data-ttu-id="3bef1-121">Результат</span><span class="sxs-lookup"><span data-stu-id="3bef1-121">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="3bef1-122">Выполняет тесты с `UnitTest1` в `FullyQualifiedName` **или** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-122">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="3bef1-123">Выполняет тесты с `UnitTest1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-123">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="3bef1-124">Выполняет тесты с `UnitTest1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA` **или** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="3bef1-124">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="3bef1-125">xUnit</span><span class="sxs-lookup"><span data-stu-id="3bef1-125">xUnit</span></span>

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

| <span data-ttu-id="3bef1-126">Выражение</span><span class="sxs-lookup"><span data-stu-id="3bef1-126">Expression</span></span> | <span data-ttu-id="3bef1-127">Результат</span><span class="sxs-lookup"><span data-stu-id="3bef1-127">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="3bef1-128">Выполняет только один тест — `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-128">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="3bef1-129">Выполняет все тесты, за исключением `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-129">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="3bef1-130">Выполняет тесты, отображаемое имя которых содержит `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-130">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="3bef1-131">В примере кода определенные характеристики с ключами `Category` и `Priority` можно использовать для фильтрации.</span><span class="sxs-lookup"><span data-stu-id="3bef1-131">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="3bef1-132">Выражение</span><span class="sxs-lookup"><span data-stu-id="3bef1-132">Expression</span></span> | <span data-ttu-id="3bef1-133">Результат</span><span class="sxs-lookup"><span data-stu-id="3bef1-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="3bef1-134">Выполняет тесты, `FullyQualifiedName` которых содержит `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-134">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="3bef1-135">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-135">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="3bef1-136">Выполняет тесты, имеющие `[Trait("Category", "CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-136">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="3bef1-137">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="3bef1-137">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="3bef1-138">Выражение</span><span class="sxs-lookup"><span data-stu-id="3bef1-138">Expression</span></span> | <span data-ttu-id="3bef1-139">Результат</span><span class="sxs-lookup"><span data-stu-id="3bef1-139">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="3bef1-140">Выполняет тесты с `TestClass1` в `FullyQualifiedName` **или** `Category` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="3bef1-141">Выполняет тесты с `TestClass1` в `FullyQualifiedName` **или** `Category` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-141">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="3bef1-142">Выполняет тесты с `TestClass1` в `FullyQualifiedName` **и** `Category` является `CategoryA` **или** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="3bef1-142">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="3bef1-143">NUnit</span><span class="sxs-lookup"><span data-stu-id="3bef1-143">NUnit</span></span>

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

| <span data-ttu-id="3bef1-144">Выражение</span><span class="sxs-lookup"><span data-stu-id="3bef1-144">Expression</span></span> | <span data-ttu-id="3bef1-145">Результат</span><span class="sxs-lookup"><span data-stu-id="3bef1-145">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="3bef1-146">Выполняет тесты, `FullyQualifiedName` которых содержит `Method`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-146">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="3bef1-147">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-147">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="3bef1-148">Выполняет тесты, имя которых содержит `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-148">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="3bef1-149">Выполняет тесты, которые находятся в классе `NUnitNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-149">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="3bef1-150">Выполняет все тесты, за исключением `NUnitNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-150">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="3bef1-151">Выполняет тесты, которые помечены атрибутом `[Category("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-151">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="3bef1-152">Выполняет тесты, которые помечены атрибутом `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-152">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="3bef1-153">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="3bef1-153">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="3bef1-154">Выражение</span><span class="sxs-lookup"><span data-stu-id="3bef1-154">Expression</span></span> | <span data-ttu-id="3bef1-155">Результат</span><span class="sxs-lookup"><span data-stu-id="3bef1-155">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="3bef1-156">Выполняет тесты с `UnitTest1` в `FullyQualifiedName` **или** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-156">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="3bef1-157">Выполняет тесты с `UnitTest1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="3bef1-157">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="3bef1-158">Выполняет тесты с `UnitTest1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA` **или** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="3bef1-158">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
