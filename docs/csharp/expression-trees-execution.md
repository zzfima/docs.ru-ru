---
title: Выполнение деревьев выражений
description: Сведения о выполнении деревьев выражений путем их преобразования в исполняемые инструкции промежуточного языка (IL).
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: 109e0ac5-2a9c-48b4-ac68-9b6219cdbccf
ms.openlocfilehash: 9af4b346962cb743daddf774e8b3c1f8fa722ae4
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73037112"
---
# <a name="executing-expression-trees"></a><span data-ttu-id="37792-103">Выполнение деревьев выражений</span><span class="sxs-lookup"><span data-stu-id="37792-103">Executing Expression Trees</span></span>

[<span data-ttu-id="37792-104">Предыдущий раздел: "Типы платформ, поддерживающие деревья выражений"</span><span class="sxs-lookup"><span data-stu-id="37792-104">Previous -- Framework Types Supporting Expression Trees</span></span>](expression-classes.md)

<span data-ttu-id="37792-105">*Дерево выражения* — это структура данных, представляющая некоторый код.</span><span class="sxs-lookup"><span data-stu-id="37792-105">An *expression tree* is a data structure that represents some code.</span></span>
<span data-ttu-id="37792-106">Это не компилируемый и исполняемый код.</span><span class="sxs-lookup"><span data-stu-id="37792-106">It is not compiled and executable code.</span></span> <span data-ttu-id="37792-107">Чтобы выполнить код .NET, представленный деревом выражения, необходимо преобразовать его в исполняемые инструкции на промежуточном языке (IL).</span><span class="sxs-lookup"><span data-stu-id="37792-107">If you want to execute the .NET code that is represented by an expression tree, you must convert it into executable IL instructions.</span></span>

## <a name="lambda-expressions-to-functions"></a><span data-ttu-id="37792-108">Преобразование лямбда-выражений в функции</span><span class="sxs-lookup"><span data-stu-id="37792-108">Lambda Expressions to Functions</span></span>

<span data-ttu-id="37792-109">Любое лямбда-выражение или тип, производный от лямбда-выражения, можно преобразовать в исполняемый код IL.</span><span class="sxs-lookup"><span data-stu-id="37792-109">You can convert any LambdaExpression, or any type derived from LambdaExpression into executable IL.</span></span> <span data-ttu-id="37792-110">Другие типы выражений невозможно преобразовать в код напрямую.</span><span class="sxs-lookup"><span data-stu-id="37792-110">Other expression types cannot be directly converted into code.</span></span> <span data-ttu-id="37792-111">На практике это ограничение редко имеет значение.</span><span class="sxs-lookup"><span data-stu-id="37792-111">This restriction has little effect in practice.</span></span> <span data-ttu-id="37792-112">Лямбда-выражения — это единственный тип выражений, которые может потребоваться выполнить путем преобразования в исполняемый код IL.</span><span class="sxs-lookup"><span data-stu-id="37792-112">Lambda expressions are the only types of expressions that you would want to execute by converting to executable intermediate language (IL).</span></span> <span data-ttu-id="37792-113">(Например, представьте, есть ли смысл выполнять `ConstantExpression` напрямую.</span><span class="sxs-lookup"><span data-stu-id="37792-113">(Think about what it would mean to directly execute a `ConstantExpression`.</span></span> <span data-ttu-id="37792-114">Может ли это быть полезным?) Любое дерево выражения, представляющее собой `LambdaExpression` или тип, производный от `LambdaExpression`, можно преобразовать в IL.</span><span class="sxs-lookup"><span data-stu-id="37792-114">Would it mean anything useful?) Any expression tree that is a `LambdaExpression`, or a type derived from `LambdaExpression` can be converted to IL.</span></span>
<span data-ttu-id="37792-115">Тип выражения `Expression<TDelegate>` — единственный конкретный пример в библиотеках .NET Core.</span><span class="sxs-lookup"><span data-stu-id="37792-115">The expression type `Expression<TDelegate>` is the only concrete example in the .NET Core libraries.</span></span> <span data-ttu-id="37792-116">Он служит для представления выражения, которое соответствует любому типу делегата.</span><span class="sxs-lookup"><span data-stu-id="37792-116">It's used to represent an expression that maps to any delegate type.</span></span> <span data-ttu-id="37792-117">Так как этот тип сопоставлен с типом делегата, .NET может проверить выражение и создать код IL для делегата, который соответствует сигнатуре лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="37792-117">Because this type maps to a delegate type, .NET can examine the expression, and generate IL for an appropriate delegate that matches the signature of the lambda expression.</span></span> 

