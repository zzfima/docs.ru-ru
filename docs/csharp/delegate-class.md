---
title: System.Delegate и ключевое слово `delegate`
description: Сведения о классах в .NET Framework, поддерживающих делегаты, а также их сопоставление с ключевым словом delegate.
ms.date: 06/20/2016
ms.assetid: f3742fda-13c2-4283-8966-9e21c2674393
ms.openlocfilehash: 39dca1053f87a5059bdc60f8b722091ba991cbd5
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2018
ms.locfileid: "34827304"
---
# <a name="systemdelegate-and-the-delegate-keyword"></a><span data-ttu-id="f5e75-103">System.Delegate и ключевое слово `delegate`</span><span class="sxs-lookup"><span data-stu-id="f5e75-103">System.Delegate and the `delegate` keyword</span></span>

[<span data-ttu-id="f5e75-104">Назад</span><span class="sxs-lookup"><span data-stu-id="f5e75-104">Previous</span></span>](delegates-overview.md)

<span data-ttu-id="f5e75-105">В этой статье описываются классы в .NET Framework, поддерживающие делегаты, и рассматривается их сопоставление с ключевым словом `delegate`.</span><span class="sxs-lookup"><span data-stu-id="f5e75-105">This article will cover the classes in the .NET framework that support delegates, and how those map to the `delegate` keyword.</span></span>

## <a name="defining-delegate-types"></a><span data-ttu-id="f5e75-106">Определение типов делегатов</span><span class="sxs-lookup"><span data-stu-id="f5e75-106">Defining Delegate Types</span></span>

<span data-ttu-id="f5e75-107">Начнем с ключевого слова "delegate", потому что это основной элемент, используемый при работе с делегатами.</span><span class="sxs-lookup"><span data-stu-id="f5e75-107">Let's start with the 'delegate' keyword, because that's primarily what you will use as you work with delegates.</span></span> <span data-ttu-id="f5e75-108">Код, который компилятор создает при использовании ключевого слова `delegate`, будет сопоставляться с вызовами методов, вызывающих члены классов <xref:System.Delegate> и <xref:System.MulticastDelegate>.</span><span class="sxs-lookup"><span data-stu-id="f5e75-108">The code that the compiler generates when you use the `delegate` keyword will map to method calls that invoke members of the <xref:System.Delegate> and <xref:System.MulticastDelegate> classes.</span></span> 

<span data-ttu-id="f5e75-109">Тип делегата определяется с помощью синтаксиса, подобному синтаксису определения сигнатуры метода.</span><span class="sxs-lookup"><span data-stu-id="f5e75-109">You define a delegate type using syntax that is similar to defining a method signature.</span></span> <span data-ttu-id="f5e75-110">К определению нужно просто добавить ключевое слово `delegate`.</span><span class="sxs-lookup"><span data-stu-id="f5e75-110">You just add the `delegate` keyword to the definition.</span></span>

<span data-ttu-id="f5e75-111">В качестве примера будем по-прежнему использовать метод List.Sort().</span><span class="sxs-lookup"><span data-stu-id="f5e75-111">Let's continue to use the List.Sort() method as our example.</span></span> <span data-ttu-id="f5e75-112">Первым шагом является создание типа для делегата сравнения.</span><span class="sxs-lookup"><span data-stu-id="f5e75-112">The first step is to create a type for the comparison delegate:</span></span>

```csharp
// From the .NET Core library

// Define the delegate type:
public delegate int Comparison<in T>(T left, T right);
```

<span data-ttu-id="f5e75-113">Компилятор создает класс, производный от `System.Delegate`, соответствующий используемой сигнатуре (в данном случае — метод, который возвращает целое число и имеет два аргумента).</span><span class="sxs-lookup"><span data-stu-id="f5e75-113">The compiler generates a class, derived from `System.Delegate` that matches the signature used (in this case, a method that returns an integer, and has two arguments).</span></span> <span data-ttu-id="f5e75-114">Тип делегата — `Comparison`.</span><span class="sxs-lookup"><span data-stu-id="f5e75-114">The type of that delegate is `Comparison`.</span></span> <span data-ttu-id="f5e75-115">Тип делегата `Comparison` является универсальным типом.</span><span class="sxs-lookup"><span data-stu-id="f5e75-115">The `Comparison` delegate type is a generic type.</span></span> <span data-ttu-id="f5e75-116">Подробные сведения об универсальных типах см. [здесь](generics.md).</span><span class="sxs-lookup"><span data-stu-id="f5e75-116">For details on generics see [here](generics.md).</span></span>

