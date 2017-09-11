---
title: "Итераторы (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: f26b5c1e-fe9d-4004-b287-da7919d717ae
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c38609878c10ff3234b5a33ec44d678d24c11d7f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="iterators-visual-basic"></a><span data-ttu-id="8a647-102">Итераторы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a647-102">Iterators (Visual Basic)</span></span>
<span data-ttu-id="8a647-103">*Итератор* можно использовать для прохода по коллекции, такие как списки и массивы.</span><span class="sxs-lookup"><span data-stu-id="8a647-103">An *iterator* can be used to step through collections such as lists and arrays.</span></span>  
  
 <span data-ttu-id="8a647-104">Метод итератора или `get` доступа выполняющий настраиваемую итерацию по коллекции.</span><span class="sxs-lookup"><span data-stu-id="8a647-104">An iterator method or `get` accessor performs a custom iteration over a collection.</span></span> <span data-ttu-id="8a647-105">Использует метод итератора [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) инструкции для возврата каждого элемента одному за раз.</span><span class="sxs-lookup"><span data-stu-id="8a647-105">An iterator method uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="8a647-106">При `Yield` к оператору запоминается текущее расположение в коде.</span><span class="sxs-lookup"><span data-stu-id="8a647-106">When a `Yield` statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="8a647-107">Выполнение возобновляется с этого места при очередном вызове функции итератора.</span><span class="sxs-lookup"><span data-stu-id="8a647-107">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="8a647-108">Использовать итератор из клиентского кода с помощью [For Each... Далее](../../../visual-basic/language-reference/statements/for-each-next-statement.md) оператор, или с помощью запроса LINQ.</span><span class="sxs-lookup"><span data-stu-id="8a647-108">You consume an iterator from client code by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement, or by using a LINQ query.</span></span>  
  
 <span data-ttu-id="8a647-109">В следующем примере первой итерации `For Each` цикл приводит к выполнению перейти в `SomeNumbers` метода итератора до первого `Yield` к оператору.</span><span class="sxs-lookup"><span data-stu-id="8a647-109">In the following example, the first iteration of the `For Each` loop causes execution to proceed  in the `SomeNumbers` iterator method until the first `Yield` statement is reached.</span></span> <span data-ttu-id="8a647-110">Этой итерации возвращает значение 3, и сохраняется текущее расположение в методе итератора.</span><span class="sxs-lookup"><span data-stu-id="8a647-110">This iteration returns a value of 3, and the current location in the iterator method is retained.</span></span> <span data-ttu-id="8a647-111">На следующей итерации цикла, выполнение в методе итератора продолжается с места останавливается, еще раз при достижении `Yield` инструкции.</span><span class="sxs-lookup"><span data-stu-id="8a647-111">On the next iteration of the loop, execution in the iterator method continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="8a647-112">Этой итерации возвращает значение 5, и еще раз сохраняется текущее расположение в методе итератора.</span><span class="sxs-lookup"><span data-stu-id="8a647-112">This iteration returns a value of 5, and the current location in the iterator method is again retained.</span></span> <span data-ttu-id="8a647-113">При достижении конца метода итератора завершения цикла.</span><span class="sxs-lookup"><span data-stu-id="8a647-113">The loop completes when the end of the iterator method is reached.</span></span>  
  