<span data-ttu-id="37792-118">В большинстве случаев при этом создается простое сопоставление между выражением и соответствующим ему делегатом.</span><span class="sxs-lookup"><span data-stu-id="37792-118">In most cases, this creates a simple mapping between an expression, and its corresponding delegate.</span></span> <span data-ttu-id="37792-119">Например, дерево выражения, представленное `Expression<Func<int>>`, преобразуется в делегат типа `Func<int>`.</span><span class="sxs-lookup"><span data-stu-id="37792-119">For example, an expression tree that is represented by `Expression<Func<int>>` would be converted to a delegate of the type `Func<int>`.</span></span> <span data-ttu-id="37792-120">Для лямбда-выражения с любым типом возвращаемого значения и списком аргументов существует тип делегата, который является целевым типом для исполняемого кода, представленного этим лямбда-выражением.</span><span class="sxs-lookup"><span data-stu-id="37792-120">For a lambda expression with any return type and argument list, there exists a delegate type that is the target type for the executable code represented by that lambda expression.</span></span>

<span data-ttu-id="37792-121">Тип `LambdaExpression` содержит члены `Compile` и `CompileToMethod`, которые используются для преобразования дерева выражения в исполняемый код.</span><span class="sxs-lookup"><span data-stu-id="37792-121">The `LambdaExpression` type contains `Compile` and `CompileToMethod` members that you would use to convert an expression tree to executable code.</span></span> <span data-ttu-id="37792-122">Метод `Compile` создает делегат.</span><span class="sxs-lookup"><span data-stu-id="37792-122">The `Compile` method creates a delegate.</span></span> <span data-ttu-id="37792-123">Метод `CompileToMethod` обновляет объект `MethodBuilder` с помощью кода IL, который представляет скомпилированные выходные данные дерева выражения.</span><span class="sxs-lookup"><span data-stu-id="37792-123">The `CompileToMethod` method updates a `MethodBuilder` object with the IL that represents the compiled output of the expression tree.</span></span> <span data-ttu-id="37792-124">Обратите внимание на то, что метод `CompileToMethod` доступен только на полнофункциональной классической платформе, но не на платформе .NET Core.</span><span class="sxs-lookup"><span data-stu-id="37792-124">Note that `CompileToMethod` is only available in the full desktop framework, not in the .NET Core.</span></span>

<span data-ttu-id="37792-125">При необходимости можно также предоставить объект `DebugInfoGenerator`, который будет получать символьную отладочную информацию для создаваемого объекта делегата.</span><span class="sxs-lookup"><span data-stu-id="37792-125">Optionally, you can also provide a `DebugInfoGenerator` that will receive the symbol debugging information for the generated delegate object.</span></span> <span data-ttu-id="37792-126">Это позволяет преобразовать дерево выражения в объект делегата и иметь полную отладочную информацию о созданном делегате.</span><span class="sxs-lookup"><span data-stu-id="37792-126">This enables you to convert the expression tree into a delegate object, and have full debugging information about the generated delegate.</span></span>

<span data-ttu-id="37792-127">Выражение преобразовывается в делегат с помощью следующего кода:</span><span class="sxs-lookup"><span data-stu-id="37792-127">You would convert an expression into a delegate using the following code:</span></span>

```csharp
Expression<Func<int>> add = () => 1 + 2;
var func = add.Compile(); // Create Delegate
var answer = func(); // Invoke Delegate
Console.WriteLine(answer);
```

<span data-ttu-id="37792-128">Обратите внимание на то, что тип делегата основан на типе выражения.</span><span class="sxs-lookup"><span data-stu-id="37792-128">Notice that the delegate type is based on the expression type.</span></span> <span data-ttu-id="37792-129">Если требуется использовать объект делегата строго типизированным образом, необходимо знать тип возвращаемого значения и список аргументов.</span><span class="sxs-lookup"><span data-stu-id="37792-129">You must know the return type and the argument list if you want to use the delegate object in a strongly typed manner.</span></span> <span data-ttu-id="37792-130">Метод `LambdaExpression.Compile()` возвращает тип `Delegate`.</span><span class="sxs-lookup"><span data-stu-id="37792-130">The `LambdaExpression.Compile()` method returns the `Delegate` type.</span></span> <span data-ttu-id="37792-131">Его необходимо будет привести к правильному типу делегата, чтобы средства времени компиляции могли проверить список аргументов или тип возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="37792-131">You will have to cast it to the correct delegate type to have any compile-time tools check the argument list or return type.</span></span>

