---
title: "Использование класса StringBuilder"
description: "Использование класса StringBuilder"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: f4f5d1c7-d84d-4867-810f-2708cd6de0da
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 076e10e095b50cc96187f2ec13ade2365d83dad3
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="using-the-stringbuilder-class"></a><span data-ttu-id="489a6-104">Использование класса StringBuilder</span><span class="sxs-lookup"><span data-stu-id="489a6-104">Using the StringBuilder class</span></span>

<span data-ttu-id="489a6-105">Объект [String](xref:System.String) является неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="489a6-105">The [String](xref:System.String) object is immutable.</span></span> <span data-ttu-id="489a6-106">Каждый раз при использовании одного из методов в классе [System.String](xref:System.String) вы создаете новый объект строки в памяти. При этом для нового объекта требуется новое выделение пространства.</span><span class="sxs-lookup"><span data-stu-id="489a6-106">Every time you use one of the methods in the [System.String](xref:System.String) class, you create a new string object in memory, which requires a new allocation of space for that new object.</span></span> <span data-ttu-id="489a6-107">В тех случаях, когда необходимо выполнять повторяющиеся модификации строки, издержки, связанные с созданием нового объекта [String](xref:System.String), могут оказаться значительными.</span><span class="sxs-lookup"><span data-stu-id="489a6-107">In situations where you need to perform repeated modifications to a string, the overhead associated with creating a new [String](xref:System.String) object can be costly.</span></span> <span data-ttu-id="489a6-108">Чтобы изменять строку без создания нового объекта, можно использовать класс [System.Text.StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="489a6-108">The [System.Text.StringBuilder](xref:System.Text.StringBuilder) class can be used when you want to modify a string without creating a new object.</span></span> <span data-ttu-id="489a6-109">Например, использование класса [StringBuilder](xref:System.Text.StringBuilder) может повысить производительность при соединении большого количества строк в цикле.</span><span class="sxs-lookup"><span data-stu-id="489a6-109">For example, using the [StringBuilder](xref:System.Text.StringBuilder) class can boost performance when concatenating many strings together in a loop.</span></span>

## <a name="importing-the-systemtext-namespace"></a><span data-ttu-id="489a6-110">Импорт пространства имен System.Text</span><span class="sxs-lookup"><span data-stu-id="489a6-110">Importing the System.Text Namespace</span></span>

<span data-ttu-id="489a6-111">Класс [StringBuilder](xref:System.Text.StringBuilder) находится в пространстве имен [System.Text](xref:System.Text).</span><span class="sxs-lookup"><span data-stu-id="489a6-111">The [StringBuilder](xref:System.Text.StringBuilder) class is found in the [System.Text](xref:System.Text) namespace.</span></span> <span data-ttu-id="489a6-112">Чтобы избежать необходимости предоставления полного имени типа в коде, вы можете импортировать пространство имен [System.Text](xref:System.Text), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="489a6-112">To avoid having to provide a fully qualified type name in your code, you can import the [System.Text](xref:System.Text) namespace:</span></span> 

```csharp
using System;
using System.Text;
```

```vb
Imports System.Text
```

## <a name="instantiating-a-stringbuilder-object"></a><span data-ttu-id="489a6-113">Создание экземпляров объекта StringBuilder</span><span class="sxs-lookup"><span data-stu-id="489a6-113">Instantiating a StringBuilder Object</span></span>

<span data-ttu-id="489a6-114">Вы можете создать новый экземпляр класса [StringBuilder](xref:System.Text.StringBuilder) путем инициализации переменной с помощью одного из перегруженных методов конструктора, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="489a6-114">You can create a new instance of the [StringBuilder](xref:System.Text.StringBuilder) class by initializing your variable with one of the overloaded constructor methods, as illustrated in the following example.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
```

## <a name="setting-the-capacity-and-length"></a><span data-ttu-id="489a6-115">Настройка емкости и длины</span><span class="sxs-lookup"><span data-stu-id="489a6-115">Setting the Capacity and Length</span></span>

<span data-ttu-id="489a6-116">Хотя [StringBuilder](xref:System.Text.StringBuilder) является динамическим объектом, который позволяет вам развернуть ряд символов в строке, которые она инкапсулирует, можно указать максимальное число содержащихся в ней символов.</span><span class="sxs-lookup"><span data-stu-id="489a6-116">Although the [StringBuilder](xref:System.Text.StringBuilder) is a dynamic object that allows you to expand the number of characters in the string that it encapsulates, you can specify a value for the maximum number of characters that it can hold.</span></span> <span data-ttu-id="489a6-117">Это значение называется емкостью объекта, и его не следует путать с длиной строки, которую содержит текущий объект [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="489a6-117">This value is called the capacity of the object and should not be confused with the length of the string that the current [StringBuilder](xref:System.Text.StringBuilder) holds.</span></span> <span data-ttu-id="489a6-118">Например, вы можете создать новый экземпляр класса [StringBuilder](xref:System.Text.StringBuilder) со строкой Hello, длина которой составляет 5 символов, или указать, что максимальная емкость объекта — 25.</span><span class="sxs-lookup"><span data-stu-id="489a6-118">For example, you might create a new instance of the [StringBuilder](xref:System.Text.StringBuilder) class with the string "Hello", which has a length of 5, and you might specify that the object has a maximum capacity of 25.</span></span> <span data-ttu-id="489a6-119">При изменении [StringBuilder](xref:System.Text.StringBuilder) размер не перераспределяется, пока не будет достигнута граница емкости.</span><span class="sxs-lookup"><span data-stu-id="489a6-119">When you modify the [StringBuilder](xref:System.Text.StringBuilder), it does not reallocate size for itself until the capacity is reached.</span></span> <span data-ttu-id="489a6-120">Когда это происходит, новое пространство выделяется автоматически, а емкость удваивается.</span><span class="sxs-lookup"><span data-stu-id="489a6-120">When this occurs, the new space is allocated automatically and the capacity is doubled.</span></span> <span data-ttu-id="489a6-121">Емкость класса [StringBuilder](xref:System.Text.StringBuilder) можно указать с помощью одного из перегруженных конструкторов.</span><span class="sxs-lookup"><span data-stu-id="489a6-121">You can specify the capacity of the [StringBuilder](xref:System.Text.StringBuilder) class using one of the overloaded constructors.</span></span> <span data-ttu-id="489a6-122">В следующем примере показано, что объект `MyStringBuilder` можно развернуть максимум на 25 позиций.</span><span class="sxs-lookup"><span data-stu-id="489a6-122">The following example specifies that the `MyStringBuilder` object can be expanded to a maximum of 25 spaces.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!", 25);
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!", 25) 
```

<span data-ttu-id="489a6-123">Кроме того, вы можете использовать свойство [Capacity](xref:System.Text.StringBuilder.Capacity) для чтения или записи, чтобы задать максимальную длину объекта.</span><span class="sxs-lookup"><span data-stu-id="489a6-123">Additionally, you can use the read/write [Capacity](xref:System.Text.StringBuilder.Capacity) property to set the maximum length of your object.</span></span> <span data-ttu-id="489a6-124">В следующем примере используется свойство [Capacity](xref:System.Text.StringBuilder.Capacity) для определения максимальной длины объекта.</span><span class="sxs-lookup"><span data-stu-id="489a6-124">The following example uses the [Capacity](xref:System.Text.StringBuilder.Capacity) property to define the maximum object length.</span></span>

```csharp
MyStringBuilder.Capacity = 25;
```

```vb
MyStringBuilder.Capacity = 25
```

<span data-ttu-id="489a6-125">Для проверки емкости текущего объекта [StringBuilder](xref:System.Text.StringBuilder) можно использовать метод [EnsureCapacity](xref:System.Text.StringBuilder.EnsureCapacity(System.Int32)).</span><span class="sxs-lookup"><span data-stu-id="489a6-125">The [EnsureCapacity](xref:System.Text.StringBuilder.EnsureCapacity(System.Int32)) method can be used to check the capacity of the current [StringBuilder](xref:System.Text.StringBuilder).</span></span> <span data-ttu-id="489a6-126">Если емкость больше переданного значения, изменения не вносятся; однако если емкость меньше переданного значения, текущая емкость изменяется для соответствия переданному значению.</span><span class="sxs-lookup"><span data-stu-id="489a6-126">If the capacity is greater than the passed value, no change is made; however, if the capacity is smaller than the passed value, the current capacity is changed to match the passed value.</span></span>

<span data-ttu-id="489a6-127">Можно также просмотреть или задать свойство [Length](xref:System.Text.StringBuilder.Length).</span><span class="sxs-lookup"><span data-stu-id="489a6-127">The [Length](xref:System.Text.StringBuilder.Length) property can also be viewed or set.</span></span> <span data-ttu-id="489a6-128">Если вы задали для свойства [Length](xref:System.Text.StringBuilder.Length) значение больше значения свойства [Capacity](xref:System.Text.StringBuilder.Capacity), значение свойства [Capacity](xref:System.Text.StringBuilder.Capacity) будет автоматически изменено на то же самое значение, что и у свойства [Length](xref:System.Text.StringBuilder.Length).</span><span class="sxs-lookup"><span data-stu-id="489a6-128">If you set the [Length](xref:System.Text.StringBuilder.Length) property to a value that is greater than the [Capacity](xref:System.Text.StringBuilder.Capacity) property, the [Capacity](xref:System.Text.StringBuilder.Capacity) property is automatically changed to the same value as the [Length](xref:System.Text.StringBuilder.Length) property.</span></span> <span data-ttu-id="489a6-129">Если задать для свойства [Length](xref:System.Text.StringBuilder.Length) значение меньше длины строки в текущем объекте [StringBuilder](xref:System.Text.StringBuilder), строка будет укорочена.</span><span class="sxs-lookup"><span data-stu-id="489a6-129">Setting the [Length](xref:System.Text.StringBuilder.Length) property to a value that is less than the length of the string within the current [StringBuilder](xref:System.Text.StringBuilder) shortens the string.</span></span>

## <a name="modifying-the-stringbuilder-string"></a><span data-ttu-id="489a6-130">Изменение строки StringBuilder</span><span class="sxs-lookup"><span data-stu-id="489a6-130">Modifying the StringBuilder String</span></span>

<span data-ttu-id="489a6-131">В следующей таблице перечислены методы, которые можно использовать для изменения содержимого объекта [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="489a6-131">The following table lists the methods you can use to modify the contents of a [StringBuilder](xref:System.Text.StringBuilder).</span></span>

<span data-ttu-id="489a6-132">Имя метода</span><span class="sxs-lookup"><span data-stu-id="489a6-132">Method name</span></span> | <span data-ttu-id="489a6-133">Применение</span><span class="sxs-lookup"><span data-stu-id="489a6-133">Use</span></span>
----------- | ---
<span data-ttu-id="489a6-134">[StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char))</span><span class="sxs-lookup"><span data-stu-id="489a6-134">[StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char))</span></span> | <span data-ttu-id="489a6-135">Добавляет сведения в конец текущего объекта [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="489a6-135">Appends information to the end of the current [StringBuilder](xref:System.Text.StringBuilder).</span></span>
<span data-ttu-id="489a6-136">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="489a6-136">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span></span> | <span data-ttu-id="489a6-137">Заменяет отформатированным текстом описатель формата, переданный в строке.</span><span class="sxs-lookup"><span data-stu-id="489a6-137">Replaces a format specifier passed in a string with formatted text.</span></span>
<span data-ttu-id="489a6-138">[StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char))</span><span class="sxs-lookup"><span data-stu-id="489a6-138">[StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char))</span></span> | <span data-ttu-id="489a6-139">Вставляет строку или объект в указанный индекс текущего объекта [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="489a6-139">Inserts a string or object into the specified index of the current [StringBuilder](xref:System.Text.StringBuilder).</span></span>
<span data-ttu-id="489a6-140">[StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32))</span><span class="sxs-lookup"><span data-stu-id="489a6-140">[StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32))</span></span> | <span data-ttu-id="489a6-141">Удаляет указанное количество символов из текущего объекта [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="489a6-141">Removes a specified number of characters from the current [StringBuilder](xref:System.Text.StringBuilder).</span></span>
<span data-ttu-id="489a6-142">[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char))</span><span class="sxs-lookup"><span data-stu-id="489a6-142">[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char))</span></span> | <span data-ttu-id="489a6-143">Заменяет указанный символ в указанном индексе.</span><span class="sxs-lookup"><span data-stu-id="489a6-143">Replaces a specified character at a specified index.</span></span>