```vb  
Sub Main()  
    For Each number As Integer In SomeNumbers()  
        Console.Write(number & " ")  
    Next  
    ' Output: 3 5 8  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function SomeNumbers() As System.Collections.IEnumerable  
    Yield 3  
    Yield 5  
    Yield 8  
End Function  
```  
  
 <span data-ttu-id="8a647-114">Возвращаемый тип метода итератора или `get` доступа может быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, или <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="8a647-114">The return type of an iterator method or `get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="8a647-115">Можно использовать `Exit Function` или `Return` инструкции для завершения итерации.</span><span class="sxs-lookup"><span data-stu-id="8a647-115">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="8a647-116">Итератор функции Visual Basic или `get` объявление метода доступа включает [итератор](../../../visual-basic/language-reference/modifiers/iterator.md) модификатор.</span><span class="sxs-lookup"><span data-stu-id="8a647-116">A Visual Basic iterator function or `get` accessor declaration includes an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
 <span data-ttu-id="8a647-117">Итераторы появились в Visual Basic в Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="8a647-117">Iterators were introduced in Visual Basic in Visual Studio 2012.</span></span>  
  
 <span data-ttu-id="8a647-118">**Содержание раздела**</span><span class="sxs-lookup"><span data-stu-id="8a647-118">**In this topic**</span></span>  
  
-   [<span data-ttu-id="8a647-119">Простой итератор</span><span class="sxs-lookup"><span data-stu-id="8a647-119">Simple Iterator</span></span>](#BKMK_SimpleIterator)  
  
-   [<span data-ttu-id="8a647-120">Создание класса коллекции</span><span class="sxs-lookup"><span data-stu-id="8a647-120">Creating a Collection Class</span></span>](#BKMK_CollectionClass)  
  
-   [<span data-ttu-id="8a647-121">Блоки try</span><span class="sxs-lookup"><span data-stu-id="8a647-121">Try Blocks</span></span>](#BKMK_TryBlocks)  
  
-   [<span data-ttu-id="8a647-122">Анонимные методы</span><span class="sxs-lookup"><span data-stu-id="8a647-122">Anonymous Methods</span></span>](#BKMK_AnonymousMethods)  
  
-   [<span data-ttu-id="8a647-123">Использование итераторов с универсальный список</span><span class="sxs-lookup"><span data-stu-id="8a647-123">Using Iterators with a Generic List</span></span>](#BKMK_GenericList)  
  
-   [<span data-ttu-id="8a647-124">Сведения о синтаксисе</span><span class="sxs-lookup"><span data-stu-id="8a647-124">Syntax Information</span></span>](#BKMK_SyntaxInformation)  
  
-   [<span data-ttu-id="8a647-125">Техническая реализация</span><span class="sxs-lookup"><span data-stu-id="8a647-125">Technical Implementation</span></span>](#BKMK_Technical)  
  
-   [<span data-ttu-id="8a647-126">Использование итераторов</span><span class="sxs-lookup"><span data-stu-id="8a647-126">Use of Iterators</span></span>](#BKMK_UseOfIterators)  
  
> [!NOTE]
>  <span data-ttu-id="8a647-127">Все примеры в разделе, за исключением того, в примере простой итератор включают [импорта](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) инструкции для `System.Collections` и `System.Collections.Generic` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="8a647-127">For all examples in the topic except the Simple Iterator example, include [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statements for the `System.Collections` and `System.Collections.Generic` namespaces.</span></span>  
  
##  <span data-ttu-id="8a647-128"><a name="BKMK_SimpleIterator"></a>Простой итератор</span><span class="sxs-lookup"><span data-stu-id="8a647-128"><a name="BKMK_SimpleIterator"></a> Simple Iterator</span></span>  
 <span data-ttu-id="8a647-129">В следующем примере имеется один `Yield` оператор, находящийся внутри [для... Далее](../../../visual-basic/language-reference/statements/for-next-statement.md) цикла.</span><span class="sxs-lookup"><span data-stu-id="8a647-129">The following example has a single `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="8a647-130">В `Main`, каждая итерация `For Each` тела оператора создает вызов функции итератора, который переходит к следующему `Yield` инструкции.</span><span class="sxs-lookup"><span data-stu-id="8a647-130">In `Main`, each iteration of the `For Each` statement body creates a call to the iterator function, which proceeds to the next `Yield` statement.</span></span>  
  
```vb  
Sub Main()  
    For Each number As Integer In EvenSequence(5, 18)  
        Console.Write(number & " ")  
    Next  
    ' Output: 6 8 10 12 14 16 18  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function EvenSequence(  
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _  
As System.Collections.Generic.IEnumerable(Of Integer)  
  
    ' Yield even numbers in the range.  
    For number As Integer = firstNumber To lastNumber  
        If number Mod 2 = 0 Then  
            Yield number  
        End If  
    Next  
End Function  
```  
  