## <a name="execution-and-lifetimes"></a><span data-ttu-id="37792-132">Выполнение и время существования</span><span class="sxs-lookup"><span data-stu-id="37792-132">Execution and Lifetimes</span></span>

<span data-ttu-id="37792-133">Код выполняется путем вызова делегата, созданного при вызове `LambdaExpression.Compile()`.</span><span class="sxs-lookup"><span data-stu-id="37792-133">You execute the code by invoking the delegate created when you called `LambdaExpression.Compile()`.</span></span> <span data-ttu-id="37792-134">Это можно увидеть в приведенном выше примере, где `add.Compile()` возвращает делегат.</span><span class="sxs-lookup"><span data-stu-id="37792-134">You can see this above where `add.Compile()` returns a delegate.</span></span> <span data-ttu-id="37792-135">Вызов этого делегата путем вызова `func()` приводит к выполнению кода.</span><span class="sxs-lookup"><span data-stu-id="37792-135">Invoking that delegate, by calling `func()` executes the code.</span></span>

<span data-ttu-id="37792-136">Делегат представляет код в дереве выражения.</span><span class="sxs-lookup"><span data-stu-id="37792-136">That delegate represents the code in the expression tree.</span></span> <span data-ttu-id="37792-137">Вы можете сохранить дескриптор делегата и вызвать его позднее.</span><span class="sxs-lookup"><span data-stu-id="37792-137">You can retain the handle to that delegate and invoke it later.</span></span> <span data-ttu-id="37792-138">Вам не нужно компилировать дерево выражения каждый раз, когда вы хотите выполнить представляемый им код.</span><span class="sxs-lookup"><span data-stu-id="37792-138">You don't need to compile the expression tree each time you want to execute the code it represents.</span></span> <span data-ttu-id="37792-139">(Помните, что деревья выражений являются неизменяемыми и повторная компиляция того же дерева выражения приведет к созданию делегата, который выполняет этот же код.)</span><span class="sxs-lookup"><span data-stu-id="37792-139">(Remember that expression trees are immutable, and compiling the same expression tree later will create a delegate that executes the same code.)</span></span>

<span data-ttu-id="37792-140">Не рекомендуется создавать более сложные механизмы перехвата с целью повышения производительности за счет уменьшения количества вызовов компиляции.</span><span class="sxs-lookup"><span data-stu-id="37792-140">I will caution you against trying to create any more sophisticated caching mechanisms to increase performance by avoiding unnecessary compile calls.</span></span> <span data-ttu-id="37792-141">Сравнение двух произвольных деревьев выражений с целью определить, представляют ли они один и тот же алгоритм, также требует времени.</span><span class="sxs-lookup"><span data-stu-id="37792-141">Comparing two arbitrary expression trees to determine if they represent the same algorithm will also be time consuming to execute.</span></span> <span data-ttu-id="37792-142">Скорее всего, время, сэкономленное за счет уменьшения количества вызовов `LambdaExpression.Compile()`, будет больше времени, затрачиваемого на выполнение кода, который определяет, приводят ли два разных дерева выражений к созданию одного и того же исполняемого кода.</span><span class="sxs-lookup"><span data-stu-id="37792-142">You'll likely find that the compute time you save avoiding any extra calls to `LambdaExpression.Compile()` will be more than consumed by the time executing code that determines of two different expression trees result in the same executable code.</span></span>

## <a name="caveats"></a><span data-ttu-id="37792-143">Предупреждения</span><span class="sxs-lookup"><span data-stu-id="37792-143">Caveats</span></span>

<span data-ttu-id="37792-144">Компиляция лямбда-выражения в делегат и вызов этого делегата — одна из простейших операций, которые можно выполнять с деревом выражения.</span><span class="sxs-lookup"><span data-stu-id="37792-144">Compiling a lambda expression to a delegate and invoking that delegate is one of the simplest operations you can perform with an expression tree.</span></span> <span data-ttu-id="37792-145">Однако даже в случае с такой простой операцией следует учитывать ряд моментов.</span><span class="sxs-lookup"><span data-stu-id="37792-145">However, even with this simple operation, there are caveats you must be aware of.</span></span> 

