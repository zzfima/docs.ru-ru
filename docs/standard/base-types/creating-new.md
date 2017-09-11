---
title: "Создание новых строк"
description: "Создание новых строк"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 639397c7-e694-43e0-845b-1681c62bd9fd
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 793b5bc4b26967104459fa2559c6127bb82f3a9d
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="creating-new-strings"></a><span data-ttu-id="2a950-104">Создание новых строк</span><span class="sxs-lookup"><span data-stu-id="2a950-104">Creating new strings</span></span>

<span data-ttu-id="2a950-105">. NET позволяет создавать строки с помощью простой операции присваивания, а также перегружать конструктор класса для создания строк с помощью нескольких различных параметров.</span><span class="sxs-lookup"><span data-stu-id="2a950-105">.NET  allows strings to be created using simple assignment, and also overloads a class constructor to support string creation using a number of different parameters.</span></span> <span data-ttu-id="2a950-106">Кроме того, в классе [System.String](xref:System.String) .NET имеются методы для создания строковых объектов путем объединения нескольких строк, массивов строк или объектов.</span><span class="sxs-lookup"><span data-stu-id="2a950-106">.NET also provides several methods in the [System.String](xref:System.String) class that create new string objects by combining several strings, arrays of strings, or objects.</span></span> 

## <a name="creating-strings-using-assignment"></a><span data-ttu-id="2a950-107">Создание строк с помощью присваивания</span><span class="sxs-lookup"><span data-stu-id="2a950-107">Creating Strings Using Assignment</span></span>

<span data-ttu-id="2a950-108">Самый простой способ создать новый объект [String](xref:System.String) — присвоить строковый литерал объекту [String](xref:System.String).</span><span class="sxs-lookup"><span data-stu-id="2a950-108">The easiest way to create a new [String](xref:System.String) object is simply to assign a string literal to a [String](xref:System.String) object.</span></span> 

## <a name="creating-strings-using-a-class-constructor"></a><span data-ttu-id="2a950-109">Создание строк с помощью конструктора класса</span><span class="sxs-lookup"><span data-stu-id="2a950-109">Creating Strings Using a Class Constructor</span></span>

<span data-ttu-id="2a950-110">С помощью перегруженного конструктора класса [String](xref:System.String) можно создавать строки из массивов символов.</span><span class="sxs-lookup"><span data-stu-id="2a950-110">You can use overloads of the [String](xref:System.String) class constructor to create strings from character arrays.</span></span> <span data-ttu-id="2a950-111">Кроме того, строки можно создавать путем копирования того или иного знака указанное количество раз.</span><span class="sxs-lookup"><span data-stu-id="2a950-111">You can also create a new string by duplicating a particular character a specified number of times.</span></span> 

## <a name="methods-that-return-strings"></a><span data-ttu-id="2a950-112">Методы, возвращающие строки</span><span class="sxs-lookup"><span data-stu-id="2a950-112">Methods that Return Strings</span></span>

<span data-ttu-id="2a950-113">В следующей таблице перечислено несколько полезных методов, которые возвращают строковые объекты.</span><span class="sxs-lookup"><span data-stu-id="2a950-113">The following table lists several useful methods that return new string objects.</span></span>