<span data-ttu-id="f5e75-117">Обратите внимание, что синтаксис может отображаться так, будто он объявляет переменную, но на самом деле он объявляет *тип*.</span><span class="sxs-lookup"><span data-stu-id="f5e75-117">Notice that the syntax may appear as though it is declaring a variable, but it is actually declaring a *type*.</span></span> <span data-ttu-id="f5e75-118">Можно определить типы делегатов внутри классов, непосредственно внутри пространств имен или даже в глобальном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="f5e75-118">You can define delegate types inside classes, directly inside namespaces, or even in the global namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="f5e75-119">Не рекомендуется объявлять типы делегатов (или другие типы) непосредственно в глобальном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="f5e75-119">Declaring delegate types (or other types) directly in the global namespace is not recommended.</span></span> 

<span data-ttu-id="f5e75-120">Компилятор также создает обработчики добавления и удаления для этого нового типа, чтобы клиенты этого класса могли добавлять и удалять методы из списка вызовов экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f5e75-120">The compiler also generates add and remove handlers for this new type so that clients of this class can add and remove methods from an instance's invocation list.</span></span> <span data-ttu-id="f5e75-121">Компилятор будет обеспечивать соответствие подписи добавляемого или удаляемого метода подписи, используемой при объявлении метода.</span><span class="sxs-lookup"><span data-stu-id="f5e75-121">The compiler will enforce that the signature of the method being added or removed matches the signature used when declaring the method.</span></span> 

## <a name="declaring-instances-of-delegates"></a><span data-ttu-id="f5e75-122">Объявление экземпляров делегатов</span><span class="sxs-lookup"><span data-stu-id="f5e75-122">Declaring instances of delegates</span></span>

<span data-ttu-id="f5e75-123">После определения делегата можно создать экземпляр этого типа.</span><span class="sxs-lookup"><span data-stu-id="f5e75-123">After defining the delegate, you can create an instance of that type.</span></span>
<span data-ttu-id="f5e75-124">Как и все переменные в C#, экземпляры делегата нельзя объявлять непосредственно в пространстве имен или в глобальном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="f5e75-124">Like all variables in C#, you cannot declare delegate instances directly in a namespace, or in the global namespace.</span></span>

```csharp
// inside a class definition:

// Declare an instance of that type:
public Comparison<T> comparator;
```

<span data-ttu-id="f5e75-125">Тип переменной — `Comparison<T>`, тип делегата определен ранее.</span><span class="sxs-lookup"><span data-stu-id="f5e75-125">The type of the variable is `Comparison<T>`, the delegate type defined earlier.</span></span> <span data-ttu-id="f5e75-126">Имя переменной — `comparator`.</span><span class="sxs-lookup"><span data-stu-id="f5e75-126">The name of the variable is `comparator`.</span></span>
 
 <span data-ttu-id="f5e75-127">В приведенном выше фрагменте кода была объявлена переменная-член в классе.</span><span class="sxs-lookup"><span data-stu-id="f5e75-127">That code snippet above declared a member variable inside a class.</span></span> <span data-ttu-id="f5e75-128">Можно также объявить переменные делегатов, локальные переменные или аргументов для методов.</span><span class="sxs-lookup"><span data-stu-id="f5e75-128">You can also declare delegate variables that are local variables, or arguments to methods.</span></span>

## <a name="invoking-delegates"></a><span data-ttu-id="f5e75-129">Вызов делегатов</span><span class="sxs-lookup"><span data-stu-id="f5e75-129">Invoking Delegates</span></span>