### <a name="append"></a><span data-ttu-id="489a6-144">Добавить</span><span class="sxs-lookup"><span data-stu-id="489a6-144">Append</span></span>

<span data-ttu-id="489a6-145">Метод [StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char)) можно использовать для добавления текста или представления строки объекта к концу строки, представленной текущим объектом [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="489a6-145">The [StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char)) method can be used to add text or a string representation of an object to the end of a string represented by the current [StringBuilder](xref:System.Text.StringBuilder).</span></span> <span data-ttu-id="489a6-146">Следующий пример инициализирует [StringBuilder](xref:System.Text.StringBuilder) с текстом Hello World, а затем добавляет текст в конец объекта.</span><span class="sxs-lookup"><span data-stu-id="489a6-146">The following example initializes a [StringBuilder](xref:System.Text.StringBuilder) to "Hello World" and then appends some text to the end of the object.</span></span> <span data-ttu-id="489a6-147">Пространство выделяется автоматически при необходимости.</span><span class="sxs-lookup"><span data-stu-id="489a6-147">Space is allocated automatically as needed.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Append(" What a beautiful day.");
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello World! What a beautiful day.
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Append(" What a beautiful day.")
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello World! What a beautiful day.
```

### <a name="appendformat"></a><span data-ttu-id="489a6-148">AppendFormat</span><span class="sxs-lookup"><span data-stu-id="489a6-148">AppendFormat</span></span>

<span data-ttu-id="489a6-149">Метод [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) добавляет текст в конец объекта [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="489a6-149">The [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) method adds text to the end of the [StringBuilder](xref:System.Text.StringBuilder) object.</span></span> <span data-ttu-id="489a6-150">Он поддерживает возможность составного форматирования (дополнительные сведения см. в разделе [Составное форматирование](composite-format.md)) путем вызова реализации [IFormattable](xref:System.IFormattable) форматируемого объекта или объектов.</span><span class="sxs-lookup"><span data-stu-id="489a6-150">It supports the composite formatting feature (for more information, see [Composite Formatting](composite-format.md)) by calling the [IFormattable](xref:System.IFormattable) implementation of the object or objects to be formatted.</span></span> <span data-ttu-id="489a6-151">Следовательно, он принимает строки стандартного формата для числовых значений, значений даты и времени, значений перечисления, строки пользовательского формата для чисел и дат и строки формата, определенные для пользовательских типов.</span><span class="sxs-lookup"><span data-stu-id="489a6-151">Therefore, it accepts the standard format strings for numeric, date and time, and enumeration values, the custom format strings for numeric and date and time values, and the format strings defined for custom types.</span></span> <span data-ttu-id="489a6-152">(Дополнительные сведения о форматировании см. в разделе [Типы форматирования](formatting-types.md).) Вы можете использовать этот метод для настройки формата переменных и добавления этих значений в объект [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="489a6-152">(For information about formatting, see [Formatting Types](formatting-types.md).) You can use this method to customize the format of variables and append those values to a [StringBuilder](xref:System.Text.StringBuilder).</span></span> <span data-ttu-id="489a6-153">В следующем примере используется метод AppendFormat для размещения целочисленного значения, отформатированного в качестве значения валюты в конце объекта [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="489a6-153">The following example uses the AppendFormat method to place an integer value formatted as a currency value at the end of a [StringBuilder](xref:System.Text.StringBuilder) object.</span></span>

```csharp
int MyInt = 25; 
StringBuilder MyStringBuilder = new StringBuilder("Your total is ");
MyStringBuilder.AppendFormat("{0:C} ", MyInt);
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Your total is $25.00
```

```vb
Dim MyInt As Integer = 25
Dim MyStringBuilder As New StringBuilder("Your total is ")
MyStringBuilder.AppendFormat("{0:C} ", MyInt)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'     Your total is $25.00 
```

### <a name="insert"></a><span data-ttu-id="489a6-154">Insert</span><span class="sxs-lookup"><span data-stu-id="489a6-154">Insert</span></span>

<span data-ttu-id="489a6-155">Метод [StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char)) добавляет строку или объект в указанную позицию в текущем объекте [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="489a6-155">The [StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char)) method adds a string or object to a specified position in the current [StringBuilder](xref:System.Text.StringBuilder) object.</span></span> <span data-ttu-id="489a6-156">В следующем примере этот метод используется для вставки слова в шестую позицию объекта [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="489a6-156">The following example uses this method to insert a word into the sixth position of a [StringBuilder](xref:System.Text.StringBuilder) object.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Insert(6,"Beautiful ");
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello Beautiful World!
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Insert(6, "Beautiful ")
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'      Hello Beautiful World!
```