##  <span data-ttu-id="8a647-131"><a name="BKMK_CollectionClass"></a>Создание класса коллекции</span><span class="sxs-lookup"><span data-stu-id="8a647-131"><a name="BKMK_CollectionClass"></a> Creating a Collection Class</span></span>  
 <span data-ttu-id="8a647-132">В следующем примере `DaysOfTheWeek` реализует <xref:System.Collections.IEnumerable>интерфейс, который требует <xref:System.Collections.IEnumerable.GetEnumerator%2A>метод.</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="8a647-132">In the following example, the `DaysOfTheWeek` class implements the <xref:System.Collections.IEnumerable> interface, which requires a <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="8a647-133">Компилятор неявно вызывает `GetEnumerator` метод, возвращающий <xref:System.Collections.IEnumerator>.</xref:System.Collections.IEnumerator></span><span class="sxs-lookup"><span data-stu-id="8a647-133">The compiler implicitly calls the `GetEnumerator` method, which returns an <xref:System.Collections.IEnumerator>.</span></span>  
  
 <span data-ttu-id="8a647-134">`GetEnumerator` Метод возвращает каждую строку, одним одновременно с помощью `Yield` инструкции и `Iterator` является модификатором в объявлении функции.</span><span class="sxs-lookup"><span data-stu-id="8a647-134">The `GetEnumerator` method returns each string one at a time by using the `Yield` statement, and  an `Iterator` modifier is in the function declaration.</span></span>  
  
```vb  
Sub Main()  
    Dim days As New DaysOfTheWeek()  
    For Each day As String In days  
        Console.Write(day & " ")  
    Next  
    ' Output: Sun Mon Tue Wed Thu Fri Sat  
    Console.ReadKey()  
End Sub  
  
Private Class DaysOfTheWeek  
    Implements IEnumerable  
  
    Public days =  
        New String() {"Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"}  
  
    Public Iterator Function GetEnumerator() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        ' Yield each day of the week.  
        For i As Integer = 0 To days.Length - 1  
            Yield days(i)  
        Next  
    End Function  
End Class  
```  
  
 <span data-ttu-id="8a647-135">В следующем примере создается `Zoo` класс, содержащий коллекцию животных.</span><span class="sxs-lookup"><span data-stu-id="8a647-135">The following example creates a `Zoo` class that contains a collection of animals.</span></span>  
  
 <span data-ttu-id="8a647-136">`For Each` Оператору, который ссылается на экземпляр класса (`theZoo`) неявно вызывает `GetEnumerator` метод.</span><span class="sxs-lookup"><span data-stu-id="8a647-136">The `For Each` statement that refers to the class instance (`theZoo`) implicitly calls the `GetEnumerator` method.</span></span> <span data-ttu-id="8a647-137">`For Each` Инструкций, ссылающихся на `Birds` и `Mammals` используют свойства `AnimalsForType` с именем метода итератора.</span><span class="sxs-lookup"><span data-stu-id="8a647-137">The `For Each` statements that refer to the `Birds` and `Mammals` properties use the `AnimalsForType` named iterator method.</span></span>  
  
