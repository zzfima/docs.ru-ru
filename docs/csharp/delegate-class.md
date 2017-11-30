---
title: "System.Delegate и ключевое слово delegate"
description: "Сведения о классах в .NET Framework, поддерживающих делегаты, а также их сопоставление с ключевым словом delegate."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: f3742fda-13c2-4283-8966-9e21c2674393
ms.openlocfilehash: 09c7da7c780389d3819cf23a533cc425b43ad5ff
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2017
---
# <a name="systemdelegate-and-the-delegate-keyword"></a><span data-ttu-id="ce3b7-104">System.Delegate и ключевое слово `delegate`</span><span class="sxs-lookup"><span data-stu-id="ce3b7-104">System.Delegate and the `delegate` keyword</span></span>

[<span data-ttu-id="ce3b7-105">Назад</span><span class="sxs-lookup"><span data-stu-id="ce3b7-105">Previous</span></span>](delegates-overview.md)

<span data-ttu-id="ce3b7-106">В этой статье описываются классы в .NET Framework, поддерживающие делегаты, и рассматривается их сопоставление с ключевым словом `delegate`.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-106">This article will cover the classes in the .NET framework that support delegates, and how those map to the `delegate` keyword.</span></span>

## <a name="defining-delegate-types"></a><span data-ttu-id="ce3b7-107">Определение типов делегатов</span><span class="sxs-lookup"><span data-stu-id="ce3b7-107">Defining Delegate Types</span></span>

<span data-ttu-id="ce3b7-108">Начнем с ключевого слова "delegate", потому что это основной элемент, используемый при работе с делегатами.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-108">Let's start with the 'delegate' keyword, because that's primarily what you will use as you work with delegates.</span></span> <span data-ttu-id="ce3b7-109">Код, который компилятор создает при использовании ключевого слова `delegate`, будет сопоставляться с вызовами методов, вызывающих члены классов <xref:System.Delegate> и <xref:System.MulticastDelegate>.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-109">The code that the compiler generates when you use the `delegate` keyword will map to method calls that invoke members of the <xref:System.Delegate> and <xref:System.MulticastDelegate> classes.</span></span> 

<span data-ttu-id="ce3b7-110">Тип делегата определяется с помощью синтаксиса, подобному синтаксису определения сигнатуры метода.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-110">You define a delegate type using syntax that is similar to defining a method signature.</span></span> <span data-ttu-id="ce3b7-111">К определению нужно просто добавить ключевое слово `delegate`.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-111">You just add the `delegate` keyword to the definition.</span></span>

<span data-ttu-id="ce3b7-112">В качестве примера будем по-прежнему использовать метод List.Sort().</span><span class="sxs-lookup"><span data-stu-id="ce3b7-112">Let's continue to use the List.Sort() method as our example.</span></span> <span data-ttu-id="ce3b7-113">Первым шагом является создание типа для делегата сравнения.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-113">The first step is to create a type for the comparison delegate:</span></span>

```csharp
// From the .NET Core library

// Define the delegate type:
public delegate int Comparison<in T>(T left, T right);
```

<span data-ttu-id="ce3b7-114">Компилятор создает класс, производный от `System.Delegate`, соответствующий используемой сигнатуре (в данном случае — метод, который возвращает целое число и имеет два аргумента).</span><span class="sxs-lookup"><span data-stu-id="ce3b7-114">The compiler generates a class, derived from `System.Delegate` that matches the signature used (in this case, a method that returns an integer, and has two arguments).</span></span> <span data-ttu-id="ce3b7-115">Тип делегата — `Comparison`.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-115">The type of that delegate is `Comparison`.</span></span> <span data-ttu-id="ce3b7-116">Тип делегата `Comparison` является универсальным типом.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-116">The `Comparison` delegate type is a generic type.</span></span> <span data-ttu-id="ce3b7-117">Подробные сведения об универсальных типах см. [здесь](generics.md).</span><span class="sxs-lookup"><span data-stu-id="ce3b7-117">For details on generics see [here](generics.md).</span></span>

