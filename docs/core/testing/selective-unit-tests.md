---
title: Выполнение выборочных модульных тестов
description: Как использовать выражения фильтра для выполнения выборочных модульных тестов с помощью команды dotnet test в .NET Core.
author: smadala
ms.date: 03/22/2017
ms.openlocfilehash: b9156300587215e68c01c609e298dbc1a2c53d11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "77543512"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="f3aef-103">Выполнение выборочных модульных тестов</span><span class="sxs-lookup"><span data-stu-id="f3aef-103">Running selective unit tests</span></span>

<span data-ttu-id="f3aef-104">Использовать выражения фильтра для выполнения выборочных модульных тестов можно с помощью команды `dotnet test` в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f3aef-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="f3aef-105">В этой статье показано, как отфильтровывать модульные тесты для выполнения.</span><span class="sxs-lookup"><span data-stu-id="f3aef-105">This article demonstrates how to filter which test are run.</span></span> <span data-ttu-id="f3aef-106">В следующих примерах используется `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="f3aef-107">Если вы используете `vstest.console.exe`, замените `--filter` на `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

> [!NOTE]
> <span data-ttu-id="f3aef-108">Чтобы в `*nix` использовать фильтры, содержащие восклицательный знак (!), требуется выполнять экранирование, так как символ `!` зарезервирован.</span><span class="sxs-lookup"><span data-stu-id="f3aef-108">Using filters that include exclamation mark (!) on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="f3aef-109">Например, этот фильтр пропускает все тесты, если пространство имен содержит IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-109">For example, this filter skips all tests if the namespace contains IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span></span>
> <span data-ttu-id="f3aef-110">Обратите внимание на обратную косую черту перед восклицательным знаком.</span><span class="sxs-lookup"><span data-stu-id="f3aef-110">Note the backslash that precedes the exclamation mark.</span></span>

## <a name="mstest"></a><span data-ttu-id="f3aef-111">MSTest</span><span class="sxs-lookup"><span data-stu-id="f3aef-111">MSTest</span></span>

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

| <span data-ttu-id="f3aef-112">Выражение</span><span class="sxs-lookup"><span data-stu-id="f3aef-112">Expression</span></span> | <span data-ttu-id="f3aef-113">Результат</span><span class="sxs-lookup"><span data-stu-id="f3aef-113">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="f3aef-114">Выполняет тесты, `FullyQualifiedName` которых содержит `Method`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-114">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="f3aef-115">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-115">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="f3aef-116">Выполняет тесты, имя которых содержит `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-116">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="f3aef-117">Выполняет тесты, которые находятся в классе `MSTestNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-117">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="f3aef-118">**Примечание.** Значение `ClassName` должно иметь пространство имен, поэтому `ClassName=UnitTest1` не будет работать.</span><span class="sxs-lookup"><span data-stu-id="f3aef-118">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="f3aef-119">Выполняет все тесты, за исключением `MSTestNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-119">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="f3aef-120">Выполняет тесты, которые помечены атрибутом `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-120">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="f3aef-121">Выполняет тесты, которые помечены атрибутом `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-121">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="f3aef-122">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="f3aef-122">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="f3aef-123">Выражение</span><span class="sxs-lookup"><span data-stu-id="f3aef-123">Expression</span></span> | <span data-ttu-id="f3aef-124">Результат</span><span class="sxs-lookup"><span data-stu-id="f3aef-124">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="f3aef-125">Выполняет тесты с `UnitTest1` в `FullyQualifiedName` **или** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-125">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="f3aef-126">Выполняет тесты с `UnitTest1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-126">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="f3aef-127">Выполняет тесты с `FullyQualifiedName` в `UnitTest1` **и** `TestCategory` является `CategoryA` **или** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="f3aef-127">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="f3aef-128">xUnit</span><span class="sxs-lookup"><span data-stu-id="f3aef-128">xUnit</span></span>

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

| <span data-ttu-id="f3aef-129">Выражение</span><span class="sxs-lookup"><span data-stu-id="f3aef-129">Expression</span></span> | <span data-ttu-id="f3aef-130">Результат</span><span class="sxs-lookup"><span data-stu-id="f3aef-130">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="f3aef-131">Выполняет только один тест — `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-131">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="f3aef-132">Выполняет все тесты, за исключением `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-132">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="f3aef-133">Выполняет тесты, отображаемое имя которых содержит `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-133">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="f3aef-134">В примере кода определенные характеристики с ключами `Category` и `Priority` можно использовать для фильтрации.</span><span class="sxs-lookup"><span data-stu-id="f3aef-134">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="f3aef-135">Выражение</span><span class="sxs-lookup"><span data-stu-id="f3aef-135">Expression</span></span> | <span data-ttu-id="f3aef-136">Результат</span><span class="sxs-lookup"><span data-stu-id="f3aef-136">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="f3aef-137">Выполняет тесты, `FullyQualifiedName` которых содержит `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-137">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="f3aef-138">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-138">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="f3aef-139">Выполняет тесты, имеющие `[Trait("Category", "CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-139">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="f3aef-140">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="f3aef-140">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="f3aef-141">Выражение</span><span class="sxs-lookup"><span data-stu-id="f3aef-141">Expression</span></span> | <span data-ttu-id="f3aef-142">Результат</span><span class="sxs-lookup"><span data-stu-id="f3aef-142">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="f3aef-143">Выполняет тесты с `TestClass1` в `FullyQualifiedName` **или** `Category` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-143">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="f3aef-144">Выполняет тесты с `TestClass1` в `FullyQualifiedName` **или** `Category` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-144">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="f3aef-145">Выполняет тесты с `FullyQualifiedName` в `TestClass1` **и** `Category` является `CategoryA` **или** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="f3aef-145">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="f3aef-146">NUnit</span><span class="sxs-lookup"><span data-stu-id="f3aef-146">NUnit</span></span>

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

| <span data-ttu-id="f3aef-147">Выражение</span><span class="sxs-lookup"><span data-stu-id="f3aef-147">Expression</span></span> | <span data-ttu-id="f3aef-148">Результат</span><span class="sxs-lookup"><span data-stu-id="f3aef-148">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="f3aef-149">Выполняет тесты, `FullyQualifiedName` которых содержит `Method`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-149">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="f3aef-150">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-150">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="f3aef-151">Выполняет тесты, имя которых содержит `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-151">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="f3aef-152">Выполняет тесты, которые находятся в классе `NUnitNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-152">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="f3aef-153">Выполняет все тесты, за исключением `NUnitNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-153">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="f3aef-154">Выполняет тесты, которые помечены атрибутом `[Category("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-154">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="f3aef-155">Выполняет тесты, которые помечены атрибутом `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-155">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="f3aef-156">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="f3aef-156">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="f3aef-157">Выражение</span><span class="sxs-lookup"><span data-stu-id="f3aef-157">Expression</span></span> | <span data-ttu-id="f3aef-158">Результат</span><span class="sxs-lookup"><span data-stu-id="f3aef-158">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="f3aef-159">Выполняет тесты с `UnitTest1` в `FullyQualifiedName` **или** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-159">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="f3aef-160">Выполняет тесты с `UnitTest1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="f3aef-160">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="f3aef-161">Выполняет тесты с `FullyQualifiedName` в `UnitTest1` **и** `TestCategory` является `CategoryA` **или** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="f3aef-161">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