```vb  
Sub Main()  
    Dim theZoo As New Zoo()  
  
    theZoo.AddMammal("Whale")  
    theZoo.AddMammal("Rhinoceros")  
    theZoo.AddBird("Penguin")  
    theZoo.AddBird("Warbler")  
  
    For Each name As String In theZoo  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Whale Rhinoceros Penguin Warbler  
  
    For Each name As String In theZoo.Birds  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Penguin Warbler  
  
    For Each name As String In theZoo.Mammals  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Whale Rhinoceros  
  
    Console.ReadKey()  
End Sub  
  
Public Class Zoo  
    Implements IEnumerable  
  
    ' Private members.  
    Private animals As New List(Of Animal)  
  
    ' Public methods.  
    Public Sub AddMammal(ByVal name As String)  
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Mammal})  
    End Sub  
  
    Public Sub AddBird(ByVal name As String)  
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Bird})  
    End Sub  
  
    Public Iterator Function GetEnumerator() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        For Each theAnimal As Animal In animals  
            Yield theAnimal.Name  
        Next  
    End Function  
  
    ' Public members.  
    Public ReadOnly Property Mammals As IEnumerable  
        Get  
            Return AnimalsForType(Animal.TypeEnum.Mammal)  
        End Get  
    End Property  
  
    Public ReadOnly Property Birds As IEnumerable  
        Get  
            Return AnimalsForType(Animal.TypeEnum.Bird)  
        End Get  
    End Property  
  
    ' Private methods.  
    Private Iterator Function AnimalsForType( _  
    ByVal type As Animal.TypeEnum) As IEnumerable  
        For Each theAnimal As Animal In animals  
            If (theAnimal.Type = type) Then  
                Yield theAnimal.Name  
            End If  
        Next  
    End Function  
  
    ' Private class.  
    Private Class Animal  
        Public Enum TypeEnum  
            Bird  
            Mammal  
        End Enum  
  
        Public Property Name As String  
        Public Property Type As TypeEnum  
    End Class  
End Class  
```  
  