<span data-ttu-id="2a950-114">Имя метода</span><span class="sxs-lookup"><span data-stu-id="2a950-114">Method name</span></span> | <span data-ttu-id="2a950-115">Применение</span><span class="sxs-lookup"><span data-stu-id="2a950-115">Use</span></span>
----------- | ---
<span data-ttu-id="2a950-116">[String.Format](xref:System.String.Format(System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="2a950-116">[String.Format](xref:System.String.Format(System.String,System.Object))</span></span> | <span data-ttu-id="2a950-117">Создание форматированной строки из набора объектов ввода.</span><span class="sxs-lookup"><span data-stu-id="2a950-117">Builds a formatted string from a set of input objects.</span></span>
<span data-ttu-id="2a950-118">[String.Concat](xref:System.String.Concat(System.String,System.String))</span><span class="sxs-lookup"><span data-stu-id="2a950-118">[String.Concat](xref:System.String.Concat(System.String,System.String))</span></span> | <span data-ttu-id="2a950-119">Создание строк из двух или более строк.</span><span class="sxs-lookup"><span data-stu-id="2a950-119">Builds strings from two or more strings.</span></span>
<span data-ttu-id="2a950-120">[String.Join](xref:System.String.Join(System.String,System.String[]))</span><span class="sxs-lookup"><span data-stu-id="2a950-120">[String.Join](xref:System.String.Join(System.String,System.String[]))</span></span> |<span data-ttu-id="2a950-121">Создание новой строки с помощью объединения массива строк.</span><span class="sxs-lookup"><span data-stu-id="2a950-121">Builds a new string by combining an array of strings.</span></span>
<span data-ttu-id="2a950-122">[String.Insert](xref:System.String.Insert(System.Int32,System.String))</span><span class="sxs-lookup"><span data-stu-id="2a950-122">[String.Insert](xref:System.String.Insert(System.Int32,System.String))</span></span> | <span data-ttu-id="2a950-123">Создание новой строки с помощью вставки строки в указанную позицию существующей строки.</span><span class="sxs-lookup"><span data-stu-id="2a950-123">Builds a new string by inserting a string into the specified index of an existing string.</span></span>
<span data-ttu-id="2a950-124">[String.CopyTo](xref:System.String.CopyTo(System.Int32,System.Char[],System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="2a950-124">[String.CopyTo](xref:System.String.CopyTo(System.Int32,System.Char[],System.Int32,System.Int32))</span></span> | <span data-ttu-id="2a950-125">Копирование указанных знаков в строке в указанную позицию в массиве символов.</span><span class="sxs-lookup"><span data-stu-id="2a950-125">Copies specified characters in a string into a specified position in an array of characters.</span></span>

### <a name="format"></a><span data-ttu-id="2a950-126">Формат</span><span class="sxs-lookup"><span data-stu-id="2a950-126">Format</span></span>

<span data-ttu-id="2a950-127">Метод `String.Format` используется для создания форматированных строк и соединения строк, представляющих несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="2a950-127">You can use the `String.Format` method to create formatted strings and concatenate strings representing multiple objects.</span></span> <span data-ttu-id="2a950-128">Этот метод автоматически преобразует в строку любой переданный объект.</span><span class="sxs-lookup"><span data-stu-id="2a950-128">This method automatically converts any passed object into a string.</span></span> <span data-ttu-id="2a950-129">Например, если приложению необходимо отобразить для пользователя значение [Int32](xref:System.Int32) и значение [DateTime](xref:System.DateTime), с помощью метода `Format` можно легко создать строку для представления этих значений.</span><span class="sxs-lookup"><span data-stu-id="2a950-129">For example, if your application must display an [Int32](xref:System.Int32) value and a [DateTime](xref:System.DateTime) value to the user, you can easily construct a string to represent these values using the `Format` method.</span></span> <span data-ttu-id="2a950-130">Сведения о правилах форматирования, используемых в этом методе, см. в разделе [Составное форматирование](composite-format.md).</span><span class="sxs-lookup"><span data-stu-id="2a950-130">For information about formatting conventions used with this method, see the section on [composite formatting](composite-format.md).</span></span>

<span data-ttu-id="2a950-131">В следующем примере метод `Format` используется для создания строки, содержащей целочисленную переменную.</span><span class="sxs-lookup"><span data-stu-id="2a950-131">The following example uses the `Format` method to create a string that uses an integer variable.</span></span>

```csharp
int numberOfFleas = 12;
string miscInfo = String.Format("Your dog has {0} fleas. " +
                                "It is time to get a flea collar. " + 
                                "The current universal date is: {1:u}.", 
                                numberOfFleas, DateTime.Now);
Console.WriteLine(miscInfo);
// The example displays the following output:
//       Your dog has 12 fleas. It is time to get a flea collar. 
//       The current universal date is: 2008-03-28 13:31:40Z.
```

```vb
Dim numberOfFleas As Integer = 12
Dim miscInfo As String = String.Format("Your dog has {0} fleas. " & _
                                       "It is time to get a flea collar. " & _ 
                                       "The current universal date is: {1:u}.", _ 
                                       numberOfFleas, Date.Now)
Console.WriteLine(miscInfo)
' The example displays the following output:
'       Your dog has 12 fleas. It is time to get a flea collar. 
'       The current universal date is: 2008-03-28 13:31:40Z.
```

<span data-ttu-id="2a950-132">В этом примере значение [DateTime.Now](xref:System.DateTime.Now) отображает текущую дату и время в соответствии с языком и региональными параметрами, связанными с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="2a950-132">In this example, [DateTime.Now](xref:System.DateTime.Now) displays the current date and time in a manner specified by the culture associated with the current thread.</span></span>

### <a name="concat"></a><span data-ttu-id="2a950-133">Concat</span><span class="sxs-lookup"><span data-stu-id="2a950-133">Concat</span></span>

<span data-ttu-id="2a950-134">Метод `String.Concat` используется для простого создания нового объекта строки из двух или более существующих объектов.</span><span class="sxs-lookup"><span data-stu-id="2a950-134">The `String.Concat` method can be used to easily create a new string object from two or more existing objects.</span></span> <span data-ttu-id="2a950-135">Он позволяет использовать независимый от языка способ сцепления строк.</span><span class="sxs-lookup"><span data-stu-id="2a950-135">It provides a language-independent way to concatenate strings.</span></span> <span data-ttu-id="2a950-136">Этот метод принимает любой класс, производный от `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="2a950-136">This method accepts any class that derives from `System.Object`.</span></span> <span data-ttu-id="2a950-137">В следующем примере создается строка из двух существующих объектов строки и символа разделителя.</span><span class="sxs-lookup"><span data-stu-id="2a950-137">The following example creates a string from two existing string objects and a separating character.</span></span>

```csharp
string helloString1 = "Hello";
string helloString2 = "World!";
Console.WriteLine(String.Concat(helloString1, ' ', helloString2));
// The example displays the following output:
//      Hello World!
```

```vb
Dim helloString1 As String = "Hello"
Dim helloString2 As String = "World!"
Console.WriteLine(String.Concat(helloString1, " "c, helloString2))
' The example displays the following output:
'      Hello World!
```

### <a name="join"></a><span data-ttu-id="2a950-138">Join</span><span class="sxs-lookup"><span data-stu-id="2a950-138">Join</span></span>

<span data-ttu-id="2a950-139">Метод `String.Join` создает новую строку из массива строк и разделительной строки.</span><span class="sxs-lookup"><span data-stu-id="2a950-139">The `String.Join` method creates a new string from an array of strings and a separator string.</span></span> <span data-ttu-id="2a950-140">Этот метод полезен в случае необходимости сцепления нескольких строк и создания списка, отделенного, например, запятой.</span><span class="sxs-lookup"><span data-stu-id="2a950-140">This method is useful if you want to concatenate multiple strings together, making a list perhaps separated by a comma.</span></span>

<span data-ttu-id="2a950-141">В следующем примере используется пробел для привязки массива строк.</span><span class="sxs-lookup"><span data-stu-id="2a950-141">The following example uses a space to bind a string array.</span></span>

```csharp
string[] words = {"Hello", "and", "welcome", "to", "my" , "world!"};
Console.WriteLine(String.Join(" ", words));
// The example displays the following output:
//      Hello and welcome to my world!
```

```vb
Dim words() As String = {"Hello", "and", "welcome", "to", "my" , "world!"}
Console.WriteLine(String.Join(" ", words))
' The example displays the following output:
'      Hello and welcome to my world!
```

### <a name="insert"></a><span data-ttu-id="2a950-142">Insert</span><span class="sxs-lookup"><span data-stu-id="2a950-142">Insert</span></span>

<span data-ttu-id="2a950-143">Метод `String.Insert` создает новую строку с помощью вставки строки в указанную позицию в другой строке.</span><span class="sxs-lookup"><span data-stu-id="2a950-143">The `String.Insert` method creates a new string by inserting a string into a specified position in another string.</span></span> <span data-ttu-id="2a950-144">Этот метод использует отсчитываемый от нуля индекс.</span><span class="sxs-lookup"><span data-stu-id="2a950-144">This method uses a zero-based index.</span></span> <span data-ttu-id="2a950-145">В следующем примере строка вставляется в пятую позицию индекса `MyString`, и создается новая строка с этим значением.</span><span class="sxs-lookup"><span data-stu-id="2a950-145">The following example inserts a string into the fifth index position of `MyString` and creates a new string with this value.</span></span>

```csharp
string sentence = "Once a time.";   
 Console.WriteLine(sentence.Insert(4, " upon"));
 // The example displays the following output:
 //      Once upon a time.
```

```vb
Dim sentence As String = "Once a time."   
 Console.WriteLine(sentence.Insert(4, " upon"))
 ' The example displays the 
```

### <a name="copyto"></a><span data-ttu-id="2a950-146">CopyTo</span><span class="sxs-lookup"><span data-stu-id="2a950-146">CopyTo</span></span>

<span data-ttu-id="2a950-147">Метод `String.CopyTo` копирует часть строки в массив символов.</span><span class="sxs-lookup"><span data-stu-id="2a950-147">The `String.CopyTo` method copies portions of a string into an array of characters.</span></span> <span data-ttu-id="2a950-148">Можно указать начальный индекс строки и число копируемых символов.</span><span class="sxs-lookup"><span data-stu-id="2a950-148">You can specify both the beginning index of the string and the number of characters to be copied.</span></span> <span data-ttu-id="2a950-149">Для копирования этому методу необходимы исходный индекс, массив знаков, индекс назначения и число символов.</span><span class="sxs-lookup"><span data-stu-id="2a950-149">This method takes the source index, an array of characters, the destination index, and the number of characters to copy.</span></span> <span data-ttu-id="2a950-150">Все индексы отсчитываются от нуля.</span><span class="sxs-lookup"><span data-stu-id="2a950-150">All indexes are zero-based.</span></span>

<span data-ttu-id="2a950-151">В следующем примере метод `CopyTo` используется для копирования символов слова "Hello" из объекта строки в первую позицию индекса массива символов.</span><span class="sxs-lookup"><span data-stu-id="2a950-151">The following example uses the `CopyTo` method to copy the characters of the word "Hello" from a string object to the first index position of an array of characters.</span></span>

```csharp
string greeting = "Hello World!";
char[] charArray = {'W','h','e','r','e'};
Console.WriteLine("The original character array: {0}", new string(charArray));
greeting.CopyTo(0, charArray,0 ,5);
Console.WriteLine("The new character array: {0}", new string(charArray));
// The example displays the following output:
//       The original character array: Where
//       The new character array: Hello
```

```vb
Dim greeting As String = "Hello World!"
Dim charArray() As Char = {"W"c, "h"c, "e"c, "r"c, "e"c}
Console.WriteLine("The original character array: {0}", New String(charArray))
greeting.CopyTo(0, charArray,0 ,5)
Console.WriteLine("The new character array: {0}", New String(charArray))
' The example displays the following output:
'       The original character array: Where
'       The new character array: Hello
```

## <a name="see-also"></a><span data-ttu-id="2a950-152">См. также</span><span class="sxs-lookup"><span data-stu-id="2a950-152">See Also</span></span>

[<span data-ttu-id="2a950-153">Базовые операции со строками</span><span class="sxs-lookup"><span data-stu-id="2a950-153">Basic string operations</span></span>](basic-string-operations.md)

[<span data-ttu-id="2a950-154">Составное форматирование</span><span class="sxs-lookup"><span data-stu-id="2a950-154">Composite formatting</span></span>](composite-format.md)