<span data-ttu-id="ce3b7-118">Обратите внимание, что синтаксис может отображаться так, будто он объявляет переменную, но на самом деле он объявляет *тип*.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-118">Notice that the syntax may appear as though it is declaring a variable, but it is actually declaring a *type*.</span></span> <span data-ttu-id="ce3b7-119">Можно определить типы делегатов внутри классов, непосредственно внутри пространств имен или даже в глобальном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-119">You can define delegate types inside classes, directly inside namespaces, or even in the global namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="ce3b7-120">Не рекомендуется объявлять типы делегатов (или другие типы) непосредственно в глобальном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-120">Declaring delegate types (or other types) directly in the global namespace is not recommended.</span></span> 

<span data-ttu-id="ce3b7-121">Компилятор также создает обработчики добавления и удаления для этого нового типа, чтобы клиенты этого класса могли добавлять и удалять методы из списка вызовов экземпляра.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-121">The compiler also generates add and remove handlers for this new type so that clients of this class can add and remove methods from an instance's invocation list.</span></span> <span data-ttu-id="ce3b7-122">Компилятор будет обеспечивать соответствие подписи добавляемого или удаляемого метода подписи, используемой при объявлении метода.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-122">The compiler will enforce that the signature of the method being added or removed matches the signature used when declaring the method.</span></span> 

## <a name="declaring-instances-of-delegates"></a><span data-ttu-id="ce3b7-123">Объявление экземпляров делегатов</span><span class="sxs-lookup"><span data-stu-id="ce3b7-123">Declaring instances of delegates</span></span>

<span data-ttu-id="ce3b7-124">После определения делегата можно создать экземпляр этого типа.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-124">After defining the delegate, you can create an instance of that type.</span></span>
<span data-ttu-id="ce3b7-125">Как и все переменные в C#, экземпляры делегата нельзя объявлять непосредственно в пространстве имен или в глобальном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-125">Like all variables in C#, you cannot declare delegate instances directly in a namespace, or in the global namespace.</span></span>

```csharp
// inside a class definition:

// Declare an instance of that type:
public Comparison<T> comparator;
```

<span data-ttu-id="ce3b7-126">Тип переменной — `Comparison<T>`, тип делегата определен ранее.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-126">The type of the variable is `Comparison<T>`, the delegate type defined earlier.</span></span> <span data-ttu-id="ce3b7-127">Имя переменной — `comparator`.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-127">The name of the variable is `comparator`.</span></span>
 
 <span data-ttu-id="ce3b7-128">В приведенном выше фрагменте кода была объявлена переменная-член в классе.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-128">That code snippet above declared a member variable inside a class.</span></span> <span data-ttu-id="ce3b7-129">Можно также объявить переменные делегатов, локальные переменные или аргументов для методов.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-129">You can also declare delegate variables that are local variables, or arguments to methods.</span></span>

## <a name="invoking-delegates"></a><span data-ttu-id="ce3b7-130">Вызов делегатов</span><span class="sxs-lookup"><span data-stu-id="ce3b7-130">Invoking Delegates</span></span>

<span data-ttu-id="ce3b7-131">Чтобы вызвать методы, которые находятся в списке вызова делегата, нужно вызвать этот делегат.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-131">You invoke the methods that are in the invocation list of a delegate by calling that delegate.</span></span> <span data-ttu-id="ce3b7-132">В методе `Sort()` код вызовет метод сравнения, чтобы определить порядок размещения объектов:</span><span class="sxs-lookup"><span data-stu-id="ce3b7-132">Inside the `Sort()` method, the code will call the comparison method to determine which order to place objects:</span></span>

```csharp
int result = comparator(left, right);
```

<span data-ttu-id="ce3b7-133">В строке выше код *вызывает* метод, подключенный к делегату.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-133">In the line above, the code *invokes* the method attached to the delegate.</span></span>
<span data-ttu-id="ce3b7-134">Переменная считается именем метода и вызывается с помощью обычного синтаксиса вызова метода.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-134">You treat the variable as a method name, and invoke it using normal method call syntax.</span></span>