##  <span data-ttu-id="8a647-138"><a name="BKMK_TryBlocks"></a>Блоки try</span><span class="sxs-lookup"><span data-stu-id="8a647-138"><a name="BKMK_TryBlocks"></a> Try Blocks</span></span>  
 <span data-ttu-id="8a647-139">Visual Basic позволяет `Yield` инструкции в `Try` блока [Try... CATCH... Оператор Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8a647-139">Visual Basic allows a `Yield` statement in the `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="8a647-140">Объект `Try` блок, который имеет `Yield` инструкция может иметь `Catch` блокируется и может иметь `Finally` блок.</span><span class="sxs-lookup"><span data-stu-id="8a647-140">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="8a647-141">Следующий пример включает `Try`, `Catch`, и `Finally` блоков в функции итератора.</span><span class="sxs-lookup"><span data-stu-id="8a647-141">The following example includes `Try`, `Catch`, and `Finally` blocks in an iterator function.</span></span> <span data-ttu-id="8a647-142">`Finally` Блок в функции итератора, выполняется перед `For Each` завершения итерации.</span><span class="sxs-lookup"><span data-stu-id="8a647-142">The `Finally` block in the iterator function executes before the `For Each` iteration finishes.</span></span>  
  
```vb  
Sub Main()  
    For Each number As Integer In Test()  
        Console.WriteLine(number)  
    Next  
    Console.WriteLine("For Each is done.")  
  
    ' Output:  
    '  3  
    '  4  
    '  Something happened. Yields are done.  
    '  Finally is called.  
    '  For Each is done.  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function Test() As IEnumerable(Of Integer)  
    Try  
        Yield 3  
        Yield 4  
        Throw New Exception("Something happened. Yields are done.")  
        Yield 5  
        Yield 6  
    Catch ex As Exception  
        Console.WriteLine(ex.Message)  
    Finally  
        Console.WriteLine("Finally is called.")  
    End Try  
End Function  
```  
  
 <span data-ttu-id="8a647-143">Объект `Yield` оператор не может находиться внутри `Catch` блока или `Finally` блока.</span><span class="sxs-lookup"><span data-stu-id="8a647-143">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="8a647-144">Если `For Each` текст (вместо метода итератора) вызывает исключение, `Catch` блок в функции итератора не выполняется, но `Finally` выполняется блок в функции итератора.</span><span class="sxs-lookup"><span data-stu-id="8a647-144">If the `For Each` body (instead of the iterator method) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="8a647-145">A `Catch` блок внутри функции итератора перехватывает только исключения, которые возникают внутри функции итератора.</span><span class="sxs-lookup"><span data-stu-id="8a647-145">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
##  <span data-ttu-id="8a647-146"><a name="BKMK_AnonymousMethods"></a>Анонимные методы</span><span class="sxs-lookup"><span data-stu-id="8a647-146"><a name="BKMK_AnonymousMethods"></a> Anonymous Methods</span></span>  
 <span data-ttu-id="8a647-147">В Visual Basic анонимная функция может быть функцией итератора.</span><span class="sxs-lookup"><span data-stu-id="8a647-147">In Visual Basic, an anonymous function can be an iterator function.</span></span> <span data-ttu-id="8a647-148">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8a647-148">The following example illustrates this.</span></span>  
  
```vb  
Dim iterateSequence = Iterator Function() _  
                      As IEnumerable(Of Integer)  
                          Yield 1  
                          Yield 2  
                      End Function  
  
For Each number As Integer In iterateSequence()  
    Console.Write(number & " ")  
Next  
' Output: 1 2  
Console.ReadKey()  
```  
  
 <span data-ttu-id="8a647-149">В следующем примере имеется метод не итератор, который проверяет аргументы.</span><span class="sxs-lookup"><span data-stu-id="8a647-149">The following example has a non-iterator method that validates the arguments.</span></span> <span data-ttu-id="8a647-150">Метод возвращает результат анонимный итератора, который описывает элементы коллекции.</span><span class="sxs-lookup"><span data-stu-id="8a647-150">The method returns the result of an anonymous iterator that describes the collection elements.</span></span>  
  
```vb  
Sub Main()  
    For Each number As Integer In GetSequence(5, 10)  
        Console.Write(number & " ")  
    Next  
    ' Output: 5 6 7 8 9 10  
    Console.ReadKey()  
End Sub  
  
Public Function GetSequence(ByVal low As Integer, ByVal high As Integer) _  
As IEnumerable  
    ' Validate the arguments.  
    If low < 1 Then  
        Throw New ArgumentException("low is too low")  
    End If  
    If high > 140 Then  
        Throw New ArgumentException("high is too high")  
    End If  
  
    ' Return an anonymous iterator function.  
    Dim iterateSequence = Iterator Function() As IEnumerable  
                              For index = low To high  
                                  Yield index  
                              Next  
                          End Function  
    Return iterateSequence()  
End Function  
```  
  
 <span data-ttu-id="8a647-151">Если проверка находится внутри функции итератора, проверка не может выполняться до начала первой итерации `For Each` текста.</span><span class="sxs-lookup"><span data-stu-id="8a647-151">If validation is instead inside the iterator function, the validation cannot be performed until the start of the first iteration of the `For Each` body.</span></span>  
  
##  <span data-ttu-id="8a647-152"><a name="BKMK_GenericList"></a>Использование итераторов с универсальный список</span><span class="sxs-lookup"><span data-stu-id="8a647-152"><a name="BKMK_GenericList"></a> Using Iterators with a Generic List</span></span>  
 <span data-ttu-id="8a647-153">В следующем примере `Stack(Of T)` реализует универсальный класс <xref:System.Collections.Generic.IEnumerable%601>универсальный интерфейс.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="8a647-153">In the following example, the `Stack(Of T)` generic class implements the <xref:System.Collections.Generic.IEnumerable%601> generic interface.</span></span> <span data-ttu-id="8a647-154">`Push` Метод присваивает значения массивом типа `T`.</span><span class="sxs-lookup"><span data-stu-id="8a647-154">The `Push` method assigns values to an array of type `T`.</span></span> <span data-ttu-id="8a647-155"><xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>Метод возвращает массив значений с помощью `Yield` инструкции.</xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="8a647-155">The <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method returns the array values by using the `Yield` statement.</span></span>  
  
 <span data-ttu-id="8a647-156">Помимо универсальный <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>метод, неуниверсальные <xref:System.Collections.IEnumerable.GetEnumerator%2A>также должен быть реализован метод.</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="8a647-156">In addition to the generic <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method, the non-generic <xref:System.Collections.IEnumerable.GetEnumerator%2A> method must also be implemented.</span></span> <span data-ttu-id="8a647-157">Это обусловлено <xref:System.Collections.Generic.IEnumerable%601>наследует <xref:System.Collections.IEnumerable>.</xref:System.Collections.IEnumerable> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="8a647-157">This is because <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="8a647-158">Реализация неуниверсального откладывает универсальные реализации.</span><span class="sxs-lookup"><span data-stu-id="8a647-158">The non-generic implementation defers to the generic implementation.</span></span>  
  
 <span data-ttu-id="8a647-159">В примере именованные итераторы для поддержки различных возможностей перебора одной коллекции данных.</span><span class="sxs-lookup"><span data-stu-id="8a647-159">The example uses named iterators to support various ways of iterating through the same collection of data.</span></span> <span data-ttu-id="8a647-160">Эти итераторы с именем `TopToBottom` и `BottomToTop` свойства и `TopN` метод.</span><span class="sxs-lookup"><span data-stu-id="8a647-160">These named iterators are the `TopToBottom` and `BottomToTop` properties, and the `TopN` method.</span></span>  
  
 <span data-ttu-id="8a647-161">`BottomToTop` Содержит объявление свойства `Iterator` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="8a647-161">The `BottomToTop` property declaration includes the `Iterator` keyword.</span></span>  
  
```vb  
Sub Main()  
    Dim theStack As New Stack(Of Integer)  
  
    ' Add items to the stack.  
    For number As Integer = 0 To 9  
        theStack.Push(number)  
    Next  
  
    ' Retrieve items from the stack.  
    ' For Each is allowed because theStack implements  
    ' IEnumerable(Of Integer).  
    For Each number As Integer In theStack  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3 2 1 0  
  
    ' For Each is allowed, because theStack.TopToBottom  
    ' returns IEnumerable(Of Integer).  
    For Each number As Integer In theStack.TopToBottom  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3 2 1 0  
  
    For Each number As Integer In theStack.BottomToTop  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 0 1 2 3 4 5 6 7 8 9   
  
    For Each number As Integer In theStack.TopN(7)  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3  
  
    Console.ReadKey()  
End Sub  
  
Public Class Stack(Of T)  
    Implements IEnumerable(Of T)  
  
    Private values As T() = New T(99) {}  
    Private top As Integer = 0  
  
    Public Sub Push(ByVal t As T)  
        values(top) = t  
        top = top + 1  
    End Sub  
  
    Public Function Pop() As T  
        top = top - 1  
        Return values(top)  
    End Function  
  
    ' This function implements the GetEnumerator method. It allows  
    ' an instance of the class to be used in a For Each statement.  
    Public Iterator Function GetEnumerator() As IEnumerator(Of T) _  
        Implements IEnumerable(Of T).GetEnumerator  
  
        For index As Integer = top - 1 To 0 Step -1  
            Yield values(index)  
        Next  
    End Function  
  
    Public Iterator Function GetEnumerator1() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        Yield GetEnumerator()  
    End Function  
  
    Public ReadOnly Property TopToBottom() As IEnumerable(Of T)  
        Get  
            Return Me  
        End Get  
    End Property  
  
    Public ReadOnly Iterator Property BottomToTop As IEnumerable(Of T)  
        Get  
            For index As Integer = 0 To top - 1  
                Yield values(index)  
            Next  
        End Get  
    End Property  
  
    Public Iterator Function TopN(ByVal itemsFromTop As Integer) _  
        As IEnumerable(Of T)  
  
        ' Return less than itemsFromTop if necessary.  
        Dim startIndex As Integer =  
            If(itemsFromTop >= top, 0, top - itemsFromTop)  
  
        For index As Integer = top - 1 To startIndex Step -1  
            Yield values(index)  
        Next  
    End Function  
End Class  
  
```  
  
##  <span data-ttu-id="8a647-162"><a name="BKMK_SyntaxInformation"></a>Сведения о синтаксисе</span><span class="sxs-lookup"><span data-stu-id="8a647-162"><a name="BKMK_SyntaxInformation"></a> Syntax Information</span></span>  
 <span data-ttu-id="8a647-163">Итератор может возникать как метод или `get` доступа.</span><span class="sxs-lookup"><span data-stu-id="8a647-163">An iterator can occur as a method or `get` accessor.</span></span> <span data-ttu-id="8a647-164">Итератор не может содержаться событие, конструктор экземпляра, статический конструктор или статический деструктор.</span><span class="sxs-lookup"><span data-stu-id="8a647-164">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="8a647-165">Должно существовать неявное преобразование из типа выражения в `Yield` инструкции в возвращаемый тип итератора.</span><span class="sxs-lookup"><span data-stu-id="8a647-165">An implicit conversion must exist from the expression type in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="8a647-166">В Visual Basic метод итератора не может содержать `ByRef` параметров.</span><span class="sxs-lookup"><span data-stu-id="8a647-166">In Visual Basic, an iterator method cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="8a647-167">В Visual Basic «Доход» не является зарезервированным словом и имеет специальное значение только в том случае, если он используется в `Iterator` метода или `get` доступа.</span><span class="sxs-lookup"><span data-stu-id="8a647-167">In Visual Basic, "Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` method or `get` accessor.</span></span>  
  
##  <span data-ttu-id="8a647-168"><a name="BKMK_Technical"></a>Техническая реализация</span><span class="sxs-lookup"><span data-stu-id="8a647-168"><a name="BKMK_Technical"></a> Technical Implementation</span></span>  
 <span data-ttu-id="8a647-169">Несмотря на то, что итератор создается как метод, компилятор преобразует его в вложенного класса и в результате, конечный автомат.</span><span class="sxs-lookup"><span data-stu-id="8a647-169">Although you write an iterator as a method, the compiler translates it into a nested class that is, in effect, a state machine.</span></span> <span data-ttu-id="8a647-170">Этот класс данные о позиции итератора, как долго `For Each...Next` продолжает цикл в коде клиента.</span><span class="sxs-lookup"><span data-stu-id="8a647-170">This class keeps track of the position of the iterator as long the `For Each...Next` loop in the client code continues.</span></span>  
  
 <span data-ttu-id="8a647-171">Чтобы увидеть, компилятор выполняет, можно использовать средство Ildasm.exe для отображения кода промежуточного языка Microsoft, созданный для метода итератора.</span><span class="sxs-lookup"><span data-stu-id="8a647-171">To see what the compiler does, you can use the Ildasm.exe tool to view the Microsoft intermediate language code that is generated for an iterator method.</span></span>  
  
 <span data-ttu-id="8a647-172">При создании итератора для [класса](../../../csharp/language-reference/keywords/class.md) или [структуры](../../../csharp/language-reference/keywords/struct.md), необходимо реализовать весь <xref:System.Collections.IEnumerator>интерфейса.</xref:System.Collections.IEnumerator></span><span class="sxs-lookup"><span data-stu-id="8a647-172">When you create an iterator for a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md), you do not have to implement the whole <xref:System.Collections.IEnumerator> interface.</span></span> <span data-ttu-id="8a647-173">Когда компилятор обнаруживает итератора, он автоматически создает `Current`, `MoveNext`, и `Dispose` методов <xref:System.Collections.IEnumerator>или <xref:System.Collections.Generic.IEnumerator%601>интерфейса.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator></span><span class="sxs-lookup"><span data-stu-id="8a647-173">When the compiler detects the iterator, it automatically generates the `Current`, `MoveNext`, and `Dispose` methods of the <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> interface.</span></span>  
  
 <span data-ttu-id="8a647-174">В последующих итерациях из `For Each…Next` цикла (или прямом вызове `IEnumerator.MoveNext`), следующий текст кода итератора возобновляется после предыдущего `Yield` инструкции.</span><span class="sxs-lookup"><span data-stu-id="8a647-174">On each successive iteration of the `For Each…Next` loop (or the direct call to `IEnumerator.MoveNext`), the next iterator code body resumes after the previous `Yield` statement.</span></span> <span data-ttu-id="8a647-175">Перейдет к следующему `Yield` инструкции, пока не будет достигнут конец тела итератора, пока не `Exit Function` или `Return` встречается оператор.</span><span class="sxs-lookup"><span data-stu-id="8a647-175">It then continues to the next `Yield` statement until the end of the iterator body is reached, or until an `Exit Function` or `Return` statement is encountered.</span></span>  
  
 <span data-ttu-id="8a647-176">Итераторы не поддерживают <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName>метод.</xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="8a647-176">Iterators do not support the <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="8a647-177">Для повторной итерации с самого начала, необходимо получить новый итератор.</span><span class="sxs-lookup"><span data-stu-id="8a647-177">To re-iterate from the start, you must obtain a new iterator.</span></span>  
  
 <span data-ttu-id="8a647-178">Дополнительные сведения см. в разделе [спецификация языка Visual Basic](../../../visual-basic/reference/language-specification.md).</span><span class="sxs-lookup"><span data-stu-id="8a647-178">For additional information, see the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification.md).</span></span>  
  