<span data-ttu-id="f5e75-130">Чтобы вызвать методы, которые находятся в списке вызова делегата, нужно вызвать этот делегат.</span><span class="sxs-lookup"><span data-stu-id="f5e75-130">You invoke the methods that are in the invocation list of a delegate by calling that delegate.</span></span> <span data-ttu-id="f5e75-131">В методе `Sort()` код вызовет метод сравнения, чтобы определить порядок размещения объектов:</span><span class="sxs-lookup"><span data-stu-id="f5e75-131">Inside the `Sort()` method, the code will call the comparison method to determine which order to place objects:</span></span>

```csharp
int result = comparator(left, right);
```

<span data-ttu-id="f5e75-132">В строке выше код *вызывает* метод, подключенный к делегату.</span><span class="sxs-lookup"><span data-stu-id="f5e75-132">In the line above, the code *invokes* the method attached to the delegate.</span></span>
<span data-ttu-id="f5e75-133">Переменная считается именем метода и вызывается с помощью обычного синтаксиса вызова метода.</span><span class="sxs-lookup"><span data-stu-id="f5e75-133">You treat the variable as a method name, and invoke it using normal method call syntax.</span></span>

<span data-ttu-id="f5e75-134">Эта строка кода содержит небезопасное условие: нет никакой гарантии, что целевой объект было добавлен к делегату.</span><span class="sxs-lookup"><span data-stu-id="f5e75-134">That line of code makes an unsafe assumption: There's no guarantee that a target has been added to the delegate.</span></span> <span data-ttu-id="f5e75-135">Если целевые объекты не были вложены, строка выше приведет к возникновению исключения `NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="f5e75-135">If no targets have been attached, the line above would cause a `NullReferenceException` to be thrown.</span></span> <span data-ttu-id="f5e75-136">Идиомы, используемые для решения этой проблемы, более сложны, чем простые проверки значений NULL, и рассматриваются далее в этой [серии](delegates-patterns.md) материалов.</span><span class="sxs-lookup"><span data-stu-id="f5e75-136">The idioms used to address this problem are more complicated than a simple null-check, and are covered later in this [series](delegates-patterns.md).</span></span>

## <a name="assigning-adding-and-removing-invocation-targets"></a><span data-ttu-id="f5e75-137">Назначение, добавление и удаление целевых объектов вызова</span><span class="sxs-lookup"><span data-stu-id="f5e75-137">Assigning, Adding and removing Invocation Targets</span></span>

<span data-ttu-id="f5e75-138">Сведения о том, как определяется тип делегата и как объявляются и вызываются экземпляры делегата.</span><span class="sxs-lookup"><span data-stu-id="f5e75-138">That's how a delegate type is defined, and how delegate instances are declared and invoked.</span></span>

<span data-ttu-id="f5e75-139">Разработчикам, которые хотят использовать метод `List.Sort()`, нужно определить метод, сигнатура которого совпадает с определением типа делегата, и назначить его делегату, используемому методом sort.</span><span class="sxs-lookup"><span data-stu-id="f5e75-139">Developers that want to use the `List.Sort()` method need to define a method whose signature matches the delegate type definition, and assign it to the delegate used by the sort method.</span></span> <span data-ttu-id="f5e75-140">Это назначение добавляет метод в список вызовов данного делегата объекта.</span><span class="sxs-lookup"><span data-stu-id="f5e75-140">This assignment adds the method to the invocation list of that delegate object.</span></span>

<span data-ttu-id="f5e75-141">Предположим, требуется отсортировать список строк по их длине.</span><span class="sxs-lookup"><span data-stu-id="f5e75-141">Suppose you wanted to sort a list of strings by their length.</span></span> <span data-ttu-id="f5e75-142">Функция сравнения может выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f5e75-142">Your comparison function might be the following:</span></span>

```csharp
private static int CompareLength(string left, string right) =>
    left.Length.CompareTo(right.Length);
```

