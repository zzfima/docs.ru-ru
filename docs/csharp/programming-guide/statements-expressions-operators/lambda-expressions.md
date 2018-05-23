---
title: Лямбда-выражения (Руководство по программированию в C#)
ms.date: 03/03/2017
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: f20ba6845a6a84a57fa7636355d08b2f4e5cea2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="lambda-expressions-c-programming-guide"></a><span data-ttu-id="4dd85-102">Лямбда-выражения (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="4dd85-102">Lambda Expressions (C# Programming Guide)</span></span>
<span data-ttu-id="4dd85-103">Лямбда-выражение — это [анонимная функция](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) , с помощью которой можно создавать типы [делегатов](../../../csharp/programming-guide/delegates/using-delegates.md) или [деревьев выражений](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b) .</span><span class="sxs-lookup"><span data-stu-id="4dd85-103">A lambda expression is an [anonymous function](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md) that you can use to create [delegates](../../../csharp/programming-guide/delegates/using-delegates.md) or [expression tree](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b) types.</span></span> <span data-ttu-id="4dd85-104">С помощью лямбда-выражений можно писать локальные функции, которые можно передавать в качестве аргументов или возвращать в качестве значений из вызовов функций.</span><span class="sxs-lookup"><span data-stu-id="4dd85-104">By using lambda expressions, you can write local functions that can be passed as arguments or returned as the value of function calls.</span></span> <span data-ttu-id="4dd85-105">Лямбда-выражения особенно полезны при написании выражений запросов LINQ.</span><span class="sxs-lookup"><span data-stu-id="4dd85-105">Lambda expressions are particularly helpful for writing LINQ query expressions.</span></span>  
  
 <span data-ttu-id="4dd85-106">Чтобы создать лямбда-выражение, необходимо указать входные параметры (если они есть) с левой стороны лямбда-оператора [=>](../../../csharp/language-reference/operators/lambda-operator.md), и поместить блок выражений или операторов с другой стороны.</span><span class="sxs-lookup"><span data-stu-id="4dd85-106">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator [=>](../../../csharp/language-reference/operators/lambda-operator.md), and you put the expression or statement block on the other side.</span></span> <span data-ttu-id="4dd85-107">Например, лямбда-выражение `x => x * x` задает параметр с именем `x` и возвращает значение `x` .</span><span class="sxs-lookup"><span data-stu-id="4dd85-107">For example, the lambda expression `x => x * x` specifies a parameter that’s named `x` and returns the value of `x` squared.</span></span> <span data-ttu-id="4dd85-108">Можно назначить это выражение типу делегата, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="4dd85-108">You can assign this expression to a delegate type, as the following example shows:</span></span>  
  
```csharp  
delegate int del(int i);  
static void Main(string[] args)  
{  
    del myDelegate = x => x * x;  
    int j = myDelegate(5); //j = 25  
}  
```  
  
 <span data-ttu-id="4dd85-109">Создание типа дерева выражений:</span><span class="sxs-lookup"><span data-stu-id="4dd85-109">To create an expression tree type:</span></span>  
  
```csharp  
using System.Linq.Expressions;  
  
namespace ConsoleApplication1  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Expression<del> myET = x => x * x;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="4dd85-110">Оператор `=>` имеет такой же приоритет, как и присваивание (`=`), и является [правоассоциативным](../../../csharp/programming-guide/statements-expressions-operators/operators.md) (см. раздел "Ассоциативность" статьи об операторах).</span><span class="sxs-lookup"><span data-stu-id="4dd85-110">The `=>` operator has the same precedence as assignment (`=`) and is [right associative](../../../csharp/programming-guide/statements-expressions-operators/operators.md) (see "Associativity" section of the Operators article).</span></span>  
  
 <span data-ttu-id="4dd85-111">Лямбда-операторы используются в запросах [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] на основе методов в качестве аргументов стандартных методов операторов запроса, таких как <xref:System.Linq.Enumerable.Where%2A>.</span><span class="sxs-lookup"><span data-stu-id="4dd85-111">Lambdas are used in method-based [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries as arguments to standard query operator methods such as <xref:System.Linq.Enumerable.Where%2A>.</span></span>  
  
 <span data-ttu-id="4dd85-112">При использовании синтаксиса на основе методов для вызова метода <xref:System.Linq.Enumerable.Where%2A> в классе <xref:System.Linq.Enumerable> (как это делается в [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] на объекты и [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]) параметром является тип делегата <xref:System.Func%602?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4dd85-112">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Where%2A> method in the <xref:System.Linq.Enumerable> class (as you do in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to Objects and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]) the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4dd85-113">Лямбда-выражение — это наиболее удобный способ создания делегата.</span><span class="sxs-lookup"><span data-stu-id="4dd85-113">A lambda expression is the most convenient way to create that delegate.</span></span> <span data-ttu-id="4dd85-114">При вызове того же метода, к примеру, в классе <xref:System.Linq.Queryable?displayProperty=nameWithType> (как это делается в [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]) типом параметра будет <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType><Func\>, где Func — это любые делегаты Func с числом входных параметров не более шестнадцати.</span><span class="sxs-lookup"><span data-stu-id="4dd85-114">When you call the same method in, for example, the <xref:System.Linq.Queryable?displayProperty=nameWithType> class (as you do in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]) then the parameter type is an <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType><Func\> where Func is any of the Func delegates with up to sixteen input parameters.</span></span> <span data-ttu-id="4dd85-115">Опять же, лямбда-выражения представляют собой самый быстрый способ построения дерева выражений.</span><span class="sxs-lookup"><span data-stu-id="4dd85-115">Again, a lambda expression is just a very concise way to construct that expression tree.</span></span> <span data-ttu-id="4dd85-116">Лямбда-выражения позволяют вызовам `Where` выглядеть одинаково, хотя на самом деле объект, созданный из лямбда-выражения, имеет другой тип.</span><span class="sxs-lookup"><span data-stu-id="4dd85-116">The lambdas allow the `Where` calls to look similar although in fact the type of object created from the lambda is different.</span></span>  
  
 <span data-ttu-id="4dd85-117">Обратите внимание: в приведенном выше примере сигнатура делегата имеет один неявный входной параметр типа `int`и возвращает значение типа `int`.</span><span class="sxs-lookup"><span data-stu-id="4dd85-117">In the previous example, notice that the delegate signature has one implicitly-typed input parameter of type `int`, and returns an `int`.</span></span> <span data-ttu-id="4dd85-118">Лямбда-выражение можно преобразовать в делегат соответствующего типа, поскольку он также имеет один входной параметр (`x`) и возвращает значение, которое компилятор может неявно преобразовать в тип `int`.</span><span class="sxs-lookup"><span data-stu-id="4dd85-118">The lambda expression can be converted to a delegate of that type because it also has one input parameter (`x`) and a return value that the compiler can implicitly convert to type `int`.</span></span> <span data-ttu-id="4dd85-119">(Вывод типов более подробно рассматривается в следующих разделах.) Делегат, вызываемый посредством входного параметра 5, возвращает результат 25.</span><span class="sxs-lookup"><span data-stu-id="4dd85-119">(Type inference is discussed in more detail in the following sections.) When the delegate is invoked by using an input parameter of 5, it returns a result of 25.</span></span>  
  
 <span data-ttu-id="4dd85-120">Лямбда-выражения нельзя использовать с левой стороны оператора [is](../../../csharp/language-reference/keywords/is.md) или [as](../../../csharp/language-reference/keywords/as.md).</span><span class="sxs-lookup"><span data-stu-id="4dd85-120">Lambdas are not allowed on the left side of the [is](../../../csharp/language-reference/keywords/is.md) or [as](../../../csharp/language-reference/keywords/as.md) operator.</span></span>  
  
 <span data-ttu-id="4dd85-121">Все ограничения, применяемые к анонимным методам, применяются также к лямбда-выражениям.</span><span class="sxs-lookup"><span data-stu-id="4dd85-121">All restrictions that apply to anonymous methods also apply to lambda expressions.</span></span> <span data-ttu-id="4dd85-122">Дополнительные сведения см. в разделе [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="4dd85-122">For more information, see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
## <a name="expression-lambdas"></a><span data-ttu-id="4dd85-123">Выражения-лямбды</span><span class="sxs-lookup"><span data-stu-id="4dd85-123">Expression Lambdas</span></span>  
 <span data-ttu-id="4dd85-124">Лямбда-выражение с выражением с правой стороны оператора => называется *выражением-лямбдой*.</span><span class="sxs-lookup"><span data-stu-id="4dd85-124">A lambda expression with an expression on the right side of the => operator is called an *expression lambda*.</span></span> <span data-ttu-id="4dd85-125">Выражения-лямбды широко используются при конструировании [деревьев выражений](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b).</span><span class="sxs-lookup"><span data-stu-id="4dd85-125">Expression lambdas are used extensively in the construction of [Expression Trees](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b).</span></span> <span data-ttu-id="4dd85-126">Выражения-лямбды возвращают результат выражения и принимают следующую основную форму.</span><span class="sxs-lookup"><span data-stu-id="4dd85-126">An expression lambda returns the result of the expression and takes the following basic form:</span></span>  
  
```csharp
(input-parameters) => expression
```

 <span data-ttu-id="4dd85-127">Если лямбда-выражение имеет только один входной параметр, скобки можно не ставить; во всех остальных случаях они обязательны.</span><span class="sxs-lookup"><span data-stu-id="4dd85-127">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span> <span data-ttu-id="4dd85-128">Два и более входных параметра разделяются запятыми и заключаются в скобки:</span><span class="sxs-lookup"><span data-stu-id="4dd85-128">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>  
  
```csharp
(x, y) => x == y
```

 <span data-ttu-id="4dd85-129">Иногда компилятору бывает трудно или даже невозможно определить входные типы.</span><span class="sxs-lookup"><span data-stu-id="4dd85-129">Sometimes it is difficult or impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="4dd85-130">В этом случае типы можно указать в явном виде, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4dd85-130">When this occurs, you can specify the types explicitly as shown in the following example:</span></span>  
  
```csharp
(int x, string s) => s.Length > x
```

 <span data-ttu-id="4dd85-131">Нулевое количество входных параметры задается пустыми скобками:</span><span class="sxs-lookup"><span data-stu-id="4dd85-131">Specify zero input parameters with empty parentheses:</span></span>  
  
```csharp
() => SomeMethod()
```

 <span data-ttu-id="4dd85-132">Обратите внимание, что тело выражения-лямбды может состоять из вызова метода, как было показано в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="4dd85-132">Note in the previous example that the body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="4dd85-133">Однако при создании деревьев выражений, которые вычисляются вне .NET Framework, например в SQL Server, не следует использовать вызовы методов в лямбда-выражениях.</span><span class="sxs-lookup"><span data-stu-id="4dd85-133">However, if you are creating expression trees that are evaluated outside of the .NET Framework, such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="4dd85-134">Эти методы не имеют смысла вне контекста среды CLR .NET.</span><span class="sxs-lookup"><span data-stu-id="4dd85-134">The methods will have no meaning outside the context of the .NET common language runtime.</span></span>  
  
## <a name="statement-lambdas"></a><span data-ttu-id="4dd85-135">Лямбды операторов</span><span class="sxs-lookup"><span data-stu-id="4dd85-135">Statement Lambdas</span></span>  
 <span data-ttu-id="4dd85-136">Лямбда оператора напоминает выражение-лямбду, за исключением того, что оператор (или операторы) заключается в фигурные скобки:</span><span class="sxs-lookup"><span data-stu-id="4dd85-136">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>  
  
<span data-ttu-id="4dd85-137">(входные-параметры) => { оператор; }</span><span class="sxs-lookup"><span data-stu-id="4dd85-137">(input-parameters) => { statement; }</span></span>

 <span data-ttu-id="4dd85-138">Тело лямбды оператора может состоять из любого количества операторов; однако на практике обычно используется не более двух-трех.</span><span class="sxs-lookup"><span data-stu-id="4dd85-138">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>  
  
[!code-csharp[StatementLamba#1](../../../../samples\snippets\csharp\programming-guide\lambda-expressions/statements.cs#1)]

[!code-csharp[StatementLamba#2](../../../../samples\snippets\csharp\programming-guide\lambda-expressions/statements.cs#2)]

 <span data-ttu-id="4dd85-139">Лямбды операторов, как и анонимные методы, не могут использоваться для создания деревьев выражений.</span><span class="sxs-lookup"><span data-stu-id="4dd85-139">Statement lambdas, like anonymous methods, cannot be used to create expression trees.</span></span>  
  
## <a name="async-lambdas"></a><span data-ttu-id="4dd85-140">Асинхронные лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="4dd85-140">Async Lambdas</span></span>  
 <span data-ttu-id="4dd85-141">С помощью ключевых слов [async](../../../csharp/language-reference/keywords/async.md) и [await](../../../csharp/language-reference/keywords/await.md) можно легко создавать лямбда-выражения и операторы, включающие асинхронную обработку.</span><span class="sxs-lookup"><span data-stu-id="4dd85-141">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../../../csharp/language-reference/keywords/async.md) and [await](../../../csharp/language-reference/keywords/await.md) keywords.</span></span> <span data-ttu-id="4dd85-142">Например, в следующем примере Windows Forms содержится обработчик событий, который вызывает асинхронный метод `ExampleMethodAsync`и ожидает его.</span><span class="sxs-lookup"><span data-stu-id="4dd85-142">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>  
  
```csharp
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
    }  
  
    private async void button1_Click(object sender, EventArgs e)  
    {  
        // ExampleMethodAsync returns a Task.  
        await ExampleMethodAsync();  
        textBox1.Text += "\r\nControl returned to Click event handler.\n";  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```

 <span data-ttu-id="4dd85-143">Такой же обработчик событий можно добавить с помощью асинхронного лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="4dd85-143">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="4dd85-144">Чтобы добавить этот обработчик, поставьте модификатор `async` перед списком параметров лямбда-выражения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4dd85-144">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows.</span></span>  
  
```csharp  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        button1.Click += async (sender, e) =>  
        {  
            // ExampleMethodAsync returns a Task.  
            await ExampleMethodAsync();  
            textBox1.Text += "\nControl returned to Click event handler.\n";  
        };  
    }  
  
    async Task ExampleMethodAsync()  
    {  
        // The following line simulates a task-returning asynchronous process.  
        await Task.Delay(1000);  
    }  
}  
```  

 <span data-ttu-id="4dd85-145">Дополнительные сведения о создании и использовании асинхронных методов см. в разделе [Асинхронное программирование с использованием ключевых слов Async и Await](../../../csharp/programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="4dd85-145">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../../../csharp/programming-guide/concepts/async/index.md).</span></span>  
  
## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="4dd85-146">Лямбды со стандартными операторами запросов</span><span class="sxs-lookup"><span data-stu-id="4dd85-146">Lambdas with the Standard Query Operators</span></span>  
 <span data-ttu-id="4dd85-147">Многие стандартные операторы запросов имеют входной параметр, тип которого принадлежит к семейству <xref:System.Func%602> универсальных делегатов.</span><span class="sxs-lookup"><span data-stu-id="4dd85-147">Many Standard query operators have an input parameter whose type is one of the <xref:System.Func%602> family of generic delegates.</span></span> <span data-ttu-id="4dd85-148">Эти делегаты используют параметры типа для определения количества и типов входных параметров, а также тип возвращаемого значения делегата.</span><span class="sxs-lookup"><span data-stu-id="4dd85-148">These delegates use type parameters to define the number and types of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="4dd85-149">Делегаты`Func` очень полезны для инкапсуляции пользовательских выражений, которые применяются к каждому элементу в наборе исходных данных.</span><span class="sxs-lookup"><span data-stu-id="4dd85-149">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="4dd85-150">В качестве примера рассмотрим следующий тип делегата.</span><span class="sxs-lookup"><span data-stu-id="4dd85-150">For example, consider the following delegate type:</span></span>  
  
```csharp  
public delegate TResult Func<TArg0, TResult>(TArg0 arg0)  
```  
  
 <span data-ttu-id="4dd85-151">Экземпляр этого делегата можно создать как `Func<int,bool> myFunc` , где `int` — входной параметр, а `bool` — возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="4dd85-151">The delegate can be instantiated as `Func<int,bool> myFunc` where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="4dd85-152">Возвращаемое значение всегда указывается в последнем параметре типа.</span><span class="sxs-lookup"><span data-stu-id="4dd85-152">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="4dd85-153">`Func<int, string, bool>` определяет делегат с двумя входными параметрами, `int` и `string`, и типом возвращаемого значения `bool`.</span><span class="sxs-lookup"><span data-stu-id="4dd85-153">`Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="4dd85-154">Следующий делегат `Func` при вызове возвращает значение true или false, которое показывает, равен ли входной параметр 5.</span><span class="sxs-lookup"><span data-stu-id="4dd85-154">The following `Func` delegate, when it is invoked, will return true or false to indicate whether the input parameter is equal to 5:</span></span>  
  
```csharp  
Func<int, bool> myFunc = x => x == 5;  
bool result = myFunc(4); // returns false of course  
```  
  
 <span data-ttu-id="4dd85-155">Также лямбда-выражения можно использовать, когда аргумент имеет тип `Expression<Func>`, например в стандартных операторах запросов, как указано в System.Linq.Queryable.</span><span class="sxs-lookup"><span data-stu-id="4dd85-155">You can also supply a lambda expression when the argument type is an `Expression<Func>`, for example in the standard query operators that are defined in System.Linq.Queryable.</span></span> <span data-ttu-id="4dd85-156">При определении аргумента `Expression<Func>` лямбда компилируется в дерево выражений.</span><span class="sxs-lookup"><span data-stu-id="4dd85-156">When you specify an `Expression<Func>` argument, the lambda will be compiled to an expression tree.</span></span>  
  
 <span data-ttu-id="4dd85-157">Ниже показан метод <xref:System.Linq.Enumerable.Count%2A> , являющийся стандартным оператором запроса.</span><span class="sxs-lookup"><span data-stu-id="4dd85-157">A standard query operator, the <xref:System.Linq.Enumerable.Count%2A> method, is shown here:</span></span>  
  
```csharp  
int[] numbers = { 5, 4, 1, 3, 9, 8, 6, 7, 2, 0 };  
int oddNumbers = numbers.Count(n => n % 2 == 1);  
```  
  
 <span data-ttu-id="4dd85-158">Компилятор может вывести тип входного параметра ввода; но его также можно определить явным образом.</span><span class="sxs-lookup"><span data-stu-id="4dd85-158">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="4dd85-159">Данное лямбда-выражение подсчитывает указанные целые значения (`n`), которые при делении на два дают остаток 1.</span><span class="sxs-lookup"><span data-stu-id="4dd85-159">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>  
  
 <span data-ttu-id="4dd85-160">Следующая строка кода создает последовательность, которая содержит все элементы массива `numbers` , расположенные слева от 9, поскольку это первое число последовательности, не удовлетворяющее условию:</span><span class="sxs-lookup"><span data-stu-id="4dd85-160">The following line of code produces a sequence that contains all elements in the `numbers` array that are to the left side of the 9 because that's the first number in the sequence that doesn't meet the condition:</span></span>  
  
```csharp  
var firstNumbersLessThan6 = numbers.TakeWhile(n => n < 6);  
```  
  
 <span data-ttu-id="4dd85-161">В этом примере показано, как определить несколько входных параметров путем их заключения в скобки.</span><span class="sxs-lookup"><span data-stu-id="4dd85-161">This example shows how to specify multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="4dd85-162">Этот метод возвращает все элементы в массиве чисел до того числа, величина которого меньше номера его позиции.</span><span class="sxs-lookup"><span data-stu-id="4dd85-162">The method returns all the elements in the numbers array until a number is encountered whose value is less than its position.</span></span> <span data-ttu-id="4dd85-163">Не следует путать лямбда-оператор (`=>`) с оператором "больше или равно" (`>=`).</span><span class="sxs-lookup"><span data-stu-id="4dd85-163">Do not confuse the lambda operator (`=>`) with the greater than or equal operator (`>=`).</span></span>  
  
```csharp  
var firstSmallNumbers = numbers.TakeWhile((n, index) => n >= index);  
```  
  
## <a name="type-inference-in-lambdas"></a><span data-ttu-id="4dd85-164">Вывод типа в лямбда-выражениях</span><span class="sxs-lookup"><span data-stu-id="4dd85-164">Type Inference in Lambdas</span></span>  
 <span data-ttu-id="4dd85-165">При написании лямбда-выражений обычно не требуется указывать тип входных параметров, поскольку компилятор может выводить этот тип на основе тела лямбда-выражения, типа делегата параметра и других факторов, как описано в спецификации языка C#.</span><span class="sxs-lookup"><span data-stu-id="4dd85-165">When writing lambdas, you often do not have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter’s delegate type, and other factors as described in the C# Language Specification.</span></span> <span data-ttu-id="4dd85-166">Для большинства стандартных операторов запросов первой входное значение имеет тип элементов в исходной последовательности.</span><span class="sxs-lookup"><span data-stu-id="4dd85-166">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="4dd85-167">Поэтому при запросе `IEnumerable<Customer>`входная переменная считается объектом `Customer` , а это означает, что у вас есть доступ к его методам и свойствам.</span><span class="sxs-lookup"><span data-stu-id="4dd85-167">So if you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  
  
```csharp  
customers.Where(c => c.City == "London");  
```  
  
 <span data-ttu-id="4dd85-168">Общие правила для лямбда-выражений формулируются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4dd85-168">The general rules for lambdas are as follows:</span></span>  
  
-   <span data-ttu-id="4dd85-169">лямбда-выражение должно содержать то же число параметров, что и тип делегата;</span><span class="sxs-lookup"><span data-stu-id="4dd85-169">The lambda must contain the same number of parameters as the delegate type.</span></span>  
  
-   <span data-ttu-id="4dd85-170">каждый входной параметр в лямбда-выражении должен быть неявно преобразуемым в соответствующий параметр делегата;</span><span class="sxs-lookup"><span data-stu-id="4dd85-170">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>  
  
-   <span data-ttu-id="4dd85-171">возвращаемое значение лямбда-выражения (если таковое имеется) должно быть неявно преобразуемым в возвращаемый тип делегата.</span><span class="sxs-lookup"><span data-stu-id="4dd85-171">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>  
  
 <span data-ttu-id="4dd85-172">Обратите внимание: лямбда-выражения сами по себе не имеют типа, поскольку в системе общих типов изначально отсутствует понятие "лямбда-выражения".</span><span class="sxs-lookup"><span data-stu-id="4dd85-172">Note that lambda expressions in themselves do not have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="4dd85-173">Однако иногда бывает удобно оперировать понятием "типа" применительно к лямбда-выражениям.</span><span class="sxs-lookup"><span data-stu-id="4dd85-173">However, it is sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="4dd85-174">При этом под типом понимается тип делегата или тип <xref:System.Linq.Expressions.Expression> , в который преобразуется лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="4dd85-174">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>  
  
## <a name="variable-scope-in-lambda-expressions"></a><span data-ttu-id="4dd85-175">Область действия переменной в лямбда-выражениях</span><span class="sxs-lookup"><span data-stu-id="4dd85-175">Variable Scope in Lambda Expressions</span></span>  
 <span data-ttu-id="4dd85-176">Лямбда-выражения могут ссылаться на *внешние переменные* (см. раздел [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)), находящиеся в области метода, в котором определена лямбда-функция, или в области типа, который содержит лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="4dd85-176">Lambdas can refer to *outer variables* (see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)) that are in scope in the method that defines the lambda function, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="4dd85-177">Переменные, полученные таким способом, сохраняются для использования в лямбда-выражениях, даже если бы в ином случае они оказались за границами области действия и уничтожились сборщиком мусора.</span><span class="sxs-lookup"><span data-stu-id="4dd85-177">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="4dd85-178">Внешняя переменная должна быть определенным образом присвоена, прежде чем она сможет использоваться в лямбда-выражениях.</span><span class="sxs-lookup"><span data-stu-id="4dd85-178">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="4dd85-179">В следующем примере демонстрируются эти правила.</span><span class="sxs-lookup"><span data-stu-id="4dd85-179">The following example demonstrates these rules:</span></span>  
  
