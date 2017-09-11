---
title: "Сокращение и удаление символов из строк"
description: "Сокращение и удаление символов из строк"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 95d818bc-2661-43f6-adb8-13b53abf9682
ms.translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 96cf08c0de8ba73d931d561187369ccf8b091651
ms.contentlocale: ru-ru
ms.lasthandoff: 11/05/2016

---

# <a name="trimming-and-removing-characters-from-strings"></a><span data-ttu-id="0981e-104">Сокращение и удаление символов из строк</span><span class="sxs-lookup"><span data-stu-id="0981e-104">Trimming and removing characters from strings</span></span>

<span data-ttu-id="0981e-105">При разборе предложения на отдельные слова может оказаться, что в начале или в конце некоторых слов стоят пробелы.</span><span class="sxs-lookup"><span data-stu-id="0981e-105">If you are parsing a sentence into individual words, you might end up with words that have blank spaces (also called white spaces) on either end of the word.</span></span> <span data-ttu-id="0981e-106">В этом случае можно воспользоваться методами сокращения в классе [System.String](https://docs.microsoft.com/dotnet/core/api/System.String), чтобы удалить любое количество пробелов или других символов из указанной позиции в строке.</span><span class="sxs-lookup"><span data-stu-id="0981e-106">In this situation, you can use one of the trim methods in the [System.String](https://docs.microsoft.com/dotnet/core/api/System.String) class to remove any number of spaces or other characters from a specified position in the string.</span></span> <span data-ttu-id="0981e-107">В таблице ниже описаны доступны методы сокращения.</span><span class="sxs-lookup"><span data-stu-id="0981e-107">The following table describes the available trim methods.</span></span>

<span data-ttu-id="0981e-108">Имя метода</span><span class="sxs-lookup"><span data-stu-id="0981e-108">Method name</span></span> | <span data-ttu-id="0981e-109">Применение</span><span class="sxs-lookup"><span data-stu-id="0981e-109">Use</span></span>
----------- | ---
[<span data-ttu-id="0981e-110">String.Trim</span><span class="sxs-lookup"><span data-stu-id="0981e-110">String.Trim</span></span>](https://docs.microsoft.com/dotnet/core/api/System.String.Trim) | <span data-ttu-id="0981e-111">Удаление пробелов или знаков, указанных в массиве знаков, из начала и конца строки.</span><span class="sxs-lookup"><span data-stu-id="0981e-111">Removes white spaces or characters specified in an array of characters from the beginning and end of a string.</span></span>
<span data-ttu-id="0981e-112">[String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[]))</span><span class="sxs-lookup"><span data-stu-id="0981e-112">[String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[]))</span></span> | <span data-ttu-id="0981e-113">Удаление символов, указанных в массиве символов, в конце строки.</span><span class="sxs-lookup"><span data-stu-id="0981e-113">Removes characters specified in an array of characters from the end of a string.</span></span>
<span data-ttu-id="0981e-114">[String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[]))</span><span class="sxs-lookup"><span data-stu-id="0981e-114">[String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[]))</span></span> | <span data-ttu-id="0981e-115">Удаление символов, указанных в массиве символов, в начале строки.</span><span class="sxs-lookup"><span data-stu-id="0981e-115">Removes characters specified in an array of characters from the beginning of a string.</span></span>
<span data-ttu-id="0981e-116">[String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32))</span><span class="sxs-lookup"><span data-stu-id="0981e-116">[String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32))</span></span> | <span data-ttu-id="0981e-117">Удаление указанного количества символов в указанной позиции индекса в строке.</span><span class="sxs-lookup"><span data-stu-id="0981e-117">Removes a specified number of characters from a specified index position in a string.</span></span>


## <a name="trim"></a><span data-ttu-id="0981e-118">Trim</span><span class="sxs-lookup"><span data-stu-id="0981e-118">Trim</span></span>