<span data-ttu-id="f5e75-143">Метод объявляется как закрытый метод.</span><span class="sxs-lookup"><span data-stu-id="f5e75-143">The method is declared as a private method.</span></span> <span data-ttu-id="f5e75-144">Все правильно.</span><span class="sxs-lookup"><span data-stu-id="f5e75-144">That's fine.</span></span> <span data-ttu-id="f5e75-145">Вам может быть не нужно, чтобы этот метод был частью общедоступного интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f5e75-145">You may not want this method to be part of your public interface.</span></span> <span data-ttu-id="f5e75-146">Этот метод, присоединенный к делегату, по-прежнему можно использовать в качестве метода сравнения.</span><span class="sxs-lookup"><span data-stu-id="f5e75-146">It can still be used as the comparison method when attached to a delegate.</span></span> <span data-ttu-id="f5e75-147">В вызывающем коде этот метод будет присоединен к целевому списку объекта делегата и будет доступен через этот делегат.</span><span class="sxs-lookup"><span data-stu-id="f5e75-147">The calling code will have this method attached to the target list of the delegate object, and can access it through that delegate.</span></span>

<span data-ttu-id="f5e75-148">Чтобы создать эту связь, передайте метод в метод `List.Sort()`:</span><span class="sxs-lookup"><span data-stu-id="f5e75-148">You create that relationship by passing that method to the `List.Sort()` method:</span></span>

```csharp
phrases.Sort(CompareLength);
```

<span data-ttu-id="f5e75-149">Обратите внимание, что имя метода используется без скобок.</span><span class="sxs-lookup"><span data-stu-id="f5e75-149">Notice that the method name is used, without parentheses.</span></span> <span data-ttu-id="f5e75-150">Использование метода как аргумента указывает компилятору преобразовать ссылку на метод в ссылку, которая может применяться как целевой объект вызова делегата, и присоединить этот метод в качестве целевого объекта вызова.</span><span class="sxs-lookup"><span data-stu-id="f5e75-150">Using the method as an argument tells the compiler to convert the method reference into a reference that can be used as a delegate invocation target, and attach that method as an invocation target.</span></span>

<span data-ttu-id="f5e75-151">Вы также явно объявили переменную типа "Comparison<string>" и выполнили назначение:</span><span class="sxs-lookup"><span data-stu-id="f5e75-151">You could also have been explicit by declaring a variable of type 'Comparison<string>\` and doing an assignment:</span></span>

```csharp
Comparison<string> comparer = CompareLength;
phrases.Sort(comparer);
```