<span data-ttu-id="ce3b7-135">Эта строка кода содержит небезопасное условие: нет никакой гарантии, что целевой объект было добавлен к делегату.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-135">That line of code makes an unsafe assumption: There's no guarantee that a target has been added to the delegate.</span></span> <span data-ttu-id="ce3b7-136">Если целевые объекты не были вложены, строка выше приведет к возникновению исключения `NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-136">If no targets have been attached, the line above would cause a `NullReferenceException` to be thrown.</span></span> <span data-ttu-id="ce3b7-137">Идиомы, используемые для решения этой проблемы, более сложны, чем простые проверки значений NULL, и рассматриваются далее в этой [серии](delegates-patterns.md) материалов.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-137">The idioms used to address this problem are more complicated than a simple null-check, and are covered later in this [series](delegates-patterns.md).</span></span>

## <a name="assigning-adding-and-removing-invocation-targets"></a><span data-ttu-id="ce3b7-138">Назначение, добавление и удаление целевых объектов вызова</span><span class="sxs-lookup"><span data-stu-id="ce3b7-138">Assigning, Adding and removing Invocation Targets</span></span>

<span data-ttu-id="ce3b7-139">Сведения о том, как определяется тип делегата и как объявляются и вызываются экземпляры делегата.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-139">That's how a delegate type is defined, and how delegate instances are declared and invoked.</span></span>

<span data-ttu-id="ce3b7-140">Разработчикам, которые хотят использовать метод `List.Sort()`, нужно определить метод, сигнатура которого совпадает с определением типа делегата, и назначить его делегату, используемому методом sort.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-140">Developers that want to use the `List.Sort()` method need to define a method whose signature matches the delegate type definition, and assign it to the delegate used by the sort method.</span></span> <span data-ttu-id="ce3b7-141">Это назначение добавляет метод в список вызовов данного делегата объекта.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-141">This assignment adds the method to the invocation list of that delegate object.</span></span>

<span data-ttu-id="ce3b7-142">Предположим, требуется отсортировать список строк по их длине.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-142">Suppose you wanted to sort a list of strings by their length.</span></span> <span data-ttu-id="ce3b7-143">Функция сравнения может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ce3b7-143">Your comparison function might be the following:</span></span>

```csharp
private static int CompareLength(string left, string right)
{
    return left.Length.CompareTo(right.Length);
}
```

<span data-ttu-id="ce3b7-144">Метод объявляется как закрытый метод.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-144">The method is declared as a private method.</span></span> <span data-ttu-id="ce3b7-145">Все правильно.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-145">That's fine.</span></span> <span data-ttu-id="ce3b7-146">Вам может быть не нужно, чтобы этот метод был частью общедоступного интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-146">You may not want this method to be part of your public interface.</span></span> <span data-ttu-id="ce3b7-147">Этот метод, присоединенный к делегату, по-прежнему можно использовать в качестве метода сравнения.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-147">It can still be used as the comparison method when attached to a delegate.</span></span> <span data-ttu-id="ce3b7-148">В вызывающем коде этот метод будет присоединен к целевому списку объекта делегата и будет доступен через этот делегат.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-148">The calling code will have this method attached to the target list of the delegate object, and can access it through that delegate.</span></span>

<span data-ttu-id="ce3b7-149">Чтобы создать эту связь, передайте метод в метод `List.Sort()`:</span><span class="sxs-lookup"><span data-stu-id="ce3b7-149">You create that relationship by passing that method to the `List.Sort()` method:</span></span>

```csharp
phrases.Sort(CompareLength);
```

<span data-ttu-id="ce3b7-150">Обратите внимание, что имя метода используется без скобок.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-150">Notice that the method name is used, without parentheses.</span></span> <span data-ttu-id="ce3b7-151">Использование метода как аргумента указывает компилятору преобразовать ссылку на метод в ссылку, которая может применяться как целевой объект вызова делегата, и присоединить этот метод в качестве целевого объекта вызова.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-151">Using the method as an argument tells the compiler to convert the method reference into a reference that can be used as a delegate invocation target, and attach that method as an invocation target.</span></span>

<span data-ttu-id="ce3b7-152">Вы также явно объявили переменную типа "Comparison<string>" и выполнили назначение:</span><span class="sxs-lookup"><span data-stu-id="ce3b7-152">You could also have been explicit by declaring a variable of type 'Comparison<string>\` and doing an assignment:</span></span>

```csharp
Comparison<string> comparer = CompareLength;
phrases.Sort(comparer);
```