```csharp  
delegate bool D();  
delegate bool D2(int i);  
  
class Test  
{  
    D del;  
    D2 del2;  
    public void TestMethod(int input)  
    {  
        int j = 0;  
        // Initialize the delegates with lambda expressions.  
        // Note access to 2 outer variables.  
        // del will be invoked within this method.  
        del = () => { j = 10;  return j > input; };  
  
        // del2 will be invoked after TestMethod goes out of scope.  
        del2 = (x) => {return x == j; };  
  
        // Demonstrate value of j:  
        // Output: j = 0   
        // The delegate has not been invoked yet.  
        Console.WriteLine("j = {0}", j);        // Invoke the delegate.  
        bool boolResult = del();  
  
        // Output: j = 10 b = True  
        Console.WriteLine("j = {0}. b = {1}", j, boolResult);  
    }  
  
    static void Main()  
    {  
        Test test = new Test();  
        test.TestMethod(5);  
  
        // Prove that del2 still has a copy of  
        // local variable j from TestMethod.  
        bool result = test.del2(10);  
  
        // Output: True  
        Console.WriteLine(result);  
  
        Console.ReadKey();  
    }  
}  
```  
  
 <span data-ttu-id="4dd85-180">Следующие правила применимы к области действия переменной в лямбда-выражениях.</span><span class="sxs-lookup"><span data-stu-id="4dd85-180">The following rules apply to variable scope in lambda expressions:</span></span>  
  
