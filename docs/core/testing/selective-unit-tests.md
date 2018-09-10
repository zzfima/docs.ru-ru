---
title: Выполнение выборочных модульных тестов
description: Демонстрация использования выражения фильтра для выполнения выборочных модульных тестов с помощью команды dotnet test.
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.openlocfilehash: 428e31014f5d8d487deb7c4b4317ebcef13c294d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43517224"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="486a0-103">Выполнение выборочных модульных тестов</span><span class="sxs-lookup"><span data-stu-id="486a0-103">Running selective unit tests</span></span>

<span data-ttu-id="486a0-104">В следующих примерах используется `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="486a0-104">The following examples use `dotnet test`.</span></span> <span data-ttu-id="486a0-105">Если вы используете `vstest.console.exe`, замените `--filter ` на `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="486a0-105">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="486a0-106">MSTest</span><span class="sxs-lookup"><span data-stu-id="486a0-106">MSTest</span></span>

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

| <span data-ttu-id="486a0-107">Выражение</span><span class="sxs-lookup"><span data-stu-id="486a0-107">Expression</span></span> | <span data-ttu-id="486a0-108">Результат</span><span class="sxs-lookup"><span data-stu-id="486a0-108">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="486a0-109">Выполняет тесты, `FullyQualifiedName` которых содержит `Method`.</span><span class="sxs-lookup"><span data-stu-id="486a0-109">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="486a0-110">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="486a0-110">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="486a0-111">Выполняет тесты, имя которых содержит `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="486a0-111">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="486a0-112">Выполняет тесты, которые находятся в классе `MSTestNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="486a0-112">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="486a0-113">**Примечание.** Значение `ClassName` должно иметь пространство имен, поэтому `ClassName=UnitTest1` не будет работать.</span><span class="sxs-lookup"><span data-stu-id="486a0-113">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="486a0-114">Выполняет все тесты, за исключением `MSTestNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="486a0-114">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="486a0-115">Выполняет тесты, которые помечены атрибутом `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="486a0-115">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="486a0-116">Выполняет тесты, которые помечены атрибутом `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="486a0-116">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="486a0-117">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="486a0-117">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="486a0-118">Выражение</span><span class="sxs-lookup"><span data-stu-id="486a0-118">Expression</span></span> | <span data-ttu-id="486a0-119">Результат</span><span class="sxs-lookup"><span data-stu-id="486a0-119">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="486a0-120">Выполняет тесты, имеющие `UnitTest1` в `FullyQualifiedName` **или** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="486a0-120">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="486a0-121">Выполняет тесты, имеющие `UnitTest1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="486a0-121">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="486a0-122">Выполняет тесты, в которых либо `FullyQualifiedName` содержит `UnitTest1` **и** `TestCategory` является `CategoryA`, **либо** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="486a0-122">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="486a0-123">xUnit</span><span class="sxs-lookup"><span data-stu-id="486a0-123">xUnit</span></span>

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

| <span data-ttu-id="486a0-124">Выражение</span><span class="sxs-lookup"><span data-stu-id="486a0-124">Expression</span></span> | <span data-ttu-id="486a0-125">Результат</span><span class="sxs-lookup"><span data-stu-id="486a0-125">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="486a0-126">Выполняет только один тест — `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="486a0-126">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="486a0-127">Выполняет все тесты, за исключением `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="486a0-127">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="486a0-128">Выполняет тесты, отображаемое имя которых содержит `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="486a0-128">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="486a0-129">В примере кода определенные характеристики с ключами `Category` и `Priority` можно использовать для фильтрации.</span><span class="sxs-lookup"><span data-stu-id="486a0-129">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="486a0-130">Выражение</span><span class="sxs-lookup"><span data-stu-id="486a0-130">Expression</span></span> | <span data-ttu-id="486a0-131">Результат</span><span class="sxs-lookup"><span data-stu-id="486a0-131">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="486a0-132">Выполняет тесты, `FullyQualifiedName` которых содержит `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="486a0-132">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="486a0-133">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="486a0-133">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="486a0-134">Выполняет тесты, имеющие `[Trait("Category", "CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="486a0-134">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="486a0-135">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="486a0-135">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="486a0-136">Выражение</span><span class="sxs-lookup"><span data-stu-id="486a0-136">Expression</span></span> | <span data-ttu-id="486a0-137">Результат</span><span class="sxs-lookup"><span data-stu-id="486a0-137">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="486a0-138">Выполняет тесты, имеющие `TestClass1` в `FullyQualifiedName` **или** `Category` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="486a0-138">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="486a0-139">Выполняет тесты, имеющие `TestClass1` в `FullyQualifiedName` **или** `Category` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="486a0-139">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="486a0-140">Выполняет тесты, в которых либо `FullyQualifiedName` содержит `TestClass1` **и** `Category` является `CategoryA`, **либо** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="486a0-140">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="486a0-141">NUnit</span><span class="sxs-lookup"><span data-stu-id="486a0-141">NUnit</span></span>

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

| <span data-ttu-id="486a0-142">Выражение</span><span class="sxs-lookup"><span data-stu-id="486a0-142">Expression</span></span> | <span data-ttu-id="486a0-143">Результат</span><span class="sxs-lookup"><span data-stu-id="486a0-143">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="486a0-144">Выполняет тесты, `FullyQualifiedName` которых содержит `Method`.</span><span class="sxs-lookup"><span data-stu-id="486a0-144">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="486a0-145">Доступно в `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="486a0-145">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="486a0-146">Выполняет тесты, имя которых содержит `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="486a0-146">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="486a0-147">Выполняет тесты, которые находятся в классе `NUnitNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="486a0-147">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="486a0-148">Выполняет все тесты, за исключением `NUnitNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="486a0-148">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="486a0-149">Выполняет тесты, которые помечены атрибутом `[Category("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="486a0-149">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="486a0-150">Выполняет тесты, которые помечены атрибутом `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="486a0-150">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="486a0-151">**Использование условных операторов | и &amp;**</span><span class="sxs-lookup"><span data-stu-id="486a0-151">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="486a0-152">Выражение</span><span class="sxs-lookup"><span data-stu-id="486a0-152">Expression</span></span> | <span data-ttu-id="486a0-153">Результат</span><span class="sxs-lookup"><span data-stu-id="486a0-153">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="486a0-154">Выполняет тесты, имеющие `UnitTest1` в `FullyQualifiedName` **или** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="486a0-154">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="486a0-155">Выполняет тесты, имеющие `UnitTest1` в `FullyQualifiedName` **и** `TestCategory` является `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="486a0-155">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="486a0-156">Выполняет тесты, в которых либо `FullyQualifiedName` содержит `UnitTest1` **и** `TestCategory` является `CategoryA`, **либо** `Priority` равно 1.</span><span class="sxs-lookup"><span data-stu-id="486a0-156">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