<span data-ttu-id="0981e-119">Простой способ удалить пробелы с обоих концов строки — метод [String.Trim](https://docs.microsoft.com/dotnet/core/api/System.String.Trim), пример использования которого приведен ниже.</span><span class="sxs-lookup"><span data-stu-id="0981e-119">You can easily remove white spaces from both ends of a string by using the [String.Trim](https://docs.microsoft.com/dotnet/core/api/System.String.Trim) method, as shown in the following example.</span></span>

```csharp
string MyString = " Big   ";
Console.WriteLine("Hello{0}World!", MyString);
string TrimString = MyString.Trim();
Console.WriteLine("Hello{0}World!", TrimString);
//       The example displays the following output:
//             Hello Big   World!
//             HelloBigWorld!
```

```vb
Dim MyString As String = " Big   "
Console.WriteLine("Hello{0}World!", MyString)
Dim TrimString As String = MyString.Trim()
Console.WriteLine("Hello{0}World!", TrimString)
' The example displays the following output:
'       Hello Big   World!
'       HelloBigWorld!
```

<span data-ttu-id="0981e-120">Кроме того, можно удалить символы, указанные в массиве знаков, из начала и конца строки.</span><span class="sxs-lookup"><span data-stu-id="0981e-120">You can also remove characters that you specify in a character array from the beginning and end of a string.</span></span> <span data-ttu-id="0981e-121">В следующем примере удаляются символы пробелов, точки и звездочки.</span><span class="sxs-lookup"><span data-stu-id="0981e-121">The following example removes white-space characters, periods, and asterisks.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      String header = "* A Short String. *";
      Console.WriteLine(header);
      Console.WriteLine(header.Trim( new Char[] { ' ', '*', '.' } ));
   }
}
// The example displays the following output:
//       * A Short String. *
//       A Short String
```

```vb
Module Example
   Public Sub Main()
      Dim header As String = "* A Short String. *"
      Console.WriteLine(header)
      Console.WriteLine(header.Trim( { " "c, "*"c, "."c } ))
   End Sub
End Module
' The example displays the following output:
'       * A Short String. *
'       A Short String
```

## <a name="trimend"></a><span data-ttu-id="0981e-122">TrimEnd</span><span class="sxs-lookup"><span data-stu-id="0981e-122">TrimEnd</span></span>

<span data-ttu-id="0981e-123">Метод [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) удаляет символы в конце строки, создавая новый строковый объект.</span><span class="sxs-lookup"><span data-stu-id="0981e-123">The [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) method removes characters from the end of a string, creating a new string object.</span></span> <span data-ttu-id="0981e-124">Для указания символов, которые следует удалять, в этот метод передается массив символов.</span><span class="sxs-lookup"><span data-stu-id="0981e-124">An array of characters is passed to this method to specify the characters to be removed.</span></span> <span data-ttu-id="0981e-125">Порядок элементов в массиве символов не влияет на выполнение операции сокращения.</span><span class="sxs-lookup"><span data-stu-id="0981e-125">The order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="0981e-126">В случае обнаружения символа, который отсутствует в массиве, операция останавливается.</span><span class="sxs-lookup"><span data-stu-id="0981e-126">The trim stops when a character not specified in the array is found.</span></span>

<span data-ttu-id="0981e-127">Ниже приведен пример удаления последних букв строки с помощью метода TrimEnd.</span><span class="sxs-lookup"><span data-stu-id="0981e-127">The following example removes the last letters of a string using the TrimEnd method.</span></span> <span data-ttu-id="0981e-128">В этом примере положение символов `'r'` и `'W'` изменено для иллюстрации того, что порядок символов в массиве не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="0981e-128">In this example, the position of the `'r'` character and the `'W'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span> <span data-ttu-id="0981e-129">Обратите внимание, что этот код удаляет последнее слово `MyString` и часть первого.</span><span class="sxs-lookup"><span data-stu-id="0981e-129">Notice that this code removes the last word of `MyString` plus part of the first.</span></span>