-   <span data-ttu-id="4dd85-181">Захваченная переменная не будет уничтожена сборщиком мусора до тех пор, пока делегат, который на нее ссылается, не перейдет в статус подлежащего уничтожению при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="4dd85-181">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>  
  
-   <span data-ttu-id="4dd85-182">Переменные, вводимые в лямбда-выражении, невидимы во внешнем методе.</span><span class="sxs-lookup"><span data-stu-id="4dd85-182">Variables introduced within a lambda expression are not visible in the outer method.</span></span>  
  
-   <span data-ttu-id="4dd85-183">Лямбда-выражение не может непосредственно захватывать параметры `in`, `ref` или `out` из метода, в котором они находятся.</span><span class="sxs-lookup"><span data-stu-id="4dd85-183">A lambda expression cannot directly capture an `in`, `ref`, or `out` parameter from an enclosing method.</span></span>  
  
-   <span data-ttu-id="4dd85-184">Оператор return в лямбда-выражении не вызывает возвращение значения внешним методом.</span><span class="sxs-lookup"><span data-stu-id="4dd85-184">A return statement in a lambda expression does not cause the enclosing method to return.</span></span>  
  
-   <span data-ttu-id="4dd85-185">Лямбда-выражение не может содержать оператора `goto` , оператора `break` или оператора `continue` внутри лямбда-функции, если целевой объект перехода находится вне блока.</span><span class="sxs-lookup"><span data-stu-id="4dd85-185">A lambda expression cannot contain a `goto` statement, `break` statement, or `continue` statement that is inside the lambda function if the jump statement’s target is outside the block.</span></span> <span data-ttu-id="4dd85-186">Если целевой объект находится внутри блока, то наличие оператора перехода за пределами лямбда-функции также будет ошибкой.</span><span class="sxs-lookup"><span data-stu-id="4dd85-186">It is also an error to have a jump statement outside the lambda function block if the target is inside the block.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4dd85-187">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="4dd85-187">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapter"></a><span data-ttu-id="4dd85-188">Важная глава книги</span><span class="sxs-lookup"><span data-stu-id="4dd85-188">Featured Book Chapter</span></span>  
 <span data-ttu-id="4dd85-189">[Делегаты, события и лямбда-выражения](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) в [справочном руководстве по C# 3.0, третье издание: более 250 решений для программистов на C# 3.0](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span><span class="sxs-lookup"><span data-stu-id="4dd85-189">[Delegates, Events, and Lambda Expressions](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dd85-190">См. также</span><span class="sxs-lookup"><span data-stu-id="4dd85-190">See Also</span></span>  
 [<span data-ttu-id="4dd85-191">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4dd85-191">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4dd85-192">Встроенный язык запросов LINQ</span><span class="sxs-lookup"><span data-stu-id="4dd85-192">LINQ (Language-Integrated Query)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)  
 [<span data-ttu-id="4dd85-193">Анонимные методы</span><span class="sxs-lookup"><span data-stu-id="4dd85-193">Anonymous Methods</span></span>](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
 [<span data-ttu-id="4dd85-194">is</span><span class="sxs-lookup"><span data-stu-id="4dd85-194">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
 [<span data-ttu-id="4dd85-195">Деревья выражений</span><span class="sxs-lookup"><span data-stu-id="4dd85-195">Expression Trees</span></span>](../../../csharp/programming-guide/concepts/expression-trees/index.md)  
 [<span data-ttu-id="4dd85-196">Примеры C# в Visual Studio 2008 (см. файлы примеров запросов LINQ и программу XQuery)</span><span class="sxs-lookup"><span data-stu-id="4dd85-196">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](http://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)  
 [<span data-ttu-id="4dd85-197">Рекурсивные лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="4dd85-197">Recursive lambda expressions</span></span>](https://blogs.msdn.microsoft.com/madst/2007/05/11/recursive-lambda-expressions/)