<span data-ttu-id="37792-146">Лямбда-выражения создают замыкания для всех локальных переменных, на которые в них имеются ссылки.</span><span class="sxs-lookup"><span data-stu-id="37792-146">Lambda Expressions create closures over any local variables that are referenced in the expression.</span></span> <span data-ttu-id="37792-147">Необходимо обеспечить возможность использования всех переменных, которые будут входить в делегат, в месте вызова `Compile` и при выполнении итогового делегата.</span><span class="sxs-lookup"><span data-stu-id="37792-147">You must guarantee that any variables that would be part of the delegate are usable at the location where you call `Compile`, and when you execute the resulting delegate.</span></span>

<span data-ttu-id="37792-148">Как правило, эту задачу решает компилятор.</span><span class="sxs-lookup"><span data-stu-id="37792-148">In general, the compiler will ensure that this is true.</span></span> <span data-ttu-id="37792-149">Однако если выражение обращается к переменной, которая реализует `IDisposable`, в коде может быть удален объект, который все еще удерживается деревом выражения.</span><span class="sxs-lookup"><span data-stu-id="37792-149">However, if your expression accesses a variable that implements `IDisposable`, it's possible that your code might dispose of the object while it is still held by the expression tree.</span></span>

<span data-ttu-id="37792-150">Например, следующий код выполняется нормально, так как `int` не реализует `IDisposable`:</span><span class="sxs-lookup"><span data-stu-id="37792-150">For example, this code works fine, because `int` does not implement `IDisposable`:</span></span>

```csharp
private static Func<int, int> CreateBoundFunc()
{
    var constant = 5; // constant is captured by the expression tree
    Expression<Func<int, int>> expression = (b) => constant + b;
    var rVal = expression.Compile();
    return rVal;
}
```

<span data-ttu-id="37792-151">Делегат захватил ссылку на локальную переменную `constant`.</span><span class="sxs-lookup"><span data-stu-id="37792-151">The delegate has captured a reference to the local variable `constant`.</span></span>
<span data-ttu-id="37792-152">Доступ к этой переменной осуществляется позднее, когда выполняется функция, возвращаемая `CreateBoundFunc`.</span><span class="sxs-lookup"><span data-stu-id="37792-152">That variable is accessed at any time later, when the function returned by `CreateBoundFunc` executes.</span></span>

<span data-ttu-id="37792-153">Однако следует рассмотреть также следующий (несколько искусственный) класс, который реализует `IDisposable`:</span><span class="sxs-lookup"><span data-stu-id="37792-153">However, consider this (rather contrived) class that implements `IDisposable`:</span></span>

```csharp
public class Resource : IDisposable
{
    private bool isDisposed = false;
    public int Argument
    {
        get
        {
            if (!isDisposed)
                return 5;
            else throw new ObjectDisposedException("Resource");
        }
    }

    public void Dispose()
    {
        isDisposed = true;
    }
}
```

<span data-ttu-id="37792-154">Если он используется в выражении, как показано ниже, то при выполнении кода, к которому обращается свойство `Resource.Argument`, возникнет исключение `ObjectDisposedException`:</span><span class="sxs-lookup"><span data-stu-id="37792-154">If you use it in an expression as shown below, you'll get an `ObjectDisposedException` when you execute the code referenced by the `Resource.Argument` property:</span></span>

```csharp
private static Func<int, int> CreateBoundResource()
{
    using (var constant = new Resource()) // constant is captured by the expression tree
    {
        Expression<Func<int, int>> expression = (b) => constant.Argument + b;
        var rVal = expression.Compile();
        return rVal;
    }
}
```