### <a name="remove"></a><span data-ttu-id="489a6-157">Удалить</span><span class="sxs-lookup"><span data-stu-id="489a6-157">Remove</span></span>

<span data-ttu-id="489a6-158">Вы можете использовать метод [StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)), чтобы удалить указанное количество символов из текущего объекта [StringBuilder](xref:System.Text.StringBuilder), начиная с указанного индекса (с отсчетом с нуля).</span><span class="sxs-lookup"><span data-stu-id="489a6-158">You can use the [StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) method to remove a specified number of characters from the current [StringBuilder](xref:System.Text.StringBuilder) object, beginning at a specified zero-based index.</span></span> <span data-ttu-id="489a6-159">В следующем примере используется метод [Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) для сокращения объекта [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="489a6-159">The following example uses the [Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) method to shorten a [StringBuilder](xref:System.Text.StringBuilder) object.</span></span>

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Remove(5,7);
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Remove(5, 7)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello
```

### <a name="replace"></a><span data-ttu-id="489a6-160">Заменить</span><span class="sxs-lookup"><span data-stu-id="489a6-160">Replace</span></span>

<span data-ttu-id="489a6-161">[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) |Заменяет указанный символ в указанном индексе.</span><span class="sxs-lookup"><span data-stu-id="489a6-161">The [StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Replaces a specified character at a specified index.</span></span>
<span data-ttu-id="489a6-162">можно использовать для замены символов в объекте [StringBuilder](xref:System.Text.StringBuilder) другими указанными символами.</span><span class="sxs-lookup"><span data-stu-id="489a6-162">method can be used to replace characters within the [StringBuilder](xref:System.Text.StringBuilder) object with another specified character.</span></span> <span data-ttu-id="489a6-163">В следующем примере метод [Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) |Заменяет указанный символ в указанном индексе.</span><span class="sxs-lookup"><span data-stu-id="489a6-163">The following example uses the [Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Replaces a specified character at a specified index.</span></span>
<span data-ttu-id="489a6-164">используется для поиска объекта [StringBuilder](xref:System.Text.StringBuilder) для всех экземпляров восклицательного знака (!) и замены их знаком вопроса (?).</span><span class="sxs-lookup"><span data-stu-id="489a6-164">method to search a [StringBuilder](xref:System.Text.StringBuilder) object for all instances of the exclamation point character (!) and replace them with the question mark character (?).</span></span>
 
 ```csharp
 StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Replace('!', '?');
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello World?
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Replace("!"c, "?"c)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello World?
```

## <a name="converting-a-stringbuilder-object-to-a-string"></a><span data-ttu-id="489a6-165">Преобразование объекта StringBuilder в строку</span><span class="sxs-lookup"><span data-stu-id="489a6-165">Converting a StringBuilder Object to a String</span></span>

<span data-ttu-id="489a6-166">Необходимо преобразовать объект [StringBuilder](xref:System.Text.StringBuilder) в объект [String](xref:System.String) перед тем, как вы сможете передать строку, представленную объектом [StringBuilder](xref:System.Text.StringBuilder), методу, который содержит параметр [String](xref:System.String), или отобразить ее в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="489a6-166">You must convert the [StringBuilder](xref:System.Text.StringBuilder) object to a [String](xref:System.String) object before you can pass the string represented by the [StringBuilder](xref:System.Text.StringBuilder) object to a method that has a [String](xref:System.String) parameter or display it in the user interface.</span></span> <span data-ttu-id="489a6-167">Это преобразование можно выполнить, вызвав метод [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString).</span><span class="sxs-lookup"><span data-stu-id="489a6-167">You do this conversion by calling the [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) method.</span></span> <span data-ttu-id="489a6-168">В следующем примере вызывается ряд методов [StringBuilder](xref:System.Text.StringBuilder), а затем вызывается метод [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) для отображения строки.</span><span class="sxs-lookup"><span data-stu-id="489a6-168">The following example calls a number of [StringBuilder](xref:System.Text.StringBuilder) methods and then calls the [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) method to display the string.</span></span>

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      StringBuilder sb = new StringBuilder();
      bool flag = true;
      string[] spellings = { "recieve", "receeve", "receive" };
      sb.AppendFormat("Which of the following spellings is {0}:", flag);
      sb.AppendLine();
      for (int ctr = 0; ctr <= spellings.GetUpperBound(0); ctr++) {
         sb.AppendFormat("   {0}. {1}", ctr, spellings[ctr]);
         sb.AppendLine();
      }
      sb.AppendLine();
      Console.WriteLine(sb.ToString());
   }
}
// The example displays the following output:
//       Which of the following spellings is True:
//          0. recieve
//          1. receeve
//          2. receive
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim sb As New StringBuilder()
      Dim flag As Boolean = True
      Dim spellings() As String = { "recieve", "receeve", "receive" }
      sb.AppendFormat("Which of the following spellings is {0}:", flag)
      sb.AppendLine()
      For ctr As Integer = 0 To spellings.GetUpperBound(0)
         sb.AppendFormat("   {0}. {1}", ctr, spellings(ctr))
         sb.AppendLine()
      Next
      sb.AppendLine()
      Console.WriteLine(sb.ToString())
   End Sub
End Module
' The example displays the following output:
'       Which of the following spellings is True:
'          0. recieve
'          1. receeve
'          2. receive
```

## <a name="see-also"></a><span data-ttu-id="489a6-169">См. также</span><span class="sxs-lookup"><span data-stu-id="489a6-169">See Also</span></span>

[<span data-ttu-id="489a6-170">System.Text.StringBuilder</span><span class="sxs-lookup"><span data-stu-id="489a6-170">System.Text.StringBuilder</span></span>](xref:System.Text.StringBuilder)

[<span data-ttu-id="489a6-171">Базовые операции со строками</span><span class="sxs-lookup"><span data-stu-id="489a6-171">Basic string operations</span></span>](basic-string-operations.md)

[<span data-ttu-id="489a6-172">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="489a6-172">Formatting types</span></span>](formatting-types.md)