<span data-ttu-id="f5e75-152">В случаях, когда в качестве объекта делегата используется небольшой метод, для назначения обычно применяется синтаксис [лямбда-выражения](lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f5e75-152">In uses where the method being used as a delegate target is a small method, it's common to use [Lambda Expression](lambda-expressions.md) syntax to perform the assignment:</span></span>

```csharp
Comparison<string> comparer = (left, right) => left.Length.CompareTo(right.Length);
phrases.Sort(comparer);
```

<span data-ttu-id="f5e75-153">Использование лямбда-выражений для целевых объектов делегатов рассматривается более подробно в [следующем разделе](delegates-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="f5e75-153">Using Lambda Expressions for delegate targets is covered more in a [later section](delegates-patterns.md).</span></span>

<span data-ttu-id="f5e75-154">В примере Sort() к делегату обычно подключается один целевой метод.</span><span class="sxs-lookup"><span data-stu-id="f5e75-154">The Sort() example typically attaches a single target method to the delegate.</span></span> <span data-ttu-id="f5e75-155">Однако объекты делегатов поддерживают списки вызовов, где к объекту делегата присоединено несколько целевых методов.</span><span class="sxs-lookup"><span data-stu-id="f5e75-155">However, delegate objects do support invocation lists that have multiple target methods attached to a delegate object.</span></span>

## <a name="delegate-and-multicastdelegate-classes"></a><span data-ttu-id="f5e75-156">Классы Delegate и MulticastDelegate</span><span class="sxs-lookup"><span data-stu-id="f5e75-156">Delegate and MulticastDelegate classes</span></span>

<span data-ttu-id="f5e75-157">Описанная выше поддержка языка предоставляет функции и поддержку, которые обычно необходимы для работы с делегатами.</span><span class="sxs-lookup"><span data-stu-id="f5e75-157">The language support described above provides the features and support you'll typically need to work with delegates.</span></span> <span data-ttu-id="f5e75-158">Эти возможности основаны на двух классах в платформе .NET Core: <xref:System.Delegate> и <xref:System.MulticastDelegate>.</span><span class="sxs-lookup"><span data-stu-id="f5e75-158">These features are built on two classes in the .NET Core framework: <xref:System.Delegate> and <xref:System.MulticastDelegate>.</span></span>

<span data-ttu-id="f5e75-159">Класс `System.Delegate` и его прямой вложенный класс `System.MulticastDelegate` обеспечивают поддержку платформы для создания делегатов, регистрации методов в качестве целевых объектов делегатов и вызова всех методов, которые зарегистрированы как целевые объекты делегатов.</span><span class="sxs-lookup"><span data-stu-id="f5e75-159">The `System.Delegate` class, and its single direct sub-class, `System.MulticastDelegate`, provide the framework support for creating delegates, registering methods as delegate targets, and invoking all methods that are registered as a delegate target.</span></span> 

<span data-ttu-id="f5e75-160">Что интересно, сами классы `System.Delegate` и `System.MulticastDelegate` не являются типами делегатов.</span><span class="sxs-lookup"><span data-stu-id="f5e75-160">Interestingly, the `System.Delegate` and `System.MulticastDelegate` classes are not themselves delegate types.</span></span> <span data-ttu-id="f5e75-161">Они являются основой для всех конкретных типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="f5e75-161">They do provide the basis for all specific delegate types.</span></span> <span data-ttu-id="f5e75-162">Тот же процесс конструкции языка требует, что нельзя объявить класс, который является производным от `Delegate` или `MulticastDelegate`.</span><span class="sxs-lookup"><span data-stu-id="f5e75-162">That same language design process mandated that you cannot declare a class that derives from `Delegate` or `MulticastDelegate`.</span></span> <span data-ttu-id="f5e75-163">Это запрещено правилами языка C#.</span><span class="sxs-lookup"><span data-stu-id="f5e75-163">The C# language rules prohibit it.</span></span>
 
<span data-ttu-id="f5e75-164">Вместо этого компилятор C# создает экземпляры класса, производного от `MulticastDelegate`, при использовании ключевого слова языка C# для объявления типов делегатов.</span><span class="sxs-lookup"><span data-stu-id="f5e75-164">Instead, the C# compiler creates instances of a class derived from `MulticastDelegate` when you use the C# language keyword to declare delegate types.</span></span>

<span data-ttu-id="f5e75-165">Такая схема впервые появилась в первом выпуске C# и .NET.</span><span class="sxs-lookup"><span data-stu-id="f5e75-165">This design has its roots in the first release of C# and .NET.</span></span> <span data-ttu-id="f5e75-166">Одной из целей команды разработки было обеспечение соблюдения типобезопасности при использовании делегатов.</span><span class="sxs-lookup"><span data-stu-id="f5e75-166">One goal for the design team was to ensure that the language enforced type safety when using delegates.</span></span> <span data-ttu-id="f5e75-167">Это значило, что делегаты вызывались с помощью правильного типа и числа аргументов.</span><span class="sxs-lookup"><span data-stu-id="f5e75-167">That meant ensuring that delegates were invoked with the right type and number of arguments.</span></span> <span data-ttu-id="f5e75-168">И что любой возвращаемый тип был правильно указан во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="f5e75-168">And, that any return type was correctly indicated at compile time.</span></span> <span data-ttu-id="f5e75-169">Делегаты входили в выпуск 1.0 .NET, который действовал до универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="f5e75-169">Delegates were part of the 1.0 .NET release, which was before generics.</span></span>

<span data-ttu-id="f5e75-170">Наилучший способ обеспечения безопасности типа заключался в том, что компилятор должен был создать конкретные классы делегатов, представляющих используемую сигнатуру метода.</span><span class="sxs-lookup"><span data-stu-id="f5e75-170">The best way to enforce this type safety was for the compiler to create the concrete delegate classes that represented the method signature being used.</span></span>

<span data-ttu-id="f5e75-171">Несмотря на то, что невозможно создать производные классы напрямую, вы будете использовать методы, определенные в этих классах.</span><span class="sxs-lookup"><span data-stu-id="f5e75-171">Even though you cannot create derived classes directly, you will use the methods defined on these classes.</span></span> <span data-ttu-id="f5e75-172">Разберем наиболее распространенные методы, которые будут использоваться при работе с делегатами.</span><span class="sxs-lookup"><span data-stu-id="f5e75-172">Let's go through the most common methods that you will use when you work with delegates.</span></span>

<span data-ttu-id="f5e75-173">Первый и самый важный момент состоит в том, что каждый делегат является производным от `MulticastDelegate`.</span><span class="sxs-lookup"><span data-stu-id="f5e75-173">The first, most important fact to remember is that every delegate you work with is derived from `MulticastDelegate`.</span></span> <span data-ttu-id="f5e75-174">Многоадресный делегат означает, что при вызове с помощью делегата может быть вызвано несколько целевых объектов метода.</span><span class="sxs-lookup"><span data-stu-id="f5e75-174">A multicast delegate means that more than one method target can be invoked when invoking through a delegate.</span></span> <span data-ttu-id="f5e75-175">В исходной структуре планировалось проводить различие между делегатами, где можно было прикреплять и вызывать только один целевой метод, и делегатами, где можно было прикреплять и вызывать несколько целевых методов.</span><span class="sxs-lookup"><span data-stu-id="f5e75-175">The original design considered making a distinction between delegates where only one target method could be attached and invoked, and delegates where multiple target methods could be attached and invoked.</span></span> <span data-ttu-id="f5e75-176">На практике это различие оказалась менее полезным, чем предполагалось изначально.</span><span class="sxs-lookup"><span data-stu-id="f5e75-176">That distinction proved to be less useful in practice than originally thought.</span></span> <span data-ttu-id="f5e75-177">Уже были созданы два разных класса, которые находились в платформе с момента первого общедоступного выпуска.</span><span class="sxs-lookup"><span data-stu-id="f5e75-177">The two different classes were already created, and have been in the framework since its initial public release.</span></span>

<span data-ttu-id="f5e75-178">Методы, которые чаще всего будут использоваться с делегатами, — `Invoke()` и `BeginInvoke()` / `EndInvoke()`.</span><span class="sxs-lookup"><span data-stu-id="f5e75-178">The methods that you will use the most with delegates are `Invoke()` and `BeginInvoke()` / `EndInvoke()`.</span></span> <span data-ttu-id="f5e75-179">`Invoke()` будет вызывать все методы, которые были прикреплены к определенному экземпляру делегата.</span><span class="sxs-lookup"><span data-stu-id="f5e75-179">`Invoke()` will invoke all the methods that have been attached to a particular delegate instance.</span></span> <span data-ttu-id="f5e75-180">Как было показано выше, для вызова делегатов обычно используется синтаксис вызова метода в переменной делегата.</span><span class="sxs-lookup"><span data-stu-id="f5e75-180">As you saw above, you typically invoke delegates using the method call syntax on the delegate variable.</span></span> <span data-ttu-id="f5e75-181">[Далее в этой серии](delegates-patterns.md) материалов вы узнаете о шаблонах, которые работают непосредственно с этими методами.</span><span class="sxs-lookup"><span data-stu-id="f5e75-181">As you'll see [later in this series](delegates-patterns.md), there are patterns that work directly with these methods.</span></span>

<span data-ttu-id="f5e75-182">После знакомства с синтаксисом языка и классами, поддерживающими делегаты, давайте рассмотрим вопросы использования, создания и вызова строго типизированных делегатов.</span><span class="sxs-lookup"><span data-stu-id="f5e75-182">Now that you've seen the language syntax and the classes that support delegates, let's examine how strongly typed delegates are used, created and invoked.</span></span>

[<span data-ttu-id="f5e75-183">Далее</span><span class="sxs-lookup"><span data-stu-id="f5e75-183">Next</span></span>](delegates-strongly-typed.md)
