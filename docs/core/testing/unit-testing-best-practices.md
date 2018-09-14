---
title: Рекомендации по написанию модульных тестов
description: Ознакомьтесь с рекомендациями по написанию модульных тестов, которые повысят качество и устойчивость кода.
author: jpreese
ms.author: wiwagn
ms.date: 07/28/2018
ms.openlocfilehash: 69fe0cae141d1ed1e1281eecd78bf03e6e8be961
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43527727"
---
# <a name="unit-testing-best-practices"></a><span data-ttu-id="aad9e-103">Рекомендации по модульному тестированию</span><span class="sxs-lookup"><span data-stu-id="aad9e-103">Unit testing best practices</span></span>

<span data-ttu-id="aad9e-104">Автор: [Джон Риз (John Reese)](http://reesespieces.io) с особой благодарностью [Рою Ошерову (Roy Osherove)](http://osherove.com/)</span><span class="sxs-lookup"><span data-stu-id="aad9e-104">By [John Reese](http://reesespieces.io) with special thanks to [Roy Osherove](http://osherove.com/)</span></span>

<span data-ttu-id="aad9e-105">Существует множество преимуществ написания модульных тестов: они помогают с регрессией, предоставляют документацию и способствуют хорошей структуре кода.</span><span class="sxs-lookup"><span data-stu-id="aad9e-105">There are numerous benefits to writing unit tests; they help with regression, provide documentation, and facilitate good design.</span></span> <span data-ttu-id="aad9e-106">Но трудночитаемые и ненадежные модульные тесты могут негативно отразиться на базе кода.</span><span class="sxs-lookup"><span data-stu-id="aad9e-106">However, hard to read and brittle unit tests can wreak havoc on your code base.</span></span>

<span data-ttu-id="aad9e-107">В этом руководстве вы получите некоторые практические рекомендации по написанию модульных тестов, чтобы создавать устойчивые и понятные тесты.</span><span class="sxs-lookup"><span data-stu-id="aad9e-107">In this guide, you'll learn some best practices when writing unit tests to keep your tests resilient and easy to understand.</span></span>

## <a name="why-unit-test"></a><span data-ttu-id="aad9e-108">Почему именно модульные тесты?</span><span class="sxs-lookup"><span data-stu-id="aad9e-108">Why unit test?</span></span>

### <a name="less-time-performing-functional-tests"></a><span data-ttu-id="aad9e-109">Меньше времени на выполнение функциональных тестов</span><span class="sxs-lookup"><span data-stu-id="aad9e-109">Less time performing functional tests</span></span>
<span data-ttu-id="aad9e-110">Функциональные тесты требуют большого количества ресурсов.</span><span class="sxs-lookup"><span data-stu-id="aad9e-110">Functional tests are expensive.</span></span> <span data-ttu-id="aad9e-111">Как правило, приходится открывать приложение и выполнять ряд действий, чтобы проверить ожидаемое поведение.</span><span class="sxs-lookup"><span data-stu-id="aad9e-111">They typically involve opening up the application and performing a series of steps that you (or someone else), must follow in order to validate the expected behavior.</span></span> <span data-ttu-id="aad9e-112">Тест-инженеры не всегда знают, что это за действия, и им приходится обращаться к специалистам в этой области.</span><span class="sxs-lookup"><span data-stu-id="aad9e-112">These steps may not always be known to the tester, which means they will have to reach out to someone more knowledgeable in the area in order to carry out the test.</span></span> <span data-ttu-id="aad9e-113">Само тестирование может занимать несколько секунд, если это обычные изменения, или несколько минут для более масштабных изменений.</span><span class="sxs-lookup"><span data-stu-id="aad9e-113">Testing itself could take seconds for trivial changes, or minutes for larger changes.</span></span> <span data-ttu-id="aad9e-114">Наконец, этот процесс необходимо повторять для каждого изменения, внесенного в систему.</span><span class="sxs-lookup"><span data-stu-id="aad9e-114">Lastly, this process must be repeated for every change that you make in the system.</span></span>

<span data-ttu-id="aad9e-115">Модульные тесты, с другой стороны, занимают миллисекунды, выполняются простым нажатием кнопки и не обязательно требуют знаний о всей системе в целом.</span><span class="sxs-lookup"><span data-stu-id="aad9e-115">Unit tests, on the other hand, take milliseconds, can be run at the press of a button and do not necessarily require any knowledge of the system at large.</span></span> <span data-ttu-id="aad9e-116">Успешность прохождения теста зависит от средства выполнения теста, а не от пользователя.</span><span class="sxs-lookup"><span data-stu-id="aad9e-116">Whether or not the test passes or fails is up to the test runner, not the individual.</span></span>

### <a name="protection-against-regression"></a><span data-ttu-id="aad9e-117">Защита от регрессии</span><span class="sxs-lookup"><span data-stu-id="aad9e-117">Protection against regression</span></span>
<span data-ttu-id="aad9e-118">Дефекты регрессии вводятся при внесении изменений в приложение.</span><span class="sxs-lookup"><span data-stu-id="aad9e-118">Regression defects are defects that are introduced when a change is made to the application.</span></span> <span data-ttu-id="aad9e-119">Довольно часто тест-инженеры тестируют не только новую функцию, но и функции, существовавшие до этого, чтобы проверить, что эти функции по-прежнему работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="aad9e-119">It is common for testers to not only test their new feature but also features that existed beforehand in order to verify that previously implemented features still function as expected.</span></span>

<span data-ttu-id="aad9e-120">С модульным тестированием можно повторно запускать весь набор тестов после каждой сборки или даже после изменения строки кода.</span><span class="sxs-lookup"><span data-stu-id="aad9e-120">With unit testing, it's possible to rerun your entire suite of tests after every build or even after you change a line of code.</span></span> <span data-ttu-id="aad9e-121">Это дает вам уверенность, что ваш новый код не нарушил существующие функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="aad9e-121">Giving you confidence that your new code does not break existing functionality.</span></span>

### <a name="executable-documentation"></a><span data-ttu-id="aad9e-122">Исполняемая документация</span><span class="sxs-lookup"><span data-stu-id="aad9e-122">Executable documentation</span></span>
<span data-ttu-id="aad9e-123">Не всегда очевидно, что делает конкретный метод или как он себя ведет при определенных входных данных.</span><span class="sxs-lookup"><span data-stu-id="aad9e-123">It may not always be obvious what a particular method does or how it behaves given a certain input.</span></span> <span data-ttu-id="aad9e-124">Вы можете спросить себя: как поведет себя метод, если я передам ему пустую строку?</span><span class="sxs-lookup"><span data-stu-id="aad9e-124">You may ask yourself: How does this method behave if I pass it a blank string?</span></span> <span data-ttu-id="aad9e-125">А значение NULL?</span><span class="sxs-lookup"><span data-stu-id="aad9e-125">Null?</span></span>

<span data-ttu-id="aad9e-126">Если у вас есть набор модульных тестов с понятными именами, каждый тест сможет четко объяснить, какими будут выходные данные для определенных входных данных.</span><span class="sxs-lookup"><span data-stu-id="aad9e-126">When you have a suite of well-named unit tests, each test should be able to clearly explain the expected output for a given input.</span></span> <span data-ttu-id="aad9e-127">Кроме того, он сможет проверить, что это действительно работает.</span><span class="sxs-lookup"><span data-stu-id="aad9e-127">In addition, it should be able to verify that it actually works.</span></span>

### <a name="less-coupled-code"></a><span data-ttu-id="aad9e-128">Менее связанный код</span><span class="sxs-lookup"><span data-stu-id="aad9e-128">Less coupled code</span></span>
<span data-ttu-id="aad9e-129">Если код тесно связан, он плохо подходит для модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="aad9e-129">When code is tightly coupled, it can be difficult to unit test.</span></span> <span data-ttu-id="aad9e-130">Без создания модульных тестов для кода это связывание может быть менее очевидным.</span><span class="sxs-lookup"><span data-stu-id="aad9e-130">Without creating unit tests for the code that you're writing, coupling may be less apparent.</span></span>

<span data-ttu-id="aad9e-131">Когда вы пишете тесты для кода, вы естественным образом разделяете его, иначе его будет сложнее тестировать.</span><span class="sxs-lookup"><span data-stu-id="aad9e-131">Writing tests for your code will naturally decouple your code, because it would be more difficult to test otherwise.</span></span>

## <a name="characteristics-of-a-good-unit-test"></a><span data-ttu-id="aad9e-132">Характеристики хорошего модульного теста</span><span class="sxs-lookup"><span data-stu-id="aad9e-132">Characteristics of a good unit test</span></span>
- <span data-ttu-id="aad9e-133">**Быстрый**.</span><span class="sxs-lookup"><span data-stu-id="aad9e-133">**Fast**.</span></span> <span data-ttu-id="aad9e-134">В хорошо разработанных проектах могут быть тысячи модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="aad9e-134">It is not uncommon for mature projects to have thousands of unit tests.</span></span> <span data-ttu-id="aad9e-135">Модульные тесты должны выполняться очень быстро.</span><span class="sxs-lookup"><span data-stu-id="aad9e-135">Unit tests should take very little time to run.</span></span> <span data-ttu-id="aad9e-136">За миллисекунды.</span><span class="sxs-lookup"><span data-stu-id="aad9e-136">Milliseconds.</span></span>
- <span data-ttu-id="aad9e-137">**Изолированный**.</span><span class="sxs-lookup"><span data-stu-id="aad9e-137">**Isolated**.</span></span> <span data-ttu-id="aad9e-138">Модульные тесты являются автономными, могут выполняться изолированно и не имеют зависимостей от внешних факторов, таких как файловая система или база данных.</span><span class="sxs-lookup"><span data-stu-id="aad9e-138">Unit tests are standalone, can be run in isolation, and have no dependencies on any outside factors such as a file system or database.</span></span>
- <span data-ttu-id="aad9e-139">**Повторяемый**.</span><span class="sxs-lookup"><span data-stu-id="aad9e-139">**Repeatable**.</span></span> <span data-ttu-id="aad9e-140">Запуски модульного теста должны иметь согласованные результаты, то есть всегда возвращать одинаковый результат, если вы не вносите никаких изменений между запусками.</span><span class="sxs-lookup"><span data-stu-id="aad9e-140">Running a unit test should be consistent with its results, that is, it always returns the same result if you do not change anything in between runs.</span></span>
- <span data-ttu-id="aad9e-141">**Самопроверяющий**.</span><span class="sxs-lookup"><span data-stu-id="aad9e-141">**Self-Checking**.</span></span> <span data-ttu-id="aad9e-142">Тест должен автоматически определять, пройден он или нет, без участия пользователя.</span><span class="sxs-lookup"><span data-stu-id="aad9e-142">The test should be able to automatically detect if it passed or failed without any human interaction.</span></span>
- <span data-ttu-id="aad9e-143">**Уместный**.</span><span class="sxs-lookup"><span data-stu-id="aad9e-143">**Timely**.</span></span> <span data-ttu-id="aad9e-144">Время на написание модульного теста должно соответствовать объему тестируемого кода.</span><span class="sxs-lookup"><span data-stu-id="aad9e-144">A unit test should not take a disproportionally long time to write compared to the code being tested.</span></span> <span data-ttu-id="aad9e-145">Если вам кажется, что тестирование кода занимает слишком много времени по сравнению с написанием кода, продумайте структуру, более подходящую для тестирования.</span><span class="sxs-lookup"><span data-stu-id="aad9e-145">If you find testing the code taking a large amount of time compared to writing the code, consider a design that is more testable.</span></span>

## <a name="lets-speak-the-same-language"></a><span data-ttu-id="aad9e-146">Определимся с терминами</span><span class="sxs-lookup"><span data-stu-id="aad9e-146">Let's speak the same language</span></span>
<span data-ttu-id="aad9e-147">К сожалению, термин *макет* по отношению к тестированию часто употребляется неправильно.</span><span class="sxs-lookup"><span data-stu-id="aad9e-147">The term *mock* is unfortunately very misused when talking about testing.</span></span> <span data-ttu-id="aad9e-148">Следующий код определяет самые распространенные типы *заполнителей* при написании модульных тестов:</span><span class="sxs-lookup"><span data-stu-id="aad9e-148">The following defines the most common types of *fakes* when writing unit tests:</span></span>

<span data-ttu-id="aad9e-149">*Заполнитель* — это общий термин, который можно использовать для описания заглушки или макета объекта.</span><span class="sxs-lookup"><span data-stu-id="aad9e-149">*Fake* - A fake is a generic term which can be used to describe either a stub or a mock object.</span></span> <span data-ttu-id="aad9e-150">Использование заглушки или макета зависит от контекста.</span><span class="sxs-lookup"><span data-stu-id="aad9e-150">Whether it is a stub or a mock depends on the context in which it's used.</span></span> <span data-ttu-id="aad9e-151">Иными словами, заполнитель может быть заглушкой или макетом.</span><span class="sxs-lookup"><span data-stu-id="aad9e-151">So in other words, a fake can be a stub or a mock.</span></span>

<span data-ttu-id="aad9e-152">*Макет*. Макет объекта — это объект-заполнитель в системе, который решает, пройден ли модульный тест.</span><span class="sxs-lookup"><span data-stu-id="aad9e-152">*Mock* - A mock object is a fake object in the system that decides whether or not a unit test has passed or failed.</span></span> <span data-ttu-id="aad9e-153">Макет начинает существование как заполнитель, пока по нему не будет проведена проверка.</span><span class="sxs-lookup"><span data-stu-id="aad9e-153">A mock starts out as a Fake until it is asserted against.</span></span>

<span data-ttu-id="aad9e-154">*Заглушка* — это управляемая замена существующей зависимости (или участника) в системе.</span><span class="sxs-lookup"><span data-stu-id="aad9e-154">*Stub* - A stub is a controllable replacement for an existing dependency (or collaborator) in the system.</span></span> <span data-ttu-id="aad9e-155">С помощью заглушки можно протестировать код, не задействовав зависимость напрямую.</span><span class="sxs-lookup"><span data-stu-id="aad9e-155">By using a stub, you can test your code without dealing with the dependency directly.</span></span> <span data-ttu-id="aad9e-156">По умолчанию заполнитель выступает как заглушка.</span><span class="sxs-lookup"><span data-stu-id="aad9e-156">By default, a fake starts out as a stub.</span></span>

<span data-ttu-id="aad9e-157">Рассмотрим следующий фрагмент кода:</span><span class="sxs-lookup"><span data-stu-id="aad9e-157">Consider the following code snippet:</span></span>

```csharp
var mockOrder = new MockOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

<span data-ttu-id="aad9e-158">Это будет пример заглушки, которая будет называться макетом.</span><span class="sxs-lookup"><span data-stu-id="aad9e-158">This would be an example of stub being referred to as a mock.</span></span> <span data-ttu-id="aad9e-159">В данном случае это заглушка.</span><span class="sxs-lookup"><span data-stu-id="aad9e-159">In this case, it is a stub.</span></span> <span data-ttu-id="aad9e-160">Вы передаете Order, чтобы создать экземпляр `Purchase` (тестируемая система).</span><span class="sxs-lookup"><span data-stu-id="aad9e-160">You're just passing in the Order as a means to be able to instantiate `Purchase` (the system under test).</span></span> <span data-ttu-id="aad9e-161">Имя `MockOrder` вводит в заблуждение, поскольку Order не является макетом.</span><span class="sxs-lookup"><span data-stu-id="aad9e-161">The name `MockOrder` is also very misleading because again, the order is not a mock.</span></span>

<span data-ttu-id="aad9e-162">Лучше было бы так:</span><span class="sxs-lookup"><span data-stu-id="aad9e-162">A better approach would be</span></span>

```csharp
var stubOrder = new FakeOrder();
var purchase = new Purchase(stubOrder);

purchase.ValidateOrders();

Assert.True(purchase.CanBeShipped);
```

<span data-ttu-id="aad9e-163">Если переименовать класс в `FakeOrder`, он будет более универсальным и его можно будет использовать как макет или как заглушку.</span><span class="sxs-lookup"><span data-stu-id="aad9e-163">By renaming the class to `FakeOrder`, you've made the class a lot more generic, the class can be used as a mock or a stub.</span></span> <span data-ttu-id="aad9e-164">Это зависит от тестового случая.</span><span class="sxs-lookup"><span data-stu-id="aad9e-164">Whichever is better for the test case.</span></span> <span data-ttu-id="aad9e-165">В приведенном выше примере `FakeOrder` используется в качестве заглушки.</span><span class="sxs-lookup"><span data-stu-id="aad9e-165">In the above example, `FakeOrder` is used as a stub.</span></span> <span data-ttu-id="aad9e-166">Вы никак не используете `FakeOrder` во время проверки.</span><span class="sxs-lookup"><span data-stu-id="aad9e-166">You're not using the `FakeOrder` in any shape or form during the assert.</span></span> <span data-ttu-id="aad9e-167">`FakeOrder` был передан в класс `Purchase` для удовлетворения требований конструктора.</span><span class="sxs-lookup"><span data-stu-id="aad9e-167">`FakeOrder` was just passed into the `Purchase` class to satisfy the requirements of the constructor.</span></span>

<span data-ttu-id="aad9e-168">Чтобы использовать его как макет, можно сделать нечто подобное:</span><span class="sxs-lookup"><span data-stu-id="aad9e-168">To use it as a Mock, you could do something like this</span></span>

```csharp
var mockOrder = new FakeOrder();
var purchase = new Purchase(mockOrder);

purchase.ValidateOrders();

Assert.True(mockOrder.Validated);
```

<span data-ttu-id="aad9e-169">В этом случае проверяется свойство заполнителя (выполняется проверка по нему), поэтому в приведенном выше фрагменте кода `mockOrder` является макетом.</span><span class="sxs-lookup"><span data-stu-id="aad9e-169">In this case, you are checking a property on the Fake (asserting against it), so in the above code snippet, the `mockOrder` is a Mock.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aad9e-170">Очень важно правильно разобраться в терминологии.</span><span class="sxs-lookup"><span data-stu-id="aad9e-170">It's important to get this terminology correct.</span></span> <span data-ttu-id="aad9e-171">Если вы будете называть заглушки макетами, другие разработчики не поймут ваших намерений.</span><span class="sxs-lookup"><span data-stu-id="aad9e-171">If you call your stubs "mocks", other developers are going to make false assumptions about your intent.</span></span>

<span data-ttu-id="aad9e-172">В первую очередь следует помнить, что макеты отличаются от заглушек тем, что вы выполняете проверку по макету объекта, но не выполняете проверку по заглушке.</span><span class="sxs-lookup"><span data-stu-id="aad9e-172">The main thing to remember about mocks versus stubs is that mocks are just like stubs, but you assert against the mock object, whereas you do not assert against a stub.</span></span>

## <a name="best-practices"></a><span data-ttu-id="aad9e-173">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="aad9e-173">Best practices</span></span>

### <a name="naming-your-tests"></a><span data-ttu-id="aad9e-174">Выбор имен для тестов</span><span class="sxs-lookup"><span data-stu-id="aad9e-174">Naming your tests</span></span>
<span data-ttu-id="aad9e-175">Имя теста должно состоять из трех частей:</span><span class="sxs-lookup"><span data-stu-id="aad9e-175">The name of your test should consist of three parts:</span></span>
- <span data-ttu-id="aad9e-176">имя тестируемого метода;</span><span class="sxs-lookup"><span data-stu-id="aad9e-176">The name of the method being tested.</span></span>
- <span data-ttu-id="aad9e-177">сценарий, в котором выполняется тестирование;</span><span class="sxs-lookup"><span data-stu-id="aad9e-177">The scenario under which it's being tested.</span></span>
- <span data-ttu-id="aad9e-178">ожидаемое поведение при вызове сценария.</span><span class="sxs-lookup"><span data-stu-id="aad9e-178">The expected behavior when the scenario is invoked.</span></span>

#### <a name="why"></a><span data-ttu-id="aad9e-179">Почему?</span><span class="sxs-lookup"><span data-stu-id="aad9e-179">Why?</span></span>
- <span data-ttu-id="aad9e-180">Стандарты именования важны, так как они выражают намерение теста.</span><span class="sxs-lookup"><span data-stu-id="aad9e-180">Naming standards are important because they explicitly express the intent of the test.</span></span>

<span data-ttu-id="aad9e-181">Тесты не просто проверяют работоспособность кода — они также предоставляют документацию.</span><span class="sxs-lookup"><span data-stu-id="aad9e-181">Tests are more than just making sure your code works, they also provide documentation.</span></span> <span data-ttu-id="aad9e-182">Просто посмотрев на набор модульных тестов, вы должны определить поведение кода, не глядя на сам код.</span><span class="sxs-lookup"><span data-stu-id="aad9e-182">Just by looking at the suite of unit tests, you should be able to infer the behavior of your code without even looking at the code itself.</span></span> <span data-ttu-id="aad9e-183">Кроме того, если тест не пройден, вы сразу увидите, какие сценарии не соответствуют вашим ожиданиям.</span><span class="sxs-lookup"><span data-stu-id="aad9e-183">Additionally, when tests fail, you can see exactly which scenarios do not meet your expectations.</span></span>

#### <a name="bad"></a><span data-ttu-id="aad9e-184">Плохо:</span><span class="sxs-lookup"><span data-stu-id="aad9e-184">Bad:</span></span>
[!code-csharp[BeforeNaming](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeNaming)]

#### <a name="better"></a><span data-ttu-id="aad9e-185">Лучше:</span><span class="sxs-lookup"><span data-stu-id="aad9e-185">Better:</span></span>
[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="arranging-your-tests"></a><span data-ttu-id="aad9e-186">Упорядочивание тестов</span><span class="sxs-lookup"><span data-stu-id="aad9e-186">Arranging your tests</span></span>
<span data-ttu-id="aad9e-187">**Упорядочивайте, действуйте, проверяйте** — это общий шаблон для модульного тестирования.</span><span class="sxs-lookup"><span data-stu-id="aad9e-187">**Arrange, Act, Assert** is a common pattern when unit testing.</span></span> <span data-ttu-id="aad9e-188">Как и предполагает название, он состоит из трех элементов.</span><span class="sxs-lookup"><span data-stu-id="aad9e-188">As the name implies, it consists of three main actions:</span></span>
- <span data-ttu-id="aad9e-189">*Упорядочивайте* объекты, создавая и настраивая их по необходимости.</span><span class="sxs-lookup"><span data-stu-id="aad9e-189">*Arrange* your objects, creating and setting them up as necessary.</span></span>
- <span data-ttu-id="aad9e-190">*Действуйте*, работая с объектами.</span><span class="sxs-lookup"><span data-stu-id="aad9e-190">*Act* on an object.</span></span>
- <span data-ttu-id="aad9e-191">*Проверяйте*, что все выполняется, как ожидалось.</span><span class="sxs-lookup"><span data-stu-id="aad9e-191">*Assert* that something is as expected.</span></span>

#### <a name="why"></a><span data-ttu-id="aad9e-192">Почему?</span><span class="sxs-lookup"><span data-stu-id="aad9e-192">Why?</span></span>
- <span data-ttu-id="aad9e-193">Объект тестирования четко отделяется от этапов *упорядочивания* и *проверки*.</span><span class="sxs-lookup"><span data-stu-id="aad9e-193">Clearly separates what is being tested from the *arrange* and *assert* steps.</span></span>
- <span data-ttu-id="aad9e-194">Меньше вероятности перепутать проверочные утверждения с кодом действия.</span><span class="sxs-lookup"><span data-stu-id="aad9e-194">Less chance to intermix assertions with "Act" code.</span></span>

<span data-ttu-id="aad9e-195">Удобочитаемость является одним из наиболее важных аспектов при написании тестов.</span><span class="sxs-lookup"><span data-stu-id="aad9e-195">Readability is one of the most important aspects when writing a test.</span></span> <span data-ttu-id="aad9e-196">Четкое разделение каждого из этих действий в тесте подчеркивает зависимости, необходимые для вызова кода, указывает, как вызывается ваш код и что вы пытаетесь проверить.</span><span class="sxs-lookup"><span data-stu-id="aad9e-196">Separating each of these actions within the test clearly highlight the dependencies required to call your code, how your code is being called, and what you are trying to assert.</span></span> <span data-ttu-id="aad9e-197">Хотя некоторые шаги можно объединить и уменьшить размер теста, основной целью является удобочитаемость теста.</span><span class="sxs-lookup"><span data-stu-id="aad9e-197">While it may be possible to combine some steps and reduce the size of your test, the primary goal is to make the test as readable as possible.</span></span>

#### <a name="bad"></a><span data-ttu-id="aad9e-198">Плохо:</span><span class="sxs-lookup"><span data-stu-id="aad9e-198">Bad:</span></span>
[!code-csharp[BeforeArranging](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeArranging)]

#### <a name="better"></a><span data-ttu-id="aad9e-199">Лучше:</span><span class="sxs-lookup"><span data-stu-id="aad9e-199">Better:</span></span>
[!code-csharp[AfterArranging](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterArranging)]

### <a name="write-minimally-passing-tests"></a><span data-ttu-id="aad9e-200">Пишите минималистичные тесты</span><span class="sxs-lookup"><span data-stu-id="aad9e-200">Write minimally passing tests</span></span>
<span data-ttu-id="aad9e-201">Входные данные для модульного теста должны быть как можно проще, чтобы проверить поведение, которое вы тестируете в данный момент.</span><span class="sxs-lookup"><span data-stu-id="aad9e-201">The input to be used in a unit test should be the simplest possible in order to verify the behavior that you are currently testing.</span></span>

#### <a name="why"></a><span data-ttu-id="aad9e-202">Почему?</span><span class="sxs-lookup"><span data-stu-id="aad9e-202">Why?</span></span>
- <span data-ttu-id="aad9e-203">Тесты становятся более устойчивыми к будущим изменениям в базе кода.</span><span class="sxs-lookup"><span data-stu-id="aad9e-203">Tests become more resilient to future changes in the codebase.</span></span>
- <span data-ttu-id="aad9e-204">Ближе к тестированию поведения по сравнению с реализацией.</span><span class="sxs-lookup"><span data-stu-id="aad9e-204">Closer to testing behavior over implementation.</span></span>

<span data-ttu-id="aad9e-205">Тесты, которые включают больше информации, чем требуется для прохождения, могут содержать больше ошибок и затруднять понимание намерения.</span><span class="sxs-lookup"><span data-stu-id="aad9e-205">Tests that include more information than required to pass the test have a higher chance of introducing errors into the test and can make the intent of the test less clear.</span></span> <span data-ttu-id="aad9e-206">При написании тестов необходимо сосредоточиться на поведении.</span><span class="sxs-lookup"><span data-stu-id="aad9e-206">When writing tests you want to focus on the behavior.</span></span> <span data-ttu-id="aad9e-207">Установка дополнительных свойств для моделей или использование ненулевых значений, когда это не требуется, только затрудняет проверку.</span><span class="sxs-lookup"><span data-stu-id="aad9e-207">Setting extra properties on models or using non-zero values when not required, only detracts from what you are trying to prove.</span></span>

#### <a name="bad"></a><span data-ttu-id="aad9e-208">Плохо:</span><span class="sxs-lookup"><span data-stu-id="aad9e-208">Bad:</span></span>
[!code-csharp[BeforeMinimallyPassing](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeMinimallyPassing)]

#### <a name="better"></a><span data-ttu-id="aad9e-209">Лучше:</span><span class="sxs-lookup"><span data-stu-id="aad9e-209">Better:</span></span>
[!code-csharp[AfterNamingAndMinimallyPassing](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterNamingAndMinimallyPassing)]

### <a name="avoid-magic-strings"></a><span data-ttu-id="aad9e-210">Избегайте "магических" строк</span><span class="sxs-lookup"><span data-stu-id="aad9e-210">Avoid magic strings</span></span>
<span data-ttu-id="aad9e-211">Именование переменных в модульных тестах так же важно, как именование переменных в рабочем коде, если не важнее.</span><span class="sxs-lookup"><span data-stu-id="aad9e-211">Naming variables in unit tests is as important, if not more important, than naming variables in production code.</span></span> <span data-ttu-id="aad9e-212">Модульные тесты не должны содержать "магических" строк.</span><span class="sxs-lookup"><span data-stu-id="aad9e-212">Unit tests should not contain magic strings.</span></span>

#### <a name="why"></a><span data-ttu-id="aad9e-213">Почему?</span><span class="sxs-lookup"><span data-stu-id="aad9e-213">Why?</span></span>
- <span data-ttu-id="aad9e-214">Избавит читателя теста от необходимости проверять рабочий код, чтобы выяснить, что делает значение особенным.</span><span class="sxs-lookup"><span data-stu-id="aad9e-214">Prevents the need for the reader of the test to inspect the production code in order to figure out what makes the value special.</span></span>
- <span data-ttu-id="aad9e-215">Явно показывает, что вы пытаетесь *проверить*, а не *выполнить*.</span><span class="sxs-lookup"><span data-stu-id="aad9e-215">Explicitly shows what you're trying to *prove* rather than trying to *accomplish*.</span></span>

<span data-ttu-id="aad9e-216">"Магические" строки могут запутать читателя тестов.</span><span class="sxs-lookup"><span data-stu-id="aad9e-216">Magic strings can cause confusion to the reader of your tests.</span></span> <span data-ttu-id="aad9e-217">Если строка выглядит необычно, у него может возникнуть вопрос, почему было выбрано определенное значение для параметра или возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="aad9e-217">If a string looks out of the ordinary, they may wonder why a certain value was chosen for a parameter or return value.</span></span> <span data-ttu-id="aad9e-218">И ему придется рассматривать детали реализации, вместо того чтобы сосредоточиться на тесте.</span><span class="sxs-lookup"><span data-stu-id="aad9e-218">This may lead them to take a closer look at the implementation details, rather than focus on the test.</span></span>

> [!TIP] 
> <span data-ttu-id="aad9e-219">При написании тестов старайтесь как можно яснее выразить свое намерение.</span><span class="sxs-lookup"><span data-stu-id="aad9e-219">When writing tests, you should aim to express as much intent as possible.</span></span> <span data-ttu-id="aad9e-220">В случае "магических" строк рекомендуется присваивать эти значения константам.</span><span class="sxs-lookup"><span data-stu-id="aad9e-220">In the case of magic strings, a good approach is to assign these values to constants.</span></span>

#### <a name="bad"></a><span data-ttu-id="aad9e-221">Плохо:</span><span class="sxs-lookup"><span data-stu-id="aad9e-221">Bad:</span></span>
[!code-csharp[BeforeMagicString](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeMagicString)]

#### <a name="better"></a><span data-ttu-id="aad9e-222">Лучше:</span><span class="sxs-lookup"><span data-stu-id="aad9e-222">Better:</span></span>
[!code-csharp[AfterMagicString](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterMagicString)]

### <a name="avoid-logic-in-tests"></a><span data-ttu-id="aad9e-223">Избегайте логики в тестах</span><span class="sxs-lookup"><span data-stu-id="aad9e-223">Avoid logic in tests</span></span>
<span data-ttu-id="aad9e-224">При написании модульных тестов избегайте объединения строк вручную и логических условий, таких как `if`, `while`, `for`, `switch` и т. д.</span><span class="sxs-lookup"><span data-stu-id="aad9e-224">When writing your unit tests avoid manual string concatenation and logical conditions such as `if`, `while`, `for`, `switch`, etc.</span></span>

#### <a name="why"></a><span data-ttu-id="aad9e-225">Почему?</span><span class="sxs-lookup"><span data-stu-id="aad9e-225">Why?</span></span>
- <span data-ttu-id="aad9e-226">Меньше шансов внедрить ошибку в тесты.</span><span class="sxs-lookup"><span data-stu-id="aad9e-226">Less chance to introduce a bug inside of your tests.</span></span>
- <span data-ttu-id="aad9e-227">Направленность на конечный результат, а не на детали реализации.</span><span class="sxs-lookup"><span data-stu-id="aad9e-227">Focus on the end result, rather than implementation details.</span></span>

<span data-ttu-id="aad9e-228">При введении логики в набор тестов вероятность появления ошибок значительно возрастает.</span><span class="sxs-lookup"><span data-stu-id="aad9e-228">When you introduce logic into your test suite, the chance of introducing a bug into it increases dramatically.</span></span> <span data-ttu-id="aad9e-229">Меньше всего вам нужна ошибка в наборе тестов.</span><span class="sxs-lookup"><span data-stu-id="aad9e-229">The last place that you want to find a bug is within your test suite.</span></span> <span data-ttu-id="aad9e-230">Вы должны быть уверены, что тесты работают. Иначе вы не сможете им доверять.</span><span class="sxs-lookup"><span data-stu-id="aad9e-230">You should have a high level of confidence that your tests work, otherwise, you will not trust them.</span></span> <span data-ttu-id="aad9e-231">Если вы не доверяете тесту, он бесполезен.</span><span class="sxs-lookup"><span data-stu-id="aad9e-231">Tests that you do not trust, do not provide any value.</span></span> <span data-ttu-id="aad9e-232">Если тест не пройден, вы должны знать, что с кодом действительно что-то не так и это нельзя игнорировать.</span><span class="sxs-lookup"><span data-stu-id="aad9e-232">When a test fails, you want to have a sense that something is actually wrong with your code and that it cannot be ignored.</span></span>

> [!TIP]
> <span data-ttu-id="aad9e-233">Если логика в тесте неизбежна, рекомендуется разбить тест на несколько тестов.</span><span class="sxs-lookup"><span data-stu-id="aad9e-233">If logic in your test seems unavoidable, consider splitting the test up into two or more different tests.</span></span>

#### <a name="bad"></a><span data-ttu-id="aad9e-234">Плохо:</span><span class="sxs-lookup"><span data-stu-id="aad9e-234">Bad:</span></span>
[!code-csharp[LogicInTests](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#LogicInTests)]

#### <a name="better"></a><span data-ttu-id="aad9e-235">Лучше:</span><span class="sxs-lookup"><span data-stu-id="aad9e-235">Better:</span></span>
[!code-csharp[AfterTestLogic](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterTestLogic)]

### <a name="prefer-helper-methods-to-setup-and-teardown"></a><span data-ttu-id="aad9e-236">Выбирайте вспомогательные методы вместо установки и удаления</span><span class="sxs-lookup"><span data-stu-id="aad9e-236">Prefer helper methods to setup and teardown</span></span>
<span data-ttu-id="aad9e-237">Если вам требуется аналогичный объект или состояние для тестов, лучше используйте вспомогательный метод, чем атрибуты установки и удаления, если они существуют.</span><span class="sxs-lookup"><span data-stu-id="aad9e-237">If you require a similar object or state for your tests, prefer a helper method than leveraging Setup and Teardown attributes if they exist.</span></span>

#### <a name="why"></a><span data-ttu-id="aad9e-238">Почему?</span><span class="sxs-lookup"><span data-stu-id="aad9e-238">Why?</span></span>
- <span data-ttu-id="aad9e-239">Меньше путаницы при чтении тестов, так как весь код виден в каждом тесте.</span><span class="sxs-lookup"><span data-stu-id="aad9e-239">Less confusion when reading the tests since all of the code is visible from within each test.</span></span>
- <span data-ttu-id="aad9e-240">Меньше шансов настроить слишком много или слишком мало для определенного теста.</span><span class="sxs-lookup"><span data-stu-id="aad9e-240">Less chance of setting up too much or too little for the given test.</span></span>
- <span data-ttu-id="aad9e-241">Меньше шансов совместного использования состояния несколькими тестами, что приводит к нежелательным зависимостям между ними.</span><span class="sxs-lookup"><span data-stu-id="aad9e-241">Less chance of sharing state between tests which creates unwanted dependencies between them.</span></span>

<span data-ttu-id="aad9e-242">В модульном тестировании `Setup` вызывается до всех модульных тестов в наборе.</span><span class="sxs-lookup"><span data-stu-id="aad9e-242">In unit testing frameworks, `Setup` is called before each and every unit test within your test suite.</span></span> <span data-ttu-id="aad9e-243">Хотя некоторые считают это полезным инструментом, в конечном итоге тесты сложно воспринимать.</span><span class="sxs-lookup"><span data-stu-id="aad9e-243">While some may see this as a useful tool, it generally ends up leading to bloated and hard to read tests.</span></span> <span data-ttu-id="aad9e-244">Каждый тест обычно имеет различные требования для запуска.</span><span class="sxs-lookup"><span data-stu-id="aad9e-244">Each test will generally have different requirements in order to get the test up and running.</span></span> <span data-ttu-id="aad9e-245">К сожалению, `Setup` заставляет вас использовать одинаковые требования для всех тестов.</span><span class="sxs-lookup"><span data-stu-id="aad9e-245">Unfortunately, `Setup` forces you to use the exact same requirements for each test.</span></span>

> [!NOTE] 
> <span data-ttu-id="aad9e-246">В xUnit удалены SetUp и TearDown в версии 2.x.</span><span class="sxs-lookup"><span data-stu-id="aad9e-246">xUnit has removed both SetUp and TearDown as of version 2.x</span></span>

#### <a name="bad"></a><span data-ttu-id="aad9e-247">Плохо:</span><span class="sxs-lookup"><span data-stu-id="aad9e-247">Bad:</span></span>
[!code-csharp[BeforeSetup](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeSetup)]

```csharp
// more tests...
```

[!code-csharp[BeforeHelperMethod](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeHelperMethod)]

#### <a name="better"></a><span data-ttu-id="aad9e-248">Лучше:</span><span class="sxs-lookup"><span data-stu-id="aad9e-248">Better:</span></span>
[!code-csharp[AfterHelperMethod](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterHelperMethod)]

```csharp
// more tests...
```

[!code-csharp[AfterSetup](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterSetup)]

### <a name="avoid-multiple-asserts"></a><span data-ttu-id="aad9e-249">Избегайте нескольких проверочных утверждений</span><span class="sxs-lookup"><span data-stu-id="aad9e-249">Avoid multiple asserts</span></span>
<span data-ttu-id="aad9e-250">При написании тестов попробуйте включить только одно проверочное утверждение в каждый тест.</span><span class="sxs-lookup"><span data-stu-id="aad9e-250">When writing your tests, try to only include one Assert per test.</span></span> <span data-ttu-id="aad9e-251">Общие подходы к использованию только одного проверочного утверждения включают следующее.</span><span class="sxs-lookup"><span data-stu-id="aad9e-251">Common approaches to using only one assert include:</span></span>
- <span data-ttu-id="aad9e-252">Создание отдельного теста для каждого проверочного утверждения.</span><span class="sxs-lookup"><span data-stu-id="aad9e-252">Create a separate test for each assert.</span></span>
- <span data-ttu-id="aad9e-253">Использование параметризованных тестов.</span><span class="sxs-lookup"><span data-stu-id="aad9e-253">Use parameterized tests.</span></span>

#### <a name="why"></a><span data-ttu-id="aad9e-254">Почему?</span><span class="sxs-lookup"><span data-stu-id="aad9e-254">Why?</span></span>
- <span data-ttu-id="aad9e-255">Если одно проверочное утверждение завершится неудачей, последующие не будут вычисляться.</span><span class="sxs-lookup"><span data-stu-id="aad9e-255">If one Assert fails, the subsequent Asserts will not be evaluated.</span></span>
- <span data-ttu-id="aad9e-256">Гарантирует, что вы не будете проверять несколько случаев в тестах.</span><span class="sxs-lookup"><span data-stu-id="aad9e-256">Ensures you are not asserting multiple cases in your tests.</span></span>
- <span data-ttu-id="aad9e-257">Предоставляет полную картину о том, почему тесты завершаются неудачей.</span><span class="sxs-lookup"><span data-stu-id="aad9e-257">Gives you the entire picture as to why your tests are failing.</span></span> 

<span data-ttu-id="aad9e-258">При использовании нескольких проверочных утверждений в тестовом случае у вас нет гарантии, что все утверждения будут выполняться.</span><span class="sxs-lookup"><span data-stu-id="aad9e-258">When introducing multiple asserts into a test case, it is not guaranteed that all of the asserts will be executed.</span></span> <span data-ttu-id="aad9e-259">В большинстве платформ модульного тестирования, когда одно утверждение в модульном тесте завершается неудачей, все последующие тесты считаются непройденными.</span><span class="sxs-lookup"><span data-stu-id="aad9e-259">In most unit testing frameworks, once an assertion fails in a unit test, the proceeding tests are automatically considered to be failing.</span></span> <span data-ttu-id="aad9e-260">Это может вызывать путаницу, так как действующие функции будут казаться неработоспособными.</span><span class="sxs-lookup"><span data-stu-id="aad9e-260">This can be confusing as functionality that is actually working, will be shown as failing.</span></span>

> [!NOTE]
> <span data-ttu-id="aad9e-261">Общее исключение из этого правила — проверка объекта.</span><span class="sxs-lookup"><span data-stu-id="aad9e-261">A common exception to this rule is when asserting against an object.</span></span> <span data-ttu-id="aad9e-262">В этом случае обычно допустимо иметь несколько утверждений для каждого свойства, чтобы убедиться, что объект находится в ожидаемом состоянии.</span><span class="sxs-lookup"><span data-stu-id="aad9e-262">In this case, it is generally acceptable to have multiple asserts against each property to ensure the object is in the state that you expect it to be in.</span></span>

#### <a name="bad"></a><span data-ttu-id="aad9e-263">Плохо:</span><span class="sxs-lookup"><span data-stu-id="aad9e-263">Bad:</span></span>
[!code-csharp[BeforeMultipleAsserts](../../../samples/csharp/unit-testing-best-practices/before/StringCalculatorTests.cs#BeforeMultipleAsserts)]

#### <a name="better"></a><span data-ttu-id="aad9e-264">Лучше:</span><span class="sxs-lookup"><span data-stu-id="aad9e-264">Better:</span></span>
[!code-csharp[AfterMultipleAsserts](../../../samples/csharp/unit-testing-best-practices/after/StringCalculatorTests.cs#AfterMultipleAsserts)]

### <a name="validate-private-methods-by-unit-testing-public-methods"></a><span data-ttu-id="aad9e-265">Проверяйте закрытые методы путем модульного тестирования открытых методов</span><span class="sxs-lookup"><span data-stu-id="aad9e-265">Validate private methods by unit testing public methods</span></span>
<span data-ttu-id="aad9e-266">В большинстве случаев вам не понадобится тестировать закрытые методы.</span><span class="sxs-lookup"><span data-stu-id="aad9e-266">In most cases, there should not be a need to test a private method.</span></span> <span data-ttu-id="aad9e-267">Закрытые методы относятся к тонкостям реализации.</span><span class="sxs-lookup"><span data-stu-id="aad9e-267">Private methods are an implementation detail.</span></span> <span data-ttu-id="aad9e-268">Подумайте об этом так: закрытые методы никогда не существуют в изоляции.</span><span class="sxs-lookup"><span data-stu-id="aad9e-268">You can think of it this way: private methods never exist in isolation.</span></span> <span data-ttu-id="aad9e-269">Рано или поздно у вас будет открытый метод, вызывающий закрытый метод в рамках его реализации.</span><span class="sxs-lookup"><span data-stu-id="aad9e-269">At some point, there is going to be a public facing method that calls the private method as part of its implementation.</span></span> <span data-ttu-id="aad9e-270">Вам следует думать о конечном результате открытого метода, который вызывает закрытый метод.</span><span class="sxs-lookup"><span data-stu-id="aad9e-270">What you should care about is the end result of the public method that calls into the private one.</span></span> 

<span data-ttu-id="aad9e-271">Рассмотрим следующий случай.</span><span class="sxs-lookup"><span data-stu-id="aad9e-271">Consider the following case</span></span>

```csharp
public string ParseLogLine(string input)
{
    var sanitizedInput = trimInput(input);
    return sanitizedInput;
}

private string trimInput(string input)
{
    return input.Trim();
}
```

<span data-ttu-id="aad9e-272">Возможно, в первую очередь вам захочется написать тест для `trimInput`, поскольку вы хотите убедиться, что метод работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="aad9e-272">Your first reaction may be to start writing a test for `trimInput` because you want to make sure that the method is working as expected.</span></span> <span data-ttu-id="aad9e-273">Но вполне возможно, что `ParseLogLine` манипулирует `sanitizedInput` неожиданным для вас образом и тестирование `trimInput` окажется бесполезным.</span><span class="sxs-lookup"><span data-stu-id="aad9e-273">However, it is entirely possible that `ParseLogLine` manipulates `sanitizedInput` in such a way that you do not expect, rendering a test against `trimInput` useless.</span></span> 

<span data-ttu-id="aad9e-274">Настоящий тест нужно провести для открытого метода `ParseLogLine`, потому что в конечном итоге для вас важен именно он.</span><span class="sxs-lookup"><span data-stu-id="aad9e-274">The real test should be done against the public facing method `ParseLogLine` because that is what you should ultimately care about.</span></span> 

```csharp
public void ParseLogLine_ByDefault_ReturnsTrimmedResult()
{
    var parser = new Parser();

    var result = parser.ParseLogLine(" a ");

    Assert.Equals("a", result);
}
```

<span data-ttu-id="aad9e-275">С этой точки зрения, если вы видите закрытый метод, найдите открытый метод и напишите тесты для него.</span><span class="sxs-lookup"><span data-stu-id="aad9e-275">With this viewpoint, if you see a private method, find the public method and write your tests against that method.</span></span> <span data-ttu-id="aad9e-276">Тот факт, что закрытый метод возвращает ожидаемый результат, вовсе не означает, что система, которая вызывает закрытый метод, использует этот результат правильно.</span><span class="sxs-lookup"><span data-stu-id="aad9e-276">Just because a private method returns the expected result, does not mean the system that eventually calls the private method uses the result correctly.</span></span>

### <a name="stub-static-references"></a><span data-ttu-id="aad9e-277">Используйте заглушки для статических ссылок</span><span class="sxs-lookup"><span data-stu-id="aad9e-277">Stub static references</span></span>
<span data-ttu-id="aad9e-278">Один из принципов модульного тестирования — его полный контроль над тестируемой системой.</span><span class="sxs-lookup"><span data-stu-id="aad9e-278">One of the principles of a unit test is that it must have full control of the system under test.</span></span> <span data-ttu-id="aad9e-279">Это может быть проблематичным, когда рабочий код вызывает статические ссылки (например, `DateTime.Now`).</span><span class="sxs-lookup"><span data-stu-id="aad9e-279">This can be problematic when production code includes calls to static references (e.g. `DateTime.Now`).</span></span> <span data-ttu-id="aad9e-280">Рассмотрим следующий код.</span><span class="sxs-lookup"><span data-stu-id="aad9e-280">Consider the following code</span></span>

```csharp
public int GetDiscountedPrice(int price)
{
    if(DateTime.Now == DayOfWeek.Tuesday) 
    {
        return price / 2;
    }
    else 
    {
        return price;
    }
}
```

<span data-ttu-id="aad9e-281">Как можно провести модульное тестирование этого кода?</span><span class="sxs-lookup"><span data-stu-id="aad9e-281">How can this code possibly be unit tested?</span></span> <span data-ttu-id="aad9e-282">Вы можете попробовать следующий подход.</span><span class="sxs-lookup"><span data-stu-id="aad9e-282">You may try an approach such as</span></span>

```csharp
public void GetDiscountedPrice_ByDefault_ReturnsFullPrice()
{
    var priceCalculator = new PriceCalculator();

    var actual = priceCalculator.GetDiscountedPrice(2);

    Assert.Equals(2, actual)
}

public void GetDiscountedPrice_OnTuesday_ReturnsHalfPrice()
{
    var priceCalculator = new PriceCalculator();

    var actual = priceCalculator.GetDiscountedPrice(2);

    Assert.Equals(1, actual);
}
```

<span data-ttu-id="aad9e-283">К сожалению, вы быстро поймете, что в тестах есть несколько проблем.</span><span class="sxs-lookup"><span data-stu-id="aad9e-283">Unfortunately, you will quickly realize that there are a couple problems with your tests.</span></span> 

- <span data-ttu-id="aad9e-284">Если набор тестов выполняется во вторник, второй тест будет пройден, а первый — нет.</span><span class="sxs-lookup"><span data-stu-id="aad9e-284">If the test suite is run on a Tuesday, the second test will pass, but the first test will fail.</span></span>
- <span data-ttu-id="aad9e-285">Если набор тестов выполняется в другой день, первый тест будет пройден, а второй — нет.</span><span class="sxs-lookup"><span data-stu-id="aad9e-285">If the test suite is run on any other day, the first test will pass, but the second test will fail.</span></span>

<span data-ttu-id="aad9e-286">Для решения этих проблем вам потребуется ввести *шов* в рабочий код.</span><span class="sxs-lookup"><span data-stu-id="aad9e-286">To solve these problems, you'll need to introduce a *seam* into your production code.</span></span> <span data-ttu-id="aad9e-287">Например, можно заключить код, который необходимо контролировать, в интерфейс, чтобы рабочий код зависел от этого интерфейса.</span><span class="sxs-lookup"><span data-stu-id="aad9e-287">One approach is to wrap the code that you need to control in an interface and have the production code depend on that interface.</span></span>

```csharp
public interface IDateTimeProvider
{
    DayOfWeek DayOfWeek();
}

public bool GetDiscountedPrice(int price, IDateTimeProvider dateTimeProvider)
{
    if(dateTimeProvider.DayOfWeek() == DayOfWeek.Tuesday) 
    {
        return price / 2;
    }
    else 
    {
        return price;
    }
}
```

<span data-ttu-id="aad9e-288">Набор тестов теперь выглядит так.</span><span class="sxs-lookup"><span data-stu-id="aad9e-288">Your test suite now becomes</span></span>

```csharp
public void GetDiscountedPrice_ByDefault_ReturnsFullPrice()
{
    var priceCalculator = new PriceCalculator();
    var dateTimeProviderStub = new Mock<IDateTimeProvider>();
    dateTimeProviderStub.Setup(dtp => dtp.DayOfWeek()).Returns(DayOfWeek.Monday);

    var actual = priceCalculator.GetDiscountedPrice(2, dateTimeProviderStub);

    Assert.Equals(2, actual);
}

public void GetDiscountedPrice_OnTuesday_ReturnsHalfPrice()
{
    var priceCalculator = new PriceCalculator();
    var dateTimeProviderStub = new Mock<IDateTimeProvider>();
    dateTimeProviderStub.Setup(dtp => dtp.DayOfWeek()).Returns(DayOfWeek.Tuesday);

    var actual = priceCalculator.GetDiscountedPrice(2, dateTimeProviderStub);

    Assert.Equals(1, actual);
}
```

<span data-ttu-id="aad9e-289">Теперь набор тестов имеет полный контроль над `DateTime.Now` и может использовать заглушку для любого значения при вызове метода.</span><span class="sxs-lookup"><span data-stu-id="aad9e-289">Now the test suite has full control over `DateTime.Now` and can stub any value when calling into the method.</span></span>