##  <span data-ttu-id="8a647-179"><a name="BKMK_UseOfIterators"></a>Использование итераторов</span><span class="sxs-lookup"><span data-stu-id="8a647-179"><a name="BKMK_UseOfIterators"></a> Use of Iterators</span></span>  
 <span data-ttu-id="8a647-180">Итераторы позволяют поддерживать простоту `For Each` цикл, когда необходимо использовать сложный код для заполнения списка последовательности.</span><span class="sxs-lookup"><span data-stu-id="8a647-180">Iterators enable you to maintain the simplicity of a `For Each` loop when you need to use complex code to populate a list sequence.</span></span> <span data-ttu-id="8a647-181">Это может быть полезно, когда необходимо сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="8a647-181">This can be useful when you want to do the following:</span></span>  
  
-   <span data-ttu-id="8a647-182">Изменение последовательности список после первого `For Each` итерации цикла.</span><span class="sxs-lookup"><span data-stu-id="8a647-182">Modify the list sequence after the first `For Each` loop iteration.</span></span>  
  
-   <span data-ttu-id="8a647-183">Избежать полной загрузки большого списка перед первой итерацией `For Each` цикла.</span><span class="sxs-lookup"><span data-stu-id="8a647-183">Avoid fully loading a large list before the first iteration of a `For Each` loop.</span></span> <span data-ttu-id="8a647-184">Например, разбитых на страницы выборки для загрузки пакета строк таблицы.</span><span class="sxs-lookup"><span data-stu-id="8a647-184">An example is a paged fetch to load a batch of table rows.</span></span> <span data-ttu-id="8a647-185">Другой пример — <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>метод, который реализует итераторы в .NET Framework.</xref:System.IO.DirectoryInfo.EnumerateFiles%2A></span><span class="sxs-lookup"><span data-stu-id="8a647-185">Another example is the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> method, which implements iterators within the .NET Framework.</span></span>  
  