```csharp
string MyString = "Hello World!";
char[] MyChar = {'r','o','W','l','d','!',' '};
string NewString = MyString.TrimEnd(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello World!"
Dim MyChar() As Char = {"r","o","W","l","d","!"," "}
Dim NewString As String = MyString.TrimEnd(MyChar)
Console.WriteLine(NewString)
```

<span data-ttu-id="0981e-130">Этот код выводит на консоль значение `He`.</span><span class="sxs-lookup"><span data-stu-id="0981e-130">This code displays `He` to the console.</span></span>

<span data-ttu-id="0981e-131">Ниже приведен пример удаления последнего слова строки с помощью метода [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])).</span><span class="sxs-lookup"><span data-stu-id="0981e-131">The following example removes the last word of a string using the [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) method.</span></span> <span data-ttu-id="0981e-132">В этом коде после слова `Hello` следует запятая, а поскольку запятая не указана в массиве символов для сокращения, то выполнение операции прекращается на запятой.</span><span class="sxs-lookup"><span data-stu-id="0981e-132">In this code, a comma follows the word `Hello` and, because the comma is not specified in the array of characters to trim, the trim ends at the comma.</span></span>

```csharp
string MyString = "Hello, World!";
char[] MyChar = {'r','o','W','l','d','!',' '};
string NewString = MyString.TrimEnd(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello, World!"
Dim MyChar() As Char = {"r","o","W","l","d","!"," "}
Dim NewString As String = MyString.TrimEnd(MyChar)
Console.WriteLine(NewString)
```

<span data-ttu-id="0981e-133">Этот код выводит на консоль значение `Hello,`.</span><span class="sxs-lookup"><span data-stu-id="0981e-133">This code displays `Hello,` to the console.</span></span>

## <a name="trimstart"></a><span data-ttu-id="0981e-134">TrimStart</span><span class="sxs-lookup"><span data-stu-id="0981e-134">TrimStart</span></span>