<span data-ttu-id="ce3b7-153">В случаях, когда в качестве объекта делегата используется небольшой метод, для назначения обычно применяется синтаксис [лямбда-выражения](lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ce3b7-153">In uses where the method being used as a delegate target is a small method, it's common to use [Lambda Expression](lambda-expressions.md) syntax to perform the assignment:</span></span>

```csharp
Comparison<string> comparer = (left, right) => left.Length.CompareTo(right.Length);
phrases.Sort(comparer);
```

<span data-ttu-id="ce3b7-154">Использование лямбда-выражений для целевых объектов делегатов рассматривается более подробно в [следующем разделе](delegates-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="ce3b7-154">Using Lambda Expressions for delegate targets is covered more in a [later section](delegates-patterns.md).</span></span>

<span data-ttu-id="ce3b7-155">В примере Sort() к делегату обычно подключается один целевой метод.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-155">The Sort() example typically attaches a single target method to the delegate.</span></span> <span data-ttu-id="ce3b7-156">Однако объекты делегатов поддерживают списки вызовов, где к объекту делегата присоединено несколько целевых методов.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-156">However, delegate objects do support invocation lists that have multiple target methods attached to a delegate object.</span></span>

## <a name="delegate-and-multicastdelegate-classes"></a><span data-ttu-id="ce3b7-157">Классы Delegate и MulticastDelegate</span><span class="sxs-lookup"><span data-stu-id="ce3b7-157">Delegate and MulticastDelegate classes</span></span>

<span data-ttu-id="ce3b7-158">Описанная выше поддержка языка предоставляет функции и поддержку, которые обычно необходимы для работы с делегатами.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-158">The language support described above provides the features and support you'll typically need to work with delegates.</span></span> <span data-ttu-id="ce3b7-159">Эти возможности построены на двух классов в платформе .NET Core: <xref:System.Delegate> и <xref:System.MulticastDelegate>.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-159">These features are built on two classes in the .NET Core framework: <xref:System.Delegate> and <xref:System.MulticastDelegate>.</span></span>

<span data-ttu-id="ce3b7-160">Класс `System.Delegate` и его прямой вложенный класс `System.MulticastDelegate` обеспечивают поддержку платформы для создания делегатов, регистрации методов в качестве целевых объектов делегатов и вызова всех методов, которые зарегистрированы как целевые объекты делегатов.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-160">The `System.Delegate` class, and its single direct sub-class, `System.MulticastDelegate`, provide the framework support for creating delegates, registering methods as delegate targets, and invoking all methods that are registered as a delegate target.</span></span> 

<span data-ttu-id="ce3b7-161">Что интересно, сами классы `System.Delegate` и `System.MulticastDelegate` не являются типами делегатов.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-161">Interestingly, the `System.Delegate` and `System.MulticastDelegate` classes are not themselves delegate types.</span></span> <span data-ttu-id="ce3b7-162">Они являются основой для всех конкретных типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-162">They do provide the basis for all specific delegate types.</span></span> <span data-ttu-id="ce3b7-163">Тот же процесс конструкции языка требует, что нельзя объявить класс, который является производным от `Delegate` или `MulticastDelegate`.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-163">That same language design process mandated that you cannot declare a class that derives from `Delegate` or `MulticastDelegate`.</span></span> <span data-ttu-id="ce3b7-164">Это запрещено правилами языка C#.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-164">The C# language rules prohibit it.</span></span>
 
<span data-ttu-id="ce3b7-165">Вместо этого компилятор C# создает экземпляры класса, производного от `MulticastDelegate`, при использовании ключевого слова языка C# для объявления типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-165">Instead, the C# compiler creates instances of a class derived from `MulticastDelegate` when you use the C# language keyword to declare delegate types.</span></span>

<span data-ttu-id="ce3b7-166">Такая схема впервые появилась в первом выпуске C# и .NET.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-166">This design has its roots in the first release of C# and .NET.</span></span> <span data-ttu-id="ce3b7-167">Одной из целей команды разработки было обеспечение соблюдения типобезопасности при использовании делегатов.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-167">One goal for the design team was to ensure that the language enforced type safety when using delegates.</span></span> <span data-ttu-id="ce3b7-168">Это значило, что делегаты вызывались с помощью правильного типа и числа аргументов.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-168">That meant ensuring that delegates were invoked with the right type and number of arguments.</span></span> <span data-ttu-id="ce3b7-169">И что любой возвращаемый тип был правильно указан во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-169">And, that any return type was correctly indicated at compile time.</span></span> <span data-ttu-id="ce3b7-170">Делегаты входили в выпуск 1.0 .NET, который действовал до универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-170">Delegates were part of the 1.0 .NET release, which was before generics.</span></span>

<span data-ttu-id="ce3b7-171">Наилучший способ обеспечения безопасности типа заключался в том, что компилятор должен был создать конкретные классы делегатов, представляющих используемую сигнатуру метода.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-171">The best way to enforce this type safety was for the compiler to create the concrete delegate classes that represented the method signature being used.</span></span>

<span data-ttu-id="ce3b7-172">Несмотря на то, что невозможно создать производные классы напрямую, вы будете использовать методы, определенные в этих классах.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-172">Even though you cannot create derived classes directly, you will use the methods defined on these classes.</span></span> <span data-ttu-id="ce3b7-173">Разберем наиболее распространенные методы, которые будут использоваться при работе с делегатами.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-173">Let's go through the most common methods that you will use when you work with delegates.</span></span>

<span data-ttu-id="ce3b7-174">Первый и самый важный момент состоит в том, что каждый делегат является производным от `MulticastDelegate`.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-174">The first, most important fact to remember is that every delegate you work with is derived from `MulticastDelegate`.</span></span> <span data-ttu-id="ce3b7-175">Многоадресный делегат означает, что при вызове с помощью делегата может быть вызвано несколько целевых объектов метода.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-175">A multicast delegate means that more than one method target can be invoked when invoking through a delegate.</span></span> <span data-ttu-id="ce3b7-176">В исходной структуре планировалось проводить различие между делегатами, где можно было прикреплять и вызывать только один целевой метод, и делегатами, где можно было прикреплять и вызывать несколько целевых методов.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-176">The original design considered making a distinction between delegates where only one target method could be attached and invoked, and delegates where multiple target methods could be attached and invoked.</span></span> <span data-ttu-id="ce3b7-177">На практике это различие оказалась менее полезным, чем предполагалось изначально.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-177">That distinction proved to be less useful in practice than originally thought.</span></span> <span data-ttu-id="ce3b7-178">Уже были созданы два разных класса, которые находились в платформе с момента первого общедоступного выпуска.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-178">The two different classes were already created, and have been in the framework since its initial public release.</span></span>

<span data-ttu-id="ce3b7-179">Методы, которые чаще всего будут использоваться с делегатами, — `Invoke()` и `BeginInvoke()` / `EndInvoke()`.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-179">The methods that you will use the most with delegates are `Invoke()` and `BeginInvoke()` / `EndInvoke()`.</span></span> <span data-ttu-id="ce3b7-180">`Invoke()` будет вызывать все методы, которые были прикреплены к определенному экземпляру делегата.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-180">`Invoke()` will invoke all the methods that have been attached to a particular delegate instance.</span></span> <span data-ttu-id="ce3b7-181">Как было показано выше, для вызова делегатов обычно используется синтаксис вызова метода в переменной делегата.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-181">As you saw above, you typically invoke delegates using the method call syntax on the delegate variable.</span></span> <span data-ttu-id="ce3b7-182">[Далее в этой серии](delegates-patterns.md) материалов вы узнаете о шаблонах, которые работают непосредственно с этими методами.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-182">As you'll see [later in this series](delegates-patterns.md), there are patterns that work directly with these methods.</span></span>

<span data-ttu-id="ce3b7-183">После знакомства с синтаксисом языка и классами, поддерживающими делегаты, давайте рассмотрим вопросы использования, создания и вызова строго типизированных делегатов.</span><span class="sxs-lookup"><span data-stu-id="ce3b7-183">Now that you've seen the language syntax and the classes that support delegates, let's examine how strongly typed delegates are used, created and invoked.</span></span>

[<span data-ttu-id="ce3b7-184">Далее</span><span class="sxs-lookup"><span data-stu-id="ce3b7-184">Next</span></span>](delegates-strongly-typed.md)