<span data-ttu-id="37792-155">Делегат, возвращенный этим методом, замкнулся на объекте `constant`, который был ликвидирован.</span><span class="sxs-lookup"><span data-stu-id="37792-155">The delegate returned from this method has closed over the `constant` object, which has been disposed of.</span></span> <span data-ttu-id="37792-156">(Причиной ликвидации является то, что он был объявлен в операторе `using`.)</span><span class="sxs-lookup"><span data-stu-id="37792-156">(It's been disposed, because it was declared in a `using` statement.)</span></span> 

<span data-ttu-id="37792-157">Теперь при выполнении делегата, возвращаемого этим методом, будет возникать исключение `ObjectDisposedException`.</span><span class="sxs-lookup"><span data-stu-id="37792-157">Now, when you execute the delegate returned from this method, you'll have a `ObjectDisposedException` thrown at the point of execution.</span></span>

<span data-ttu-id="37792-158">Может показаться странным, что ошибка времени выполнения представляет конструкцию времени компиляции, но таковы особенности работы с деревьями выражений.</span><span class="sxs-lookup"><span data-stu-id="37792-158">It does seem strange to have a runtime error representing a compile-time construct, but that's the world we enter when we work with expression trees.</span></span>

<span data-ttu-id="37792-159">Эта проблема может принимать разные формы, поэтому трудно дать общую рекомендацию по тому, как ее избежать.</span><span class="sxs-lookup"><span data-stu-id="37792-159">There are a lot of permutations of this problem, so it's hard to offer general guidance to avoid it.</span></span> <span data-ttu-id="37792-160">Проявляйте осторожность в отношении доступа к локальным переменным при определении выражений и в отношении доступа к состоянию в текущем объекте (представленном `this`) при создании дерева выражения, которое может возвращаться открытым интерфейсом API.</span><span class="sxs-lookup"><span data-stu-id="37792-160">Be careful about accessing local variables when defining expressions, and be careful about accessing state in the current object (represented by `this`) when creating an expression tree that can be returned by a public API.</span></span>

<span data-ttu-id="37792-161">Код выражения может ссылаться на методы или свойства в других сборках.</span><span class="sxs-lookup"><span data-stu-id="37792-161">The code in your expression may reference methods or properties in other assemblies.</span></span> <span data-ttu-id="37792-162">Эти сборки должны быть доступны при определении выражения, его компиляции и вызове итогового делегата.</span><span class="sxs-lookup"><span data-stu-id="37792-162">That assembly must be accessible when the expression is defined, and when it is compiled, and when the resulting delegate is invoked.</span></span> <span data-ttu-id="37792-163">В случае их отсутствия будет возникать исключение `ReferencedAssemblyNotFoundException`.</span><span class="sxs-lookup"><span data-stu-id="37792-163">You'll be met with a `ReferencedAssemblyNotFoundException` in cases where it is not present.</span></span>

## <a name="summary"></a><span data-ttu-id="37792-164">Сводка</span><span class="sxs-lookup"><span data-stu-id="37792-164">Summary</span></span>

<span data-ttu-id="37792-165">Деревья выражений, представляющие лямбда-выражения, можно компилировать с целью создания делегатов, которые можно выполнять.</span><span class="sxs-lookup"><span data-stu-id="37792-165">Expression Trees that represent lambda expressions can be compiled to create a delegate that you can execute.</span></span> <span data-ttu-id="37792-166">Таким образом обеспечивается механизм выполнения кода, представленного деревом выражения.</span><span class="sxs-lookup"><span data-stu-id="37792-166">This provides one mechanism to execute the code represented by an expression tree.</span></span>

<span data-ttu-id="37792-167">Дерево выражения представляет код, который будет выполняться для определенной конструкции, которую вы создаете.</span><span class="sxs-lookup"><span data-stu-id="37792-167">The Expression Tree does represent the code that would execute for any given construct you create.</span></span> <span data-ttu-id="37792-168">При условии, что среда, в которой компилируется и выполняется код, соответствует среде, в которой создается выражение, все работает правильно.</span><span class="sxs-lookup"><span data-stu-id="37792-168">As long as the environment where you compile and execute the code matches the environment where you create the expression, everything works as expected.</span></span> <span data-ttu-id="37792-169">В противном случае ошибки очень предсказуемы и выявляются при проведении первых тестов кода, в котором используются деревья выражений.</span><span class="sxs-lookup"><span data-stu-id="37792-169">When that doesn't happen, the errors are very predictable, and they will be caught in your first tests of any code using the expression trees.</span></span>

[<span data-ttu-id="37792-170">Следующий раздел: "Интерпретация выражений"</span><span class="sxs-lookup"><span data-stu-id="37792-170">Next -- Interpreting Expressions</span></span>](expression-trees-interpreting.md)