<span data-ttu-id="0981e-135">Метод [String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) аналогичен методу [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) за исключением того, что он создает новую строку путем удаления знаков в начале существующего строкового объекта.</span><span class="sxs-lookup"><span data-stu-id="0981e-135">The [String.TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) method is similar to the [String.TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) method except that it creates a new string by removing characters from the beginning of an existing string object.</span></span> <span data-ttu-id="0981e-136">Для указания символов, которые следует удалять, в метод [TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) передается массив символов.</span><span class="sxs-lookup"><span data-stu-id="0981e-136">An array of characters is passed to the [TrimStart](https://docs.microsoft.com/dotnet/core/api/System.String.TrimStart(System.Char[])) method to specify the characters to be removed.</span></span> <span data-ttu-id="0981e-137">Как и в случае с методом [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])), порядок элементов в массиве символов не влияет на выполнение операции сокращения.</span><span class="sxs-lookup"><span data-stu-id="0981e-137">As with the [TrimEnd](https://docs.microsoft.com/dotnet/core/api/System.String.TrimEnd(System.Char[])) method, the order of the elements in the character array does not affect the trim operation.</span></span> <span data-ttu-id="0981e-138">В случае обнаружения символа, который отсутствует в массиве, операция останавливается.</span><span class="sxs-lookup"><span data-stu-id="0981e-138">The trim stops when a character not specified in the array is found.</span></span>

<span data-ttu-id="0981e-139">В следующем примере удаляется первое слово в строке.</span><span class="sxs-lookup"><span data-stu-id="0981e-139">The following example removes the first word of a string.</span></span> <span data-ttu-id="0981e-140">В этом примере положение символов `'l'` и `'H'` изменено для иллюстрации того, что порядок символов в массиве не имеет значения.</span><span class="sxs-lookup"><span data-stu-id="0981e-140">In this example, the position of the `'l'` character and the `'H'` character are reversed to illustrate that the order of characters in the array does not matter.</span></span>

```csharp
string MyString = "Hello World!";
char[] MyChar = {'e', 'H','l','o',' ' };
string NewString = MyString.TrimStart(MyChar);
Console.WriteLine(NewString);
```

```vb
Dim MyString As String = "Hello World!"
Dim MyChar() As Char = {"e","H","l","o"," " }
Dim NewString As String = MyString.TrimStart(MyChar)
Console.WriteLine(NewString)
```

<span data-ttu-id="0981e-141">Этот код выводит на консоль значение `World!`.</span><span class="sxs-lookup"><span data-stu-id="0981e-141">This code displays `World!` to the console.</span></span>

## <a name="remove"></a><span data-ttu-id="0981e-142">Удалить</span><span class="sxs-lookup"><span data-stu-id="0981e-142">Remove</span></span>

<span data-ttu-id="0981e-143">Метод [String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32)) удаляет указанное количество символов, начиная с указанного места в существующей строке.</span><span class="sxs-lookup"><span data-stu-id="0981e-143">The [String.Remove](https://docs.microsoft.com/dotnet/core/api/System.String.Remove(System.Int32)) method removes a specified number of characters that begin at a specified position in an existing string.</span></span> <span data-ttu-id="0981e-144">Этот метод подразумевает, что отсчет индекса начинается с нуля.</span><span class="sxs-lookup"><span data-stu-id="0981e-144">This method assumes a zero-based index.</span></span>

<span data-ttu-id="0981e-145">В следующем примере из строки удаляется десять символов, начиная с пятой позиции отсчитываемого от нуля индекса строки.</span><span class="sxs-lookup"><span data-stu-id="0981e-145">The following example removes ten characters from a string beginning at position five of a zero-based index of the string.</span></span>

```csharp
string MyString = "Hello Beautiful World!";
Console.WriteLine(MyString.Remove(5,10));
// The example displays the following output:
//         Hello World!  
```

```vb
Dim MyString As String = "Hello Beautiful World!"
Console.WriteLine(MyString.Remove(5,10))
' The example displays the following output:
'         Hello World!
```

<span data-ttu-id="0981e-146">Чтобы удалить из строки указанный символ или подстроку, можно вызвать метод [String.Replace(String, String)](https://docs.microsoft.com/dotnet/core/api/System.String.Replace(System.String,System.String)) и указать пустую строку ([String.Empty](https://docs.microsoft.com/dotnet/core/api/System.String.Empty)) в качестве замены.</span><span class="sxs-lookup"><span data-stu-id="0981e-146">You can also remove a specified character or substring from a string by calling the [String.Replace(String, String)](https://docs.microsoft.com/dotnet/core/api/System.String.Replace(System.String,System.String)) method and specifying an empty string ([String.Empty](https://docs.microsoft.com/dotnet/core/api/System.String.Empty)) as the replacement.</span></span> <span data-ttu-id="0981e-147">В следующем примере удаляются все запятые из строки.</span><span class="sxs-lookup"><span data-stu-id="0981e-147">The following example removes all commas from a string.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      String phrase = "a cold, dark night";
      Console.WriteLine("Before: {0}", phrase);
      phrase = phrase.Replace(",", "");
      Console.WriteLine("After: {0}", phrase);
   }
}
// The example displays the following output:
//       Before: a cold, dark night
//       After: a cold dark night
```

```vb
Module Example
   Public Sub Main()
      Dim phrase As String = "a cold, dark night"
      Console.WriteLine("Before: {0}", phrase)
      phrase = phrase.Replace(",", "")
      Console.WriteLine("After: {0}", phrase)
   End Sub
End Module
' The example displays the following output:
'       Before: a cold, dark night
'       After: a cold dark night
```

## <a name="see-also"></a><span data-ttu-id="0981e-148">См. также</span><span class="sxs-lookup"><span data-stu-id="0981e-148">See Also</span></span>

[<span data-ttu-id="0981e-149">Базовые операции со строками</span><span class="sxs-lookup"><span data-stu-id="0981e-149">Basic string operations</span></span>](basic-string-operations.md)