-   <span data-ttu-id="8a647-186">Инкапсуляция, Создание списка в итераторе.</span><span class="sxs-lookup"><span data-stu-id="8a647-186">Encapsulate building the list in the iterator.</span></span> <span data-ttu-id="8a647-187">В методе итератора можно составить список и затем выдает каждый результат в цикле.</span><span class="sxs-lookup"><span data-stu-id="8a647-187">In the iterator method, you can build the list and then yield each result in a loop.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a647-188">См. также</span><span class="sxs-lookup"><span data-stu-id="8a647-188">See Also</span></span>  
 <span data-ttu-id="8a647-189"><xref:System.Collections.Generic></xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="8a647-189"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="8a647-190"><xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="8a647-190"><xref:System.Collections.Generic.IEnumerable%601></span></span>   
<span data-ttu-id="8a647-191"> [Для каждого... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8a647-191"> [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span></span>  
<span data-ttu-id="8a647-192"> [Оператор yield](../../../visual-basic/language-reference/statements/yield-statement.md) </span><span class="sxs-lookup"><span data-stu-id="8a647-192"> [Yield Statement](../../../visual-basic/language-reference/statements/yield-statement.md) </span></span>  
<span data-ttu-id="8a647-193"> [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md)</span><span class="sxs-lookup"><span data-stu-id="8a647-193"> [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md)</span></span>
