---
title: "Типы форматирования"
description: "Типы форматирования"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: cf497639-9f91-45cb-836f-998d1cea2f43
ms.translationtype: Human Translation
ms.sourcegitcommit: b967d8e55347f44a012e4ad8e916440ae228c8ec
ms.openlocfilehash: e9b8ad13a48dd43236769b130d6f8a75b7b023ca
ms.contentlocale: ru-ru
ms.lasthandoff: 03/10/2017

---

# <a name="formatting-types"></a><span data-ttu-id="d76fd-104">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="d76fd-104">Formatting types</span></span>

<span data-ttu-id="d76fd-105">Форматирование — это процесс преобразования экземпляра класса, структуры или значения перечисления в строковое представление. Результирующая строка затем демонстрируется пользователям или десериализуется для последующего восстановления значения с исходным типом данных.</span><span class="sxs-lookup"><span data-stu-id="d76fd-105">Formatting is the process of converting an instance of a class, structure, or enumeration value to its string representation, often so that the resulting string can be displayed to users or deserialized to restore the original data type.</span></span> <span data-ttu-id="d76fd-106">Преобразование может быть связано с рядом проблем:</span><span class="sxs-lookup"><span data-stu-id="d76fd-106">This conversion can pose a number of challenges:</span></span>

* <span data-ttu-id="d76fd-107">Внутреннее представление значений необязательно соответствует тому виду, в котором они должны быть представлены пользователям.</span><span class="sxs-lookup"><span data-stu-id="d76fd-107">The way that values are stored internally does not necessarily reflect the way that users want to view them.</span></span> <span data-ttu-id="d76fd-108">Например, номер телефона может храниться в форме **8009999999**, которая не отличается удобством для пользователей.</span><span class="sxs-lookup"><span data-stu-id="d76fd-108">For example, a telephone number might be stored in the form **8009999999**, which is not user-friendly.</span></span> <span data-ttu-id="d76fd-109">Вместо этого номер должен отображаться в следующем виде: **800-999-9999**.</span><span class="sxs-lookup"><span data-stu-id="d76fd-109">It should instead be displayed as **800-999-9999**.</span></span> <span data-ttu-id="d76fd-110">Пример подобного форматирования см. в разделе [Строки настраиваемого формата](#custom-format-strings).</span><span class="sxs-lookup"><span data-stu-id="d76fd-110">See the [Custom format strings](#custom-format-strings) section for an example that formats a number in this way.</span></span> 

* <span data-ttu-id="d76fd-111">Иногда порядок преобразования объекта в строковое представление неочевиден.</span><span class="sxs-lookup"><span data-stu-id="d76fd-111">Sometimes the conversion of an object to its string representation is not intuitive.</span></span> <span data-ttu-id="d76fd-112">Например, неясно, как должно выглядеть строковое представление объекта класса **Temperature**, представляющего температурные значения, или класса **Person**, представляющего данные о людях.</span><span class="sxs-lookup"><span data-stu-id="d76fd-112">For example, it is not clear how the string representation of a **Temperature** object or a **Person** object should appear.</span></span> <span data-ttu-id="d76fd-113">Пример различного форматирования объекта **Temperature** см. в разделе [Строки стандартного формата](#standard-format-strings).</span><span class="sxs-lookup"><span data-stu-id="d76fd-113">For an example that formats a **Temperature** object in a variety of ways, see the [Standard format strings](#standard-format-strings) section.</span></span>

* <span data-ttu-id="d76fd-114">Для некоторых значений может потребоваться форматирование, учитывающее язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="d76fd-114">Values often require culture-sensitive formatting.</span></span> <span data-ttu-id="d76fd-115">Например, в приложении, где числа используются для обозначения денежных сумм, числовые строки должны включать символ текущей валюты, разделители групп (в большинстве случаев они совпадают с разделителями тысяч) и символ-разделитель целой и дробной частей.</span><span class="sxs-lookup"><span data-stu-id="d76fd-115">For example, in an application that uses numbers to reflect monetary values, numeric strings should include the current culture’s currency symbol, group separator (which, in most cultures, is the thousands separator), and decimal symbol.</span></span> <span data-ttu-id="d76fd-116">Пример см. в разделе [Форматирование с учетом языка и региональных параметров с помощью поставщиков формата и интерфейса IFormatProvider](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface).</span><span class="sxs-lookup"><span data-stu-id="d76fd-116">For an example, see the [Culture-sensitive formatting with format providers and the IFormatProvider interface](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface) section.</span></span> 

* <span data-ttu-id="d76fd-117">Одно и то же значение может быть необходимо представить в приложении несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="d76fd-117">An application may have to display the same value in different ways.</span></span> <span data-ttu-id="d76fd-118">Например, приложение может представлять элемент перечисления, отображая строковое представление его имени или его базовое значение.</span><span class="sxs-lookup"><span data-stu-id="d76fd-118">For example, an application may represent an enumeration member by displaying a string representation of its name or by displaying its underlying value.</span></span> <span data-ttu-id="d76fd-119">Пример различного форматирования члена перечисления [DayOfWeek](xref:System.DayOfWeek) см. в разделе [Строки стандартного формата](#standard-format-strings).</span><span class="sxs-lookup"><span data-stu-id="d76fd-119">For an example that formats a member of the [DayOfWeek](xref:System.DayOfWeek) enumeration in different ways, see the [Standard format strings](#standard-format-strings) section.</span></span>

<span data-ttu-id="d76fd-120">Платформа .NET обеспечивает обширную поддержку форматирования, позволяя разработчикам справиться с описанными проблемами.</span><span class="sxs-lookup"><span data-stu-id="d76fd-120">.NET provides rich formatting support that enables developers to address these requirements.</span></span> 

> [!NOTE]
> <span data-ttu-id="d76fd-121">Форматирование приводит к преобразованию значения определенного типа в его строковое представление.</span><span class="sxs-lookup"><span data-stu-id="d76fd-121">Formatting converts the value of a type into a string representation.</span></span> <span data-ttu-id="d76fd-122">Обратной по отношению к форматированию операцией является анализ.</span><span class="sxs-lookup"><span data-stu-id="d76fd-122">Parsing is the inverse of formatting.</span></span> <span data-ttu-id="d76fd-123">В ходе анализа на основании строкового представления создается экземпляр некоторого типа данных.</span><span class="sxs-lookup"><span data-stu-id="d76fd-123">A parsing operation creates an instance of a data type from its string representation.</span></span> <span data-ttu-id="d76fd-124">Дополнительные сведения о преобразовании строк в другие типы данных см. в статье [Анализ строк](parsing-strings.md).</span><span class="sxs-lookup"><span data-stu-id="d76fd-124">For information about converting strings to other data types, see [Parsing strings](parsing-strings.md).</span></span>

<span data-ttu-id="d76fd-125">Обзор включает следующие разделы.</span><span class="sxs-lookup"><span data-stu-id="d76fd-125">This overview contains the following sections:</span></span>

* [<span data-ttu-id="d76fd-126">Форматирование в .NET</span><span class="sxs-lookup"><span data-stu-id="d76fd-126">Formatting in .NET</span></span>](#formatting-in-net)

* [<span data-ttu-id="d76fd-127">Форматирование по умолчанию при помощи метода ToString</span><span class="sxs-lookup"><span data-stu-id="d76fd-127">Default formatting using the ToString method</span></span>](#default-formatting-using-the-tostring-method)

* [<span data-ttu-id="d76fd-128">Переопределение метода ToString</span><span class="sxs-lookup"><span data-stu-id="d76fd-128">Overriding the ToString method</span></span>](#overriding-the-tostring-method)

* [<span data-ttu-id="d76fd-129">Метод ToString и строки формата</span><span class="sxs-lookup"><span data-stu-id="d76fd-129">The ToString method and format strings</span></span>](#the-tostring-method-and-format-strings)

    * [<span data-ttu-id="d76fd-130">Строки стандартного формата</span><span class="sxs-lookup"><span data-stu-id="d76fd-130">Standard format strings</span></span>](#standard-format-strings)
    
    * [<span data-ttu-id="d76fd-131">Строки настраиваемого формата</span><span class="sxs-lookup"><span data-stu-id="d76fd-131">Custom format strings</span></span>](#custom-format-strings)
    
    * [<span data-ttu-id="d76fd-132">Строки форматов и типы .NET</span><span class="sxs-lookup"><span data-stu-id="d76fd-132">Format strings and .NET types</span></span>](#format-strings-and-net-types)
    
* [<span data-ttu-id="d76fd-133">Форматирование с учетом языка и региональных параметров с помощью поставщиков формата и интерфейса IFormatProvider</span><span class="sxs-lookup"><span data-stu-id="d76fd-133">Culture-sensitive formatting with format providers and the IFormatProvider interface</span></span>](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface)

    * [<span data-ttu-id="d76fd-134">Форматирование числовых значений, зависящее от языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="d76fd-134">Culture-sensitive formatting of numeric values</span></span>](#culture-sensitive-formatting-of-numeric-values)
    
    * [<span data-ttu-id="d76fd-135">Форматирование значений даты и времени, зависящее от языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="d76fd-135">Culture-sensitive formatting of date and time values</span></span>](#culture-sensitive-formatting-of-date-and-time-values)
    
* [<span data-ttu-id="d76fd-136">Интерфейс IFormattable</span><span class="sxs-lookup"><span data-stu-id="d76fd-136">The IFormattable interface</span></span>](#the-iformattable-interface)

* [<span data-ttu-id="d76fd-137">Составное форматирование</span><span class="sxs-lookup"><span data-stu-id="d76fd-137">Composite formatting</span></span>](#composite-formatting)

* [<span data-ttu-id="d76fd-138">Настраиваемое форматирование с использованием интерфейса ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="d76fd-138">Custom formatting with ICustomFormatter</span></span>](#custom-formatting-with-icustomformatter)

* [<span data-ttu-id="d76fd-139">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="d76fd-139">Related topics</span></span>](#related-topics)

* [<span data-ttu-id="d76fd-140">Ссылки</span><span class="sxs-lookup"><span data-stu-id="d76fd-140">Reference</span></span>](#reference)

## <a name="formatting-in-net"></a><span data-ttu-id="d76fd-141">Форматирование в .NET</span><span class="sxs-lookup"><span data-stu-id="d76fd-141">Formatting in .NET</span></span>

<span data-ttu-id="d76fd-142">Базовый механизм форматирования — это используемая по умолчанию реализация метода [Object.ToString](xref:System.Object.ToString), которая описана ниже в разделе [Форматирование по умолчанию при помощи метода ToString](#default-formatting-using-the-tostring-method).</span><span class="sxs-lookup"><span data-stu-id="d76fd-142">The basic mechanism for formatting is the default implementation of the [Object.ToString](xref:System.Object.ToString) method, which is discussed in the [Default formatting using the ToString method](#default-formatting-using-the-tostring-method) section later in this topic.</span></span> <span data-ttu-id="d76fd-143">При этом платформа .NET предоставляет несколько способов изменения и расширения имеющихся по умолчанию возможностей форматирования.</span><span class="sxs-lookup"><span data-stu-id="d76fd-143">However, .NET provides several ways to modify and extend its default formatting support.</span></span> <span data-ttu-id="d76fd-144">В число этих требований входят следующие:</span><span class="sxs-lookup"><span data-stu-id="d76fd-144">These include the following:</span></span>

* <span data-ttu-id="d76fd-145">Переопределение метода [Object.ToString](xref:System.Object.ToString), позволяющее определить настраиваемое строковое представление значения объекта.</span><span class="sxs-lookup"><span data-stu-id="d76fd-145">Overriding the [Object.ToString](xref:System.Object.ToString) method to define a custom string representation of an object’s value.</span></span> <span data-ttu-id="d76fd-146">Дополнительные сведения см. ниже в разделе [Переопределение метода ToString](#overriding-the-tostring-method).</span><span class="sxs-lookup"><span data-stu-id="d76fd-146">For more information, see the [Overriding the ToString method](#overriding-the-tostring-method) section later in this topic.</span></span>

* <span data-ttu-id="d76fd-147">Определение описателей формата, позволяющих использовать несколько видов строкового представления значения объекта.</span><span class="sxs-lookup"><span data-stu-id="d76fd-147">Defining format specifiers that enable the string representation of an object’s value to take multiple forms.</span></span> <span data-ttu-id="d76fd-148">Например, описатель формата "X" в следующем операторе позволяет преобразовать целое число в шестнадцатеричное строковое представление.</span><span class="sxs-lookup"><span data-stu-id="d76fd-148">For example, the "X" format specifier in the following statement converts an integer to the string representation of a hexadecimal value.</span></span>

  ```csharp
  int integerValue = 60312;
  Console.WriteLine(integerValue.ToString("X"));   // Displays EB98.
  ```

  ```vb
  Dim integerValue As Integer = 60312
  Console.WriteLine(integerValue.ToString("X"))   ' Displays EB98.
  ```
  
  <span data-ttu-id="d76fd-149">Дополнительные сведения об описателях форматов см. в разделе [Метод ToString и строки формата](#the-tostring-method-and-format-strings).</span><span class="sxs-lookup"><span data-stu-id="d76fd-149">For more information about format specifiers, see the [The ToString method and format strings](#the-tostring-method-and-format-strings) section.</span></span>
  
* <span data-ttu-id="d76fd-150">Использование поставщиков форматирования, позволяющих воспользоваться преимуществами соглашений о форматировании, присущих конкретному языку и региональным параметрам.</span><span class="sxs-lookup"><span data-stu-id="d76fd-150">Using format providers to take advantage of the formatting conventions of a specific culture.</span></span> <span data-ttu-id="d76fd-151">Например, следующий оператор выводит значение валюты с использованием соглашений о форматировании языка и региональных параметров "en-US".</span><span class="sxs-lookup"><span data-stu-id="d76fd-151">For example, the following statement displays a currency value by using the formatting conventions of the en-US culture.</span></span> 

  ```csharp
  double cost = 1632.54; 
  Console.WriteLine(cost.ToString("C", 
                  new System.Globalization.CultureInfo("en-US")));   
  // The example displays the following output:
  //       $1,632.54
  ```

  ```vb
  Dim cost As Double = 1632.54
  Console.WriteLine(cost.ToString("C", New System.Globalization.CultureInfo("en-US")))
  ' The example displays the following output:
  '       $1,632.54
  ```
  
  <span data-ttu-id="d76fd-152">Дополнительные сведения о форматировании при помощи поставщиков форматирования см. в разделе [Форматирование с учетом языка и региональных параметров с помощью поставщиков формата и интерфейса IFormatProvider](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface).</span><span class="sxs-lookup"><span data-stu-id="d76fd-152">For more information about formatting with format providers, see the [Culture-sensitive formatting with format providers and the IFormatProvider interface](#culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface) section.</span></span>  
  
* <span data-ttu-id="d76fd-153">Реализация интерфейса [IFormattable](xref:System.IFormattable), позволяющая преобразовывать строки с помощью класса [Convert](xref:System.Convert) и использовать составное форматирование.</span><span class="sxs-lookup"><span data-stu-id="d76fd-153">Implementing the [IFormattable](xref:System.IFormattable) interface to support both string conversion with the [Convert](xref:System.Convert) class and composite formatting.</span></span> <span data-ttu-id="d76fd-154">Дополнительные сведения см. в разделе [Интерфейс IFormattable](#the-iformattable-interface).</span><span class="sxs-lookup"><span data-stu-id="d76fd-154">For more information, see the [The IFormattable interface](#the-iformattable-interface) section.</span></span>

* <span data-ttu-id="d76fd-155">Использование составного форматирования, позволяющее внедрить строковую презентацию в состав более крупной строки.</span><span class="sxs-lookup"><span data-stu-id="d76fd-155">Using composite formatting to embed the string representation of a value in a larger string.</span></span> <span data-ttu-id="d76fd-156">Дополнительные сведения см. в разделе [Составное форматирование](#composite-formatting).</span><span class="sxs-lookup"><span data-stu-id="d76fd-156">For more information, see the [Composite formatting](#composite-formatting) section.</span></span>

* <span data-ttu-id="d76fd-157">Реализация интерфейсов [ICustomFormatter](xref:System.ICustomFormatter) и [IFormatProvider](xref:System.IFormatProvider), позволяющая создать полноценное настраиваемое решение для форматирования.</span><span class="sxs-lookup"><span data-stu-id="d76fd-157">Implementing [ICustomFormatter](xref:System.ICustomFormatter) and [IFormatProvider](xref:System.IFormatProvider) to provide a complete custom formatting solution.</span></span> <span data-ttu-id="d76fd-158">Дополнительные сведения см. в разделе [Настраиваемое форматирование с использованием интерфейса ICustomFormatter](#custom-formatting-with-icustomformatter).</span><span class="sxs-lookup"><span data-stu-id="d76fd-158">For more information, see the [Custom formatting with ICustomFormatter](#custom-formatting-with-icustomformatter) section.</span></span>

<span data-ttu-id="d76fd-159">В следующих подразделах перечисленные методы преобразования объектов в их строковые представления рассматриваются более подробно.</span><span class="sxs-lookup"><span data-stu-id="d76fd-159">The following sections examine these methods for converting an object to its string representation.</span></span>

## <a name="default-formatting-using-the-tostring-method"></a><span data-ttu-id="d76fd-160">Форматирование по умолчанию при помощи метода ToString</span><span class="sxs-lookup"><span data-stu-id="d76fd-160">Default formatting using the ToString method</span></span>

<span data-ttu-id="d76fd-161">Любой производный от [System.Object](xref:System.Object) тип автоматически наследует метод [ToString](xref:System.Object.ToString) без параметров, по умолчанию возвращающий имя типа.</span><span class="sxs-lookup"><span data-stu-id="d76fd-161">Every type that is derived from [System.Object](xref:System.Object) automatically inherits a parameterless [ToString](xref:System.Object.ToString) method, which returns the name of the type by default.</span></span> <span data-ttu-id="d76fd-162">В следующем примере демонстрируется использование метода [ToString](xref:System.Object.ToString) по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d76fd-162">The following example illustrates the default [ToString](xref:System.Object.ToString) method.</span></span> <span data-ttu-id="d76fd-163">Здесь определен класс с именем `Automobile`, у которого нет реализации.</span><span class="sxs-lookup"><span data-stu-id="d76fd-163">It defines a class named `Automobile` that has no implementation.</span></span> <span data-ttu-id="d76fd-164">При создании экземпляра этого класса и вызове его метода [ToString](xref:System.Object.ToString) отображается имя типа.</span><span class="sxs-lookup"><span data-stu-id="d76fd-164">When the class is instantiated and its [ToString](xref:System.Object.ToString) method is called, it displays its type name.</span></span> <span data-ttu-id="d76fd-165">Обратите внимание, что метод [ToString](xref:System.Object.ToString) не вызывается в примере явным образом.</span><span class="sxs-lookup"><span data-stu-id="d76fd-165">Note that the [ToString](xref:System.Object.ToString) method is not explicitly called in the example.</span></span> <span data-ttu-id="d76fd-166">Метод [Console.WriteLine(Object)](xref:System.Console.WriteLine(System.Object)) неявно вызывает метод [ToString](xref:System.Object.ToString) объекта, переданного ему в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="d76fd-166">The [Console.WriteLine(Object)](xref:System.Console.WriteLine(System.Object)) method implicitly calls the [ToString](xref:System.Object.ToString) method of the object passed to it as an argument.</span></span> 

```csharp
using System;

public class Automobile
{
   // No implementation. All members are inherited from Object.
}

public class Example
{
   public static void Main()
   {
      Automobile firstAuto = new Automobile();
      Console.WriteLine(firstAuto);
   }
}
// The example displays the following output:
//       Automobile
```

```vb 
Public Class Automobile
   ' No implementation. All members are inherited from Object.
End Class

Module Example
   Public Sub Main()
      Dim firstAuto As New Automobile()
      Console.WriteLine(firstAuto)
   End Sub
End Module
' The example displays the following output:
'       Automobile
```

<span data-ttu-id="d76fd-167">Поскольку производными от [Object](xref:System.Object) являются все типы, кроме интерфейсов, данная функциональность автоматически присутствует в пользовательских классах и структурах.</span><span class="sxs-lookup"><span data-stu-id="d76fd-167">Because all types other than interfaces are derived from [Object](xref:System.Object), this functionality is automatically provided to your custom classes or structures.</span></span> <span data-ttu-id="d76fd-168">Тем не менее метод [ToString](xref:System.Object.ToString) по умолчанию обладает весьма ограниченной функциональностью: хотя метод позволяет определить имя типа, никаких сведений об экземпляре типа он не предоставляет.</span><span class="sxs-lookup"><span data-stu-id="d76fd-168">However, the functionality offered by the default [ToString](xref:System.Object.ToString) method, is limited: Although it identifies the type, it fails to provide any information about an instance of the type.</span></span> <span data-ttu-id="d76fd-169">Для формирования строкового представления объекта, позволяющего получить сведения о конкретном объекте, следует переопределить метод [ToString](xref:System.Object.ToString).</span><span class="sxs-lookup"><span data-stu-id="d76fd-169">To provide a string representation of an object that provides information about that object, you must override the [ToString](xref:System.Object.ToString) method.</span></span>

> [!NOTE]
> <span data-ttu-id="d76fd-170">Структуры наследуют от типа [ValueType](xref:System.ValueType), который также является производным от [Object](xref:System.Object).</span><span class="sxs-lookup"><span data-stu-id="d76fd-170">Structures inherit from [ValueType](xref:System.ValueType), which in turn is derived from [Object](xref:System.Object).</span></span> <span data-ttu-id="d76fd-171">Хотя [ValueType](xref:System.ValueType) переопределяет [Object.ToString](xref:System.Object.ToString), его реализация идентична.</span><span class="sxs-lookup"><span data-stu-id="d76fd-171">Although [ValueType](xref:System.ValueType) overrides [Object.ToString](xref:System.Object.ToString), its implementation is identical.</span></span>

## <a name="overriding-the-tostring-method"></a><span data-ttu-id="d76fd-172">Переопределение метода ToString</span><span class="sxs-lookup"><span data-stu-id="d76fd-172">Overriding the ToString method</span></span>

<span data-ttu-id="d76fd-173">Отображение имени типа зачастую малополезно и не позволяет пользователям типов отличить один экземпляр от другого.</span><span class="sxs-lookup"><span data-stu-id="d76fd-173">Displaying the name of a type is often of limited use and does not allow consumers of your types to differentiate one instance from another.</span></span> <span data-ttu-id="d76fd-174">Однако метод [ToString](xref:System.Object.ToString) можно переопределить, чтобы он мог возвращать более функциональное представление значения объекта.</span><span class="sxs-lookup"><span data-stu-id="d76fd-174">However, you can override the [ToString](xref:System.Object.ToString) method to provide a more useful representation of an object’s value.</span></span> <span data-ttu-id="d76fd-175">В следующем примере определяется объект `Temperature`, метод [ToString](xref:System.Object.ToString) которого переопределен и отображает температуру в градусах Цельсия.</span><span class="sxs-lookup"><span data-stu-id="d76fd-175">The following example defines a `Temperature` object and overrides its [ToString](xref:System.Object.ToString) method to display the temperature in degrees Celsius.</span></span>

```csharp
using System;

public class Temperature
{
   private decimal temp;

   public Temperature(decimal temperature)
   {
      this.temp = temperature;   
   }

   public override string ToString()
   {
      return this.temp.ToString("N1") + "°C";
   }
}

public class Example
{
   public static void Main()
   {
      Temperature currentTemperature = new Temperature(23.6m);
      Console.WriteLine("The current temperature is " +
                        currentTemperature.ToString());
   }
}
// The example displays the following output:
//       The current temperature is 23.6°C.
```

```vb
Public Class Temperature
   Private temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.temp = temperature
   End Sub

   Public Overrides Function ToString() As String
      Return Me.temp.ToString("N1") + "°C"   
   End Function
End Class

Module Example
   Public Sub Main()
      Dim currentTemperature As New Temperature(23.6d)
      Console.WriteLine("The current temperature is " +
                        currentTemperature.ToString())
   End Sub
End Module
' The example displays the following output:
'       The current temperature is 23.6°C.
```

<span data-ttu-id="d76fd-176">В платформе .NET метод [ToString](xref:System.Object.ToString) переопределен у всех типов-примитивов значений: вместо имени он отображает значение объекта.</span><span class="sxs-lookup"><span data-stu-id="d76fd-176">In .NET, the [ToString](xref:System.Object.ToString) method of each primitive value type has been overridden to display the object’s value instead of its name.</span></span> <span data-ttu-id="d76fd-177">В следующей таблице показаны переопределения для всех типов-примитивов.</span><span class="sxs-lookup"><span data-stu-id="d76fd-177">The following table shows the override for each primitive type.</span></span> <span data-ttu-id="d76fd-178">Обратите внимание, что большинство переопределенных методов вызывают другую перегрузку метода [ToString](xref:System.Object.ToString) и передают ей описатель формата "G", который задает общий формат типа, и объект [IFormatProvider](xref:System.IFormatProvider), представляющий текущий язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="d76fd-178">Note that most of the overridden methods call another overload of the [ToString](xref:System.Object.ToString) method and pass it the "G" format specifier, which defines the general format for its type, and an [IFormatProvider](xref:System.IFormatProvider) object that represents the current culture.</span></span>

<span data-ttu-id="d76fd-179">Тип</span><span class="sxs-lookup"><span data-stu-id="d76fd-179">Type</span></span> | <span data-ttu-id="d76fd-180">Переопределение ToString</span><span class="sxs-lookup"><span data-stu-id="d76fd-180">ToString override</span></span>
---- | -----------------
[<span data-ttu-id="d76fd-181">Boolean</span><span class="sxs-lookup"><span data-stu-id="d76fd-181">Boolean</span></span>](xref:System.Boolean) | <span data-ttu-id="d76fd-182">Возвращает [Boolean.TrueString](xref:System.Boolean.TrueString) или [Boolean.FalseString](xref:System.Boolean.FalseString).</span><span class="sxs-lookup"><span data-stu-id="d76fd-182">Returns either [Boolean.TrueString](xref:System.Boolean.TrueString) or [Boolean.FalseString](xref:System.Boolean.FalseString).</span></span>
[<span data-ttu-id="d76fd-183">Byte</span><span class="sxs-lookup"><span data-stu-id="d76fd-183">Byte</span></span>](xref:System.Byte) | <span data-ttu-id="d76fd-184">Вызывает метод `Byte.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [Byte](xref:System.Byte) в соответствии с текущим языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="d76fd-184">Calls `Byte.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Byte](xref:System.Byte) value for the current culture.</span></span>
[<span data-ttu-id="d76fd-185">Char</span><span class="sxs-lookup"><span data-stu-id="d76fd-185">Char</span></span>](xref:System.Char) | <span data-ttu-id="d76fd-186">Возвращает символ в виде строки.</span><span class="sxs-lookup"><span data-stu-id="d76fd-186">Returns the character as a string.</span></span>
[<span data-ttu-id="d76fd-187">DateTime</span><span class="sxs-lookup"><span data-stu-id="d76fd-187">DateTime</span></span>](xref:System.DateTime) | <span data-ttu-id="d76fd-188">Вызывает метод `DateTime.ToString("G", DatetimeFormatInfo.CurrentInfo)`, чтобы отформатировать значение даты и времени в соответствии с текущим языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="d76fd-188">Calls `DateTime.ToString("G", DatetimeFormatInfo.CurrentInfo)` to format the date and time value for the current culture.</span></span> 
[<span data-ttu-id="d76fd-189">Decimal</span><span class="sxs-lookup"><span data-stu-id="d76fd-189">Decimal</span></span>](xref:System.Decimal) | <span data-ttu-id="d76fd-190">Вызывает метод `Decimal.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [Decimal](xref:System.Decimal) в соответствии с текущим языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="d76fd-190">Calls `Decimal.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Decimal](xref:System.Decimal) value for the current culture.</span></span>
[<span data-ttu-id="d76fd-191">Double</span><span class="sxs-lookup"><span data-stu-id="d76fd-191">Double</span></span>](xref:System.Double) | <span data-ttu-id="d76fd-192">Вызывает метод `Double.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [Double](xref:System.Double) в соответствии с текущим языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="d76fd-192">Calls `Double.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Double](xref:System.Double) value for the current culture.</span></span>
[<span data-ttu-id="d76fd-193">Int16</span><span class="sxs-lookup"><span data-stu-id="d76fd-193">Int16</span></span>](xref:System.Int16) | <span data-ttu-id="d76fd-194">Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [Int16](xref:System.Int16) в соответствии с текущим языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="d76fd-194">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Int16](xref:System.Int16) value for the current culture.</span></span>
[<span data-ttu-id="d76fd-195">Int32</span><span class="sxs-lookup"><span data-stu-id="d76fd-195">Int32</span></span>](xref:System.Int32) | <span data-ttu-id="d76fd-196">Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [Int32](xref:System.Int32) в соответствии с текущим языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="d76fd-196">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Int32](xref:System.Int32) value for the current culture.</span></span>
[<span data-ttu-id="d76fd-197">Int64</span><span class="sxs-lookup"><span data-stu-id="d76fd-197">Int64</span></span>](xref:System.Int64) | <span data-ttu-id="d76fd-198">Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [Int64](xref:System.Int64) в соответствии с текущим языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="d76fd-198">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Int64](xref:System.Int64) value for the current culture.</span></span>
[<span data-ttu-id="d76fd-199">SByte</span><span class="sxs-lookup"><span data-stu-id="d76fd-199">SByte</span></span>](xref:System.SByte) | <span data-ttu-id="d76fd-200">Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [SByte](xref:System.SByte)</span><span class="sxs-lookup"><span data-stu-id="d76fd-200">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [SByte](xref:System.SByte)</span></span> | <span data-ttu-id="d76fd-201">в соответствии с текущим языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="d76fd-201">value for the current culture.</span></span>
[<span data-ttu-id="d76fd-202">Single</span><span class="sxs-lookup"><span data-stu-id="d76fd-202">Single</span></span>](xref:System.Single) | <span data-ttu-id="d76fd-203">Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [Single](xref:System.Single) в соответствии с текущим языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="d76fd-203">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [Single](xref:System.Single) value for the current culture.</span></span>
[<span data-ttu-id="d76fd-204">UInt32</span><span class="sxs-lookup"><span data-stu-id="d76fd-204">UInt32</span></span>](xref:System.UInt32) | <span data-ttu-id="d76fd-205">Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [UInt32](xref:System.UInt32) в соответствии с текущим языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="d76fd-205">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [UInt32](xref:System.UInt32)value for the current culture.</span></span>
[<span data-ttu-id="d76fd-206">UInt32</span><span class="sxs-lookup"><span data-stu-id="d76fd-206">UInt32</span></span>](xref:System.UInt32) | <span data-ttu-id="d76fd-207">Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [UInt32](xref:System.UInt32) в соответствии с текущим языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="d76fd-207">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [UInt32](xref:System.UInt32) value for the current culture.</span></span>
[<span data-ttu-id="d76fd-208">UInt64</span><span class="sxs-lookup"><span data-stu-id="d76fd-208">UInt64</span></span>](xref:System.UInt64) | <span data-ttu-id="d76fd-209">Вызывает метод `Int16.ToString("G", NumberFormatInfo.CurrentInfo)`, чтобы отформатировать значение [UInt64](xref:System.UInt64) в соответствии с текущим языком и региональными параметрами.</span><span class="sxs-lookup"><span data-stu-id="d76fd-209">Calls `Int16.ToString("G", NumberFormatInfo.CurrentInfo)` to format the [UInt64](xref:System.UInt64)  value for the current culture.</span></span>

## <a name="the-tostring-method-and-format-strings"></a><span data-ttu-id="d76fd-210">Метод ToString и строки формата</span><span class="sxs-lookup"><span data-stu-id="d76fd-210">The ToString method and format strings</span></span>

<span data-ttu-id="d76fd-211">Использовать метод [ToString](xref:System.Object.ToString) по умолчанию или перегрузку [ToString](xref:System.Object.ToString) удобно, если у объекта имеется однозначное строковое представление.</span><span class="sxs-lookup"><span data-stu-id="d76fd-211">Relying on the default [ToString](xref:System.Object.ToString) method or overriding [ToString](xref:System.Object.ToString) is appropriate when an object has a single string representation.</span></span> <span data-ttu-id="d76fd-212">Тем не менее зачастую значение объекта может иметь несколько представлений.</span><span class="sxs-lookup"><span data-stu-id="d76fd-212">However, the value of an object often has multiple representations.</span></span> <span data-ttu-id="d76fd-213">Например, температура может выражаться в градусах по шкале Фаренгейта, Цельсия или Кельвина.</span><span class="sxs-lookup"><span data-stu-id="d76fd-213">For example, a temperature can be expressed in degrees Fahrenheit, degrees Celsius, or kelvins.</span></span> <span data-ttu-id="d76fd-214">Аналогично, целое число 10 можно представить различными способами, включая 10, 10.0, 1.0e01 или $10.00.</span><span class="sxs-lookup"><span data-stu-id="d76fd-214">Similarly, the integer value 10 can be represented in numerous ways, including 10, 10.0, 1.0e01, or $10.00.</span></span>

<span data-ttu-id="d76fd-215">Для реализации нескольких строковых представлений одного значения в платформе .NET используются строки формата.</span><span class="sxs-lookup"><span data-stu-id="d76fd-215">To enable a single value to have multiple string representations, .NET uses format strings.</span></span> <span data-ttu-id="d76fd-216">Строка формата содержит один или несколько предопределенных описателей формата, представляющих собой одиночные символы или группы символов, указывающие, как метод [ToString](xref:System.Object.ToString) должен форматировать вывод.</span><span class="sxs-lookup"><span data-stu-id="d76fd-216">A format string is a string that contains one or more predefined format specifiers, which are single characters or groups of characters that define how the [ToString](xref:System.Object.ToString) method should format its output.</span></span> <span data-ttu-id="d76fd-217">Строка формата передается в качестве параметра методу [ToString](xref:System.Object.ToString) объекта и определяет, как должно выглядеть строковое представление его значения.</span><span class="sxs-lookup"><span data-stu-id="d76fd-217">The format string is then passed as a parameter to the object's [ToString](xref:System.Object.ToString) method and determines how the string representation of that object's value should appear.</span></span>

<span data-ttu-id="d76fd-218">Все числовые типы, типы даты и времени, а также перечисления в составе платформы .NET поддерживают предопределенный набор описателей формата.</span><span class="sxs-lookup"><span data-stu-id="d76fd-218">All numeric types, date and time types, and enumeration types in .NET support a predefined set of format specifiers.</span></span> <span data-ttu-id="d76fd-219">Строки формата также можно использовать для определения разнообразных строковых представлений прикладных пользовательских типов данных.</span><span class="sxs-lookup"><span data-stu-id="d76fd-219">You can also use format strings to define multiple string representations of your application-defined data types.</span></span>

### <a name="standard-format-strings"></a><span data-ttu-id="d76fd-220">Строки стандартного формата</span><span class="sxs-lookup"><span data-stu-id="d76fd-220">Standard format strings</span></span>

<span data-ttu-id="d76fd-221">Строка стандартного формата содержит один описатель формата. Это алфавитный символ, определяющий строковое представление объекта, к которому он применяется. Также строка формата может содержать необязательный описатель точности, определяющий, сколько цифр отображается в результирующей строке.</span><span class="sxs-lookup"><span data-stu-id="d76fd-221">A standard format string contains a single format specifier, which is an alphabetic character that defines the string representation of the object to which it is applied, along with an optional precision specifier that affects how many digits are displayed in the result string.</span></span> <span data-ttu-id="d76fd-222">Если описатель точности не указан или не поддерживается, описатель стандартного формата будет эквивалентен строке стандартного формата.</span><span class="sxs-lookup"><span data-stu-id="d76fd-222">If the precision specifier is omitted or is not supported, a standard format specifier is equivalent to a standard format string.</span></span> 

<span data-ttu-id="d76fd-223">В платформе .NET определяется набор описателей стандартного формата для всех числовых типов, типов даты и времени, а также для всех типов перечислений.</span><span class="sxs-lookup"><span data-stu-id="d76fd-223">.NET defines a set of standard format specifiers for all numeric types, all date and time types, and all enumeration types.</span></span> <span data-ttu-id="d76fd-224">Например, все эти категории поддерживают описатель стандартного формата "G", который определяет общее строковое представление значения соответствующего типа.</span><span class="sxs-lookup"><span data-stu-id="d76fd-224">For example, each of these categories supports a "G" standard format specifier, which defines a general string representation of a value of that type.</span></span>

<span data-ttu-id="d76fd-225">Строки стандартного формата для типов перечислений напрямую определяют строковое представление значения.</span><span class="sxs-lookup"><span data-stu-id="d76fd-225">Standard format strings for enumeration types directly control the string representation of a value.</span></span> <span data-ttu-id="d76fd-226">От строки формата, переданной в метод [ToString](xref:System.Object.ToString) значения перечисления, зависит, будет ли оно представлено своим строковым именем (описатели формата "G" и "F"), базовым целочисленным значением (описатель формата "D") или шестнадцатеричным значением (описатель формата "X").</span><span class="sxs-lookup"><span data-stu-id="d76fd-226">The format strings passed to an enumeration value’s [ToString](xref:System.Object.ToString) method determine whether the value is displayed using its string name (the "G" and "F" format specifiers), its underlying integral value (the "D" format specifier), or its hexadecimal value (the "X" format specifier).</span></span> <span data-ttu-id="d76fd-227">В следующем примере демонстрируется использование строк стандартного формата для форматирования значения перечисления [DayOfWeek](xref:System.DayOfWeek).</span><span class="sxs-lookup"><span data-stu-id="d76fd-227">The following example illustrates the use of standard format strings to format a [DayOfWeek](xref:System.DayOfWeek) enumeration value.</span></span> 

```csharp
DayOfWeek thisDay = DayOfWeek.Monday;
string[] formatStrings = {"G", "F", "D", "X"};

foreach (string formatString in formatStrings)
   Console.WriteLine(thisDay.ToString(formatString));
// The example displays the following output:
//       Monday
//       Monday
//       1
//       00000001
```

```vb
Dim thisDay As DayOfWeek = DayOfWeek.Monday
Dim formatStrings() As String = {"G", "F", "D", "X"}

For Each formatString As String In formatStrings
   Console.WriteLine(thisDay.ToString(formatString))
Next
' The example displays the following output:
'       Monday
'       Monday
'       1
'       00000001
```

<span data-ttu-id="d76fd-228">Информацию о строках форматов перечисления см. в статье [Строки форматов перечисления](enumeration-format.md).</span><span class="sxs-lookup"><span data-stu-id="d76fd-228">For information about enumeration format strings, see [Enumeration format strings](enumeration-format.md).</span></span>

<span data-ttu-id="d76fd-229">Строки стандартного формата для числовых типов обычно задают результирующую строку, точный вид которой зависит от значения одного или нескольких свойств.</span><span class="sxs-lookup"><span data-stu-id="d76fd-229">Standard format strings for numeric types usually define a result string whose precise appearance is controlled by one or more property values.</span></span> <span data-ttu-id="d76fd-230">Например, описатель формата "C" форматирует число в виде значения валюты.</span><span class="sxs-lookup"><span data-stu-id="d76fd-230">For example, the "C" format specifier formats a number as a currency value.</span></span> <span data-ttu-id="d76fd-231">При вызове метода [ToString](xref:System.Object.ToString) с описателем формата "C" в качестве единственного параметра для определения строкового представления числового значения используются следующие свойства объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) для текущего языка и региональных параметров:</span><span class="sxs-lookup"><span data-stu-id="d76fd-231">When you call the [ToString](xref:System.Object.ToString) method with the "C" format specifier as the only parameter, the following property values from the current culture’s [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object are used to define the string representation of the numeric value:</span></span>

* <span data-ttu-id="d76fd-232">Свойство [CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol), определяющее обозначение денежной единицы для текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d76fd-232">The [CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) property, which specifies the current culture’s currency symbol.</span></span>

* <span data-ttu-id="d76fd-233">Свойство [CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) или [CurrencyPositivePattern](xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern), возвращающее целое число, от которого зависят указанные далее моменты.</span><span class="sxs-lookup"><span data-stu-id="d76fd-233">The [CurrencyNegativePattern](xref:System.Globalization.NumberFormatInfo.CurrencyNegativePattern) or [CurrencyPositivePattern](xref:System.Globalization.NumberFormatInfo.CurrencyPositivePattern) property, which returns an integer that determines the following:</span></span> 

    * <span data-ttu-id="d76fd-234">Положение символа валюты.</span><span class="sxs-lookup"><span data-stu-id="d76fd-234">The placement of the currency symbol.</span></span>
    
    * <span data-ttu-id="d76fd-235">Обозначение отрицательных значений: отрицательный знак в начале, отрицательный знак в конце или круглые скобки.</span><span class="sxs-lookup"><span data-stu-id="d76fd-235">Whether negative values are indicated by a leading negative sign, a trailing negative sign, or parentheses.</span></span>
    
    * <span data-ttu-id="d76fd-236">Наличие пробела между числовым значением и символом валюты.</span><span class="sxs-lookup"><span data-stu-id="d76fd-236">Whether a space appears between the numeric value and the currency symbol.</span></span>
    
* <span data-ttu-id="d76fd-237">Свойство [CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits), определяющее число цифр дробной части в результирующей строке.</span><span class="sxs-lookup"><span data-stu-id="d76fd-237">The [CurrencyDecimalDigits](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalDigits) property, which defines the number of fractional digits in the result string.</span></span>

* <span data-ttu-id="d76fd-238">Свойство [CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator), определяющее символ-разделитель целой и дробной частей в результирующей строке.</span><span class="sxs-lookup"><span data-stu-id="d76fd-238">The [CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) property, which defines the decimal separator symbol in the result string.</span></span>

* <span data-ttu-id="d76fd-239">Свойство [CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator), определяющее символ-разделитель групп.</span><span class="sxs-lookup"><span data-stu-id="d76fd-239">The [CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) property, which defines the group separator symbol.</span></span>

* <span data-ttu-id="d76fd-240">Свойство [CurrencyGroupSizes](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes), определяющее число цифр в каждой из групп слева от разделителя целой и дробной частей.</span><span class="sxs-lookup"><span data-stu-id="d76fd-240">The [CurrencyGroupSizes](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSizes) property, which defines the number of digits in each group to the left of the decimal.</span></span>

* <span data-ttu-id="d76fd-241">Свойство [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign), задающее отрицательный знак, который используется в случаях, если скобки не применяются для обозначения отрицательных значений в результирующей строке.</span><span class="sxs-lookup"><span data-stu-id="d76fd-241">The [NegativeSign](xref:System.Globalization.NumberFormatInfo.NegativeSign) property, which determines the negative sign used in the result string if parentheses are not used to indicate negative values.</span></span>

<span data-ttu-id="d76fd-242">Кроме того, строки числового формата могут содержать описатель точности.</span><span class="sxs-lookup"><span data-stu-id="d76fd-242">In addition, numeric format strings may include a precision specifier.</span></span> <span data-ttu-id="d76fd-243">Смысл этого описателя зависит от строки формата, в которой он используется, но обычно он задает общее число цифр в результирующей строке или число цифр в дробной части.</span><span class="sxs-lookup"><span data-stu-id="d76fd-243">The meaning of this specifier depends on the format string with which it is used, but it typically indicates either the total number of digits or the number of fractional digits that should appear in the result string.</span></span> <span data-ttu-id="d76fd-244">В следующем примере используется строка стандартного числового формата с описателем точности ("X4"), что позволяет сформировать строковое значение из четырех шестидесятеричных цифр.</span><span class="sxs-lookup"><span data-stu-id="d76fd-244">For example, the following example uses the "X4" standard numeric string and a precision specifier to create a string value that has four hexadecimal digits.</span></span>

```csharp
byte[] byteValues = { 12, 163, 255 };
foreach (byte byteValue in byteValues)
   Console.WriteLine(byteValue.ToString("X4"));
// The example displays the following output:
//       000C
//       00A3
//       00FF
```

```vb
Dim byteValues() As Byte = { 12, 163, 255 }
For Each byteValue As Byte In byteValues
   Console.WriteLine(byteValue.ToString("X4"))
Next
' The example displays the following output:
'       000C
'       00A3
'       00FF
```

<span data-ttu-id="d76fd-245">Подробности о строках стандартных числовых форматов см. в статье [Строки стандартных числовых форматов](standard-numeric.md).</span><span class="sxs-lookup"><span data-stu-id="d76fd-245">For more information about standard numeric formatting strings, see [Standard numeric format strings](standard-numeric.md).</span></span> 

<span data-ttu-id="d76fd-246">Строки стандартного формата для значений даты и времени — это псевдонимы строк настраиваемого формата, которые хранятся в конкретном свойстве [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo).</span><span class="sxs-lookup"><span data-stu-id="d76fd-246">Standard format strings for date and time values are aliases for custom format strings stored by a particular [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) class.</span></span> <span data-ttu-id="d76fd-247">Например, вызов метода [ToString](xref:System.Object.ToString) применительно к значению даты и времени с описателем формата "D" приведет к отображению даты и времени с помощью настраиваемой строки формата, хранящейся в свойстве [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) для текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d76fd-247">For example, calling the [ToString](xref:System.Object.ToString) method of a date and time value with the "D" format specifier displays the date and time by using the custom format string stored in the current culture’s [DateTimeFormatInfo.LongDatePattern](xref:System.Globalization.DateTimeFormatInfo.LongDatePattern) property.</span></span> <span data-ttu-id="d76fd-248">(Дополнительные сведения о строках настраиваемого формата см. в разделе [Строки настраиваемого формата](#custom-format-strings).) Данная связь показана в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d76fd-248">(For more information about custom format strings, see the [Custom format strings](#custom-format-strings) section.) The following example illustrates this relationship.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      DateTime date1 = new DateTime(2017, 6, 30);
      Console.WriteLine("D Format Specifier:     {0:D}", date1);
      string longPattern = CultureInfo.CurrentCulture.DateTimeFormat.LongDatePattern;
      Console.WriteLine("'{0}' custom format string:     {1}", 
                        longPattern, date1.ToString(longPattern));
   }
}
// The example displays the following output when run on a system whose
// current culture is en-US:
//    D Format Specifier:     Tuesday, June 30, 2017
//    'dddd, MMMM dd, yyyy' custom format string:     Tuesday, June 30, 2017
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim date1 As Date = #6/30/2009#
      Console.WriteLine("D Format Specifier:     {0:D}", date1)
      Dim longPattern As String = CultureInfo.CurrentCulture.DateTimeFormat.LongDatePattern
      Console.WriteLine("'{0}' custom format string:     {1}", _
                        longPattern, date1.ToString(longPattern))
   End Sub
End Module
' The example displays the following output when run on a system whose
' current culture is en-US:
'    D Format Specifier:     Tuesday, June 30, 2009
'    'dddd, MMMM dd, yyyy' custom format string:     Tuesday, June 30, 2009
```

<span data-ttu-id="d76fd-249">Дополнительные сведения о строках стандартных форматов даты и времени см. в статье [Строки стандартных форматов даты и времени](standard-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="d76fd-249">For more information about standard date and time format strings, see [Standard date and time format strings](standard-datetime.md).</span></span>

<span data-ttu-id="d76fd-250">Строки стандартного формата также можно использовать для определения строкового представления прикладного объекта, формируемого с помощью метода `ToString(String)` такого объекта.</span><span class="sxs-lookup"><span data-stu-id="d76fd-250">You can also use standard format strings to define the string representation of an application-defined object that is produced by the object’s `ToString(String)` method.</span></span> <span data-ttu-id="d76fd-251">Можно определить конкретные описатели стандартного формата, поддерживаемые объектом, а также решить, будут ли они зависеть от регистра символов.</span><span class="sxs-lookup"><span data-stu-id="d76fd-251">You can define the specific standard format specifiers that your object supports, and you can determine whether they are case-sensitive or case-insensitive.</span></span> <span data-ttu-id="d76fd-252">Реализация метода `ToString(String)` должна отвечать следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="d76fd-252">Your implementation of the `ToString(String)` method should support the following:</span></span>

* <span data-ttu-id="d76fd-253">Должен поддерживаться описатель формата "G", отвечающий за представление обычного или общего формата объекта.</span><span class="sxs-lookup"><span data-stu-id="d76fd-253">A "G" format specifier that represents a customary or common format of the object.</span></span> <span data-ttu-id="d76fd-254">Перегрузка метода `ToString` объекта, не имеющая параметров, должна вызывать его перегрузку `ToString(String)`, передавая ей строку стандартного формата "G".</span><span class="sxs-lookup"><span data-stu-id="d76fd-254">The parameterless overload of your object's `ToString` method should call its `ToString(String)` overload and pass it the "G" standard format string.</span></span>

* <span data-ttu-id="d76fd-255">Должен поддерживаться описатель формата, равный пустой ссылке.</span><span class="sxs-lookup"><span data-stu-id="d76fd-255">Support for a format specifier that is equal to a null reference.</span></span> <span data-ttu-id="d76fd-256">Описатель формата, равный пустой ссылке, должен рассматриваться как эквивалент описателя формата "G".</span><span class="sxs-lookup"><span data-stu-id="d76fd-256">A format specifier that is equal to a null reference should be considered equivalent to the "G" format specifier.</span></span>

<span data-ttu-id="d76fd-257">Например, во внутреннем представлении класса `Temperature` температура может храниться в градусах Цельсия, а для представления значения объекта `Temperature` в градусах Цельсия, Фаренгейта или Кельвина могут использоваться различные описатели формата.</span><span class="sxs-lookup"><span data-stu-id="d76fd-257">For example, a `Temperature` class can internally store the temperature in degrees Celsius and use format specifiers to represent the value of the `Temperature` object in degrees Celsius, degrees Fahrenheit, and kelvins.</span></span> <span data-ttu-id="d76fd-258">Ниже приведен пример.</span><span class="sxs-lookup"><span data-stu-id="d76fd-258">The following example provides an illustration.</span></span>

```csharp
using System;

public class Temperature
{
   private decimal m_Temp;

   public Temperature(decimal temperature)
   {
      this.m_Temp = temperature;
   }

   public decimal Celsius
   {
      get { return this.m_Temp; }
   }

   public decimal Kelvin
   {
      get { return this.m_Temp + 273.15m; }   
   }

   public decimal Fahrenheit
   {
      get { return Math.Round(((decimal) (this.m_Temp * 9 / 5 + 32)), 2); }
   }

   public override string ToString()
   {
      return this.ToString("C");
   }

   public string ToString(string format)
   {  
      // Handle null or empty string.
      if (String.IsNullOrEmpty(format)) format = "C";
      // Remove spaces and convert to uppercase.
      format = format.Trim().ToUpperInvariant();      

      // Convert temperature to Fahrenheit and return string.
      switch (format)
      {
         // Convert temperature to Fahrenheit and return string.
         case "F":
            return this.Fahrenheit.ToString("N2") + " °F";
         // Convert temperature to Kelvin and return string.
         case "K":
            return this.Kelvin.ToString("N2") + " K";
         // return temperature in Celsius.
         case "G":
         case "C":
            return this.Celsius.ToString("N2") + " °C";
         default:
            throw new FormatException(String.Format("The '{0}' format string is not supported.", format));
      }      
   }
}

public class Example
{
   public static void Main()
   {
      Temperature temp1 = new Temperature(0m);
      Console.WriteLine(temp1.ToString());
      Console.WriteLine(temp1.ToString("G"));
      Console.WriteLine(temp1.ToString("C"));
      Console.WriteLine(temp1.ToString("F"));
      Console.WriteLine(temp1.ToString("K"));

      Temperature temp2 = new Temperature(-40m);
      Console.WriteLine(temp2.ToString());
      Console.WriteLine(temp2.ToString("G"));
      Console.WriteLine(temp2.ToString("C"));
      Console.WriteLine(temp2.ToString("F"));
      Console.WriteLine(temp2.ToString("K"));

      Temperature temp3 = new Temperature(16m);
      Console.WriteLine(temp3.ToString());
      Console.WriteLine(temp3.ToString("G"));
      Console.WriteLine(temp3.ToString("C"));
      Console.WriteLine(temp3.ToString("F"));
      Console.WriteLine(temp3.ToString("K"));

      Console.WriteLine(String.Format("The temperature is now {0:F}.", temp3));
   }
}
// The example displays the following output:
//       0.00 °C
//       0.00 °C
//       0.00 °C
//       32.00 °F
//       273.15 K
//       -40.00 °C
//       -40.00 °C
//       -40.00 °C
//       -40.00 °F
//       233.15 K
//       16.00 °C
//       16.00 °C
//       16.00 °C
//       60.80 °F
//       289.15 K
//       The temperature is now 16.00 °C.
```

```vb
Public Class Temperature
   Private m_Temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.m_Temp = temperature
   End Sub

   Public ReadOnly Property Celsius() As Decimal
      Get
         Return Me.m_Temp
      End Get   
   End Property

   Public ReadOnly Property Kelvin() As Decimal
      Get
         Return Me.m_Temp + 273.15d   
      End Get
   End Property

   Public ReadOnly Property Fahrenheit() As Decimal
      Get
         Return Math.Round(CDec(Me.m_Temp * 9 / 5 + 32), 2)
      End Get      
   End Property

   Public Overrides Function ToString() As String
      Return Me.ToString("C")
   End Function

   Public Overloads Function ToString(format As String) As String  
      ' Handle null or empty string.
      If String.IsNullOrEmpty(format) Then format = "C"
      ' Remove spaces and convert to uppercase.
      format = format.Trim().ToUpperInvariant()      

      Select Case format
         Case "F"
           ' Convert temperature to Fahrenheit and return string.
            Return Me.Fahrenheit.ToString("N2") & " °F"
         Case "K"
            ' Convert temperature to Kelvin and return string.
            Return Me.Kelvin.ToString("N2") & " K"
         Case "C", "G"
            ' Return temperature in Celsius.
            Return Me.Celsius.ToString("N2") & " °C"
         Case Else
            Throw New FormatException(String.Format("The '{0}' format string is not supported.", format))
      End Select      
   End Function
End Class

Public Module Example
   Public Sub Main()
      Dim temp1 As New Temperature(0d)
      Console.WriteLine(temp1.ToString())
      Console.WriteLine(temp1.ToString("G"))
      Console.WriteLine(temp1.ToString("C"))
      Console.WriteLine(temp1.ToString("F"))
      Console.WriteLine(temp1.ToString("K"))

      Dim temp2 As New Temperature(-40d)
      Console.WriteLine(temp2.ToString())
      Console.WriteLine(temp2.ToString("G"))
      Console.WriteLine(temp2.ToString("C"))
      Console.WriteLine(temp2.ToString("F"))
      Console.WriteLine(temp2.ToString("K"))

      Dim temp3 As New Temperature(16d)
      Console.WriteLine(temp3.ToString())
      Console.WriteLine(temp3.ToString("G"))
      Console.WriteLine(temp3.ToString("C"))
      Console.WriteLine(temp3.ToString("F"))
      Console.WriteLine(temp3.ToString("K"))

      Console.WriteLine(String.Format("The temperature is now {0:F}.", temp3))
   End Sub
End Module
' The example displays the following output:
'       0.00 °C
'       0.00 °C
'       0.00 °C
'       32.00 °F
'       273.15 K
'       -40.00 °C
'       -40.00 °C
'       -40.00 °C
'       -40.00 °F
'       233.15 K
'       16.00 °C
'       16.00 °C
'       16.00 °C
'       60.80 °F
'       289.15 K
'       The temperature is now 16.00 °C.
```

### <a name="custom-format-strings"></a><span data-ttu-id="d76fd-259">Строки настраиваемого формата</span><span class="sxs-lookup"><span data-stu-id="d76fd-259">Custom format strings</span></span>

<span data-ttu-id="d76fd-260">Помимо строк стандартного формата, в платформе .NET для числовых значений и значений даты и времени определяются строки настраиваемого формата.</span><span class="sxs-lookup"><span data-stu-id="d76fd-260">In addition to the standard format strings, .NET defines custom format strings for both numeric values and date and time values.</span></span> <span data-ttu-id="d76fd-261">Строка настраиваемого формата состоит из одного или нескольких описателей настраиваемого формата, описывающих строковое представление значения.</span><span class="sxs-lookup"><span data-stu-id="d76fd-261">A custom format string consists of one or more custom format specifiers that define the string representation of a value.</span></span> <span data-ttu-id="d76fd-262">Например, строка настраиваемого формата даты и времени, заданная как "yyyy/mm/dd hh:mm:ss.ffff t zzz", преобразует дату в строковое представления вида "2008/11/15 07:45:00.0000 P -08:00" для языка и региональных параметров "en-US".</span><span class="sxs-lookup"><span data-stu-id="d76fd-262">For example, the custom date and time format string "yyyy/mm/dd hh:mm:ss.ffff t zzz" converts a date to its string representation in the form "2008/11/15 07:45:00.0000 P -08:00" for the en-US culture.</span></span> <span data-ttu-id="d76fd-263">Аналогично строка настраиваемого формата "0000" приведет к преобразованию целочисленного значения 12 в строку "0012".</span><span class="sxs-lookup"><span data-stu-id="d76fd-263">Similarly, the custom format string "0000" converts the integer value 12 to "0012".</span></span> <span data-ttu-id="d76fd-264">Полный список строк настраиваемых форматов см. в статьях [Строки настраиваемых форматов даты и времени](custom-datetime.md) и [Строки настраиваемых числовых форматов](custom-numeric.md).</span><span class="sxs-lookup"><span data-stu-id="d76fd-264">For a complete list of custom format strings, see [Custom date and time format strings](custom-datetime.md) and [Custom numeric format strings](custom-numeric.md).</span></span>

<span data-ttu-id="d76fd-265">Если строка формата состоит из одного описателя настраиваемого формата, то перед ним должен стоять символ процента (%), чтобы его можно было отличить от описателя стандартного формата.</span><span class="sxs-lookup"><span data-stu-id="d76fd-265">If a format string consists of a single custom format specifier, the format specifier should be preceded by the percent (%) symbol to avoid confusion with a standard format specifier.</span></span> <span data-ttu-id="d76fd-266">В следующем примере описатель настраиваемого формата "М" используется для вывода одно- или двухзначного числа месяца для определенной даты.</span><span class="sxs-lookup"><span data-stu-id="d76fd-266">The following example uses the "M" custom format specifier to display a one-digit or two-digit number of the month of a particular date.</span></span>

```csharp
DateTime date1 = new DateTime(2009, 9, 8);
Console.WriteLine(date1.ToString("%M"));       
// Displays 9
```

```vb
Dim date1 As Date = #09/08/2009#
Console.WriteLine(date1.ToString("%M"))      ' Displays 9
```

<span data-ttu-id="d76fd-267">Многие строки стандартного формата для значений даты и времени являются псевдонимами для строк настраиваемого формата, определяемых свойствами объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo).</span><span class="sxs-lookup"><span data-stu-id="d76fd-267">Many standard format strings for date and time values are aliases for custom format strings that are defined by properties of the [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object.</span></span> <span data-ttu-id="d76fd-268">Строки настраиваемого формата также позволяют добиться значительной гибкости в реализации прикладного форматирования числовых значений или значений даты и времени.</span><span class="sxs-lookup"><span data-stu-id="d76fd-268">Custom format strings also offer considerable flexibility in providing application-defined formatting for numeric values or date and time values.</span></span> <span data-ttu-id="d76fd-269">Можно определить собственные настраиваемые результирующие строки для числовых значений и значений даты и времени, объединив несколько описателей настраиваемого формата в одной строке настраиваемого формата.</span><span class="sxs-lookup"><span data-stu-id="d76fd-269">You can define your own custom result strings for both numeric values and date and time values by combining multiple custom format specifiers into a single custom format string.</span></span> <span data-ttu-id="d76fd-270">В следующем примере определяется строка настраиваемого формата, отображающая день недели в скобках после названия месяца, числа и года.</span><span class="sxs-lookup"><span data-stu-id="d76fd-270">The following example defines a custom format string that displays the day of the week in parentheses after the month name, day, and year.</span></span>

```csharp
string customFormat = "MMMM dd, yyyy (dddd)";
DateTime date1 = new DateTime(2009, 8, 28);
Console.WriteLine(date1.ToString(customFormat));   
// The example displays the following output if run on a system
// whose language is English:
//       August 28, 2009 (Friday) 
```

```vb
Dim customFormat As String = "MMMM dd, yyyy (dddd)"
Dim date1 As Date = #8/28/2009#
Console.WriteLine(date1.ToString(customFormat))   
' The example displays the following output if run on a system
' whose language is English:
'       August 28, 2009 (Friday) 
```

<span data-ttu-id="d76fd-271">В следующем примере определяется строка настраиваемого формата, которая отображает значение [Int64](xref:System.Int64) как стандартный 7-значный американский номер телефона вместе с кодом города.</span><span class="sxs-lookup"><span data-stu-id="d76fd-271">The following example defines a custom format string that displays an [Int64](xref:System.Int64) value as a standard, seven-digit U.S. telephone number along with its area code.</span></span> 

```csharp
using System;

public class Example
{
   public static void Main()
   {
      long number = 8009999999;
      string fmt = "000-000-0000";
      Console.WriteLine(number.ToString(fmt));
   }
}
// The example displays the following output:
//        800-999-9999
```

```vb
Module Example
   Public Sub Main()
      Dim number As Long = 8009999999
      Dim fmt As String = "000-000-0000"
      Console.WriteLine(number.ToString(fmt))
   End Sub
End Module
' The example displays the following output:

' The example displays the following output:
'       800-999-9999
```

<span data-ttu-id="d76fd-272">Хотя строк стандартного формата обычно достаточно для выполнения большинства задач форматирования прикладных типов, для форматирования пользовательских типов также можно определять описатели настраиваемого формата.</span><span class="sxs-lookup"><span data-stu-id="d76fd-272">Although standard format strings can generally handle most of the formatting needs for your application-defined types, you may also define custom format specifiers to format your types.</span></span> 

### <a name="format-strings-and-net-types"></a><span data-ttu-id="d76fd-273">Строки форматов и типы .NET</span><span class="sxs-lookup"><span data-stu-id="d76fd-273">Format strings and .NET types</span></span>

<span data-ttu-id="d76fd-274">Все числовые типы (то есть [Byte](xref:System.Byte), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64) и [BigInteger](xref:System.Numerics.BigInteger)), а также [DateTime](xref:System.DateTime), [DateTimeOffset](xref:System.DateTimeOffset), [TimeSpan](xref:System.TimeSpan), [Guid](xref:System.Guid) и все типы перечислений поддерживают форматирование с помощью строк форматов.</span><span class="sxs-lookup"><span data-stu-id="d76fd-274">All numeric types (that is, the [Byte](xref:System.Byte), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32), [UInt64](xref:System.UInt64), and [BigInteger](xref:System.Numerics.BigInteger) types), as well as the [DateTime](xref:System.DateTime), [DateTimeOffset](xref:System.DateTimeOffset), [TimeSpan](xref:System.TimeSpan), [Guid](xref:System.Guid), and all enumeration types, support formatting with format strings.</span></span> <span data-ttu-id="d76fd-275">Сведения о конкретных строках форматов, поддерживаемых каждым типом, см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="d76fd-275">For information on the specific format strings supported by each type, see the following topics:</span></span> 

<span data-ttu-id="d76fd-276">Заголовок</span><span class="sxs-lookup"><span data-stu-id="d76fd-276">Title</span></span> | <span data-ttu-id="d76fd-277">Определение</span><span class="sxs-lookup"><span data-stu-id="d76fd-277">Definition</span></span>
----- | ----------
[<span data-ttu-id="d76fd-278">Строки стандартных числовых форматов</span><span class="sxs-lookup"><span data-stu-id="d76fd-278">Standard numeric format strings</span></span>](standard-numeric.md) | <span data-ttu-id="d76fd-279">Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления числовых значений.</span><span class="sxs-lookup"><span data-stu-id="d76fd-279">Describes standard format strings that create commonly used string representations of numeric values.</span></span> 
[<span data-ttu-id="d76fd-280">Строки настраиваемых числовых форматов</span><span class="sxs-lookup"><span data-stu-id="d76fd-280">Custom numeric format strings</span></span>](custom-numeric.md) | <span data-ttu-id="d76fd-281">Описание строк настраиваемого формата, позволяющих создавать прикладные строковые представления числовых значений.</span><span class="sxs-lookup"><span data-stu-id="d76fd-281">Describes custom format strings that create application-specific formats for numeric values.</span></span>
[<span data-ttu-id="d76fd-282">Строки стандартных форматов даты и времени</span><span class="sxs-lookup"><span data-stu-id="d76fd-282">Standard date and time format strings</span></span>](standard-datetime.md) | <span data-ttu-id="d76fd-283">Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления значений [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="d76fd-283">Describes standard format strings that create commonly used string representations of [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="d76fd-284">Строки настраиваемых форматов даты и времени</span><span class="sxs-lookup"><span data-stu-id="d76fd-284">Custom date and time format strings</span></span>](custom-datetime.md) | <span data-ttu-id="d76fd-285">Описание строк настраиваемого формата, позволяющих создавать характерные для приложений форматы для значений [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="d76fd-285">Describes custom format strings that create application-specific formats for [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="d76fd-286">Строки стандартного формата TimeSpan</span><span class="sxs-lookup"><span data-stu-id="d76fd-286">Standard TimeSpan format Strings</span></span>](standard-timespan.md) | <span data-ttu-id="d76fd-287">Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления интервалов времени.</span><span class="sxs-lookup"><span data-stu-id="d76fd-287">Describes standard format strings that create commonly used string representations of time intervals.</span></span>
[<span data-ttu-id="d76fd-288">Строки настраиваемого формата TimeSpan</span><span class="sxs-lookup"><span data-stu-id="d76fd-288">Custom TimeSpan format strings</span></span>](custom-timespan.md) | <span data-ttu-id="d76fd-289">Описание строк настраиваемого формата, позволяющих создавать прикладные строковые представления интервалов времени.</span><span class="sxs-lookup"><span data-stu-id="d76fd-289">Describes custom format strings that create application-specific formats for time intervals.</span></span>
[<span data-ttu-id="d76fd-290">Строки форматов перечисления</span><span class="sxs-lookup"><span data-stu-id="d76fd-290">Enumeration format strings</span></span>](enumeration-format.md) | <span data-ttu-id="d76fd-291">Описание строк стандартного формата, используемых для создания строковых представлений значений перечислений.</span><span class="sxs-lookup"><span data-stu-id="d76fd-291">Describes standard format strings that are used to create string representations of enumeration values.</span></span>
<span data-ttu-id="d76fd-292">[Guid.ToString(String)](xref:System.Guid.ToString(System.String))</span><span class="sxs-lookup"><span data-stu-id="d76fd-292">[Guid.ToString(String)](xref:System.Guid.ToString(System.String))</span></span> | <span data-ttu-id="d76fd-293">Описание строк стандартного формата для значений [Guid](xref:System.Guid).</span><span class="sxs-lookup"><span data-stu-id="d76fd-293">Describes standard format strings for [Guid](xref:System.Guid) values.</span></span>

## <a name="culture-sensitive-formatting-with-format-providers-and-the-iformatprovider-interface"></a><span data-ttu-id="d76fd-294">Форматирование с учетом языка и региональных параметров с помощью поставщиков формата и интерфейса IFormatProvider</span><span class="sxs-lookup"><span data-stu-id="d76fd-294">Culture-Sensitive Formatting with Format Providers and the IFormatProvider Interface</span></span>

<span data-ttu-id="d76fd-295">Хотя описатели формата позволяют настраивать форматирование объектов, для формирования осмысленного строкового представления объектов зачастую требуется дополнительная информация, связанная с форматированием.</span><span class="sxs-lookup"><span data-stu-id="d76fd-295">Although format specifiers let you customize the formatting of objects, producing a meaningful string representation of objects often requires additional formatting information.</span></span> <span data-ttu-id="d76fd-296">Например, при форматировании числового значения в формате валюты с помощью строки стандартного формата "C" или строки настраиваемого формата "$ #,#.00" для включения в отформатированную строку должен быть известен нужный символ валюты, разделитель групп, а также разделитель целой и дробной частей.</span><span class="sxs-lookup"><span data-stu-id="d76fd-296">For example, formatting a number as a currency value by using either the "C" standard format string or a custom format string such as "$ #,#.00" requires, at a minimum, information about the correct currency symbol, group separator, and decimal separator to be available to include in the formatted string.</span></span> <span data-ttu-id="d76fd-297">В платформе .NET подобные дополнительные сведения предоставляются с помощью интерфейса [IFormatProvider](xref:System.IFormatProvider), передаваемого в качестве параметра одной или нескольких перегрузок метода `ToString` для числовых типов и типов даты и времени.</span><span class="sxs-lookup"><span data-stu-id="d76fd-297">In .NET, this additional formatting information is made available through the [IFormatProvider](xref:System.IFormatProvider) interface, which is provided as a parameter to one or more overloads of the `ToString` method of numeric types and date and time types.</span></span> <span data-ttu-id="d76fd-298">Реализации [IFormatProvider](xref:System.IFormatProvider) используются в .NET для поддержки форматирования с учетом языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d76fd-298">[IFormatProvider](xref:System.IFormatProvider) implementations are used in .NET to support culture-specific formatting.</span></span> <span data-ttu-id="d76fd-299">В следующем примере показано, как меняется строковое представление объекта при его форматировании с использованием трех разных объектов [IFormatProvider](xref:System.IFormatProvider), представляющих разные язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="d76fd-299">The following example illustrates how the string representation of an object changes when it is formatted with three [IFormatProvider](xref:System.IFormatProvider) objects that represent different cultures.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      decimal value = 1603.42m;
      Console.WriteLine(value.ToString("C3", new CultureInfo("en-US")));
      Console.WriteLine(value.ToString("C3", new CultureInfo("fr-FR")));
      Console.WriteLine(value.ToString("C3", new CultureInfo("de-DE")));
   }
}
// The example displays the following output:
//       $1,603.420
//       1 603,420 €
//       1.603,420 €
```

```vb
Imports System.Globalization

Public Module Example
   Public Sub Main()
      Dim value As Decimal = 1603.42d
      Console.WriteLine(value.ToString("C3", New CultureInfo("en-US")))
      Console.WriteLine(value.ToString("C3", New CultureInfo("fr-FR")))
      Console.WriteLine(value.ToString("C3", New CultureInfo("de-DE")))
   End Sub
End Module
' The example displays the following output:
'       $1,603.420
'       1 603,420 €
'       1.603,420 €
```

<span data-ttu-id="d76fd-300">Интерфейс [IFormatProvider](xref:System.IFormatProvider) включает один метод [GetFormat(Type)](xref:System.IFormatProvider.GetFormat(System.Type)), имеющий один параметр, задающий тип объекта, который предоставляет сведения о форматировании.</span><span class="sxs-lookup"><span data-stu-id="d76fd-300">The [IFormatProvider](xref:System.IFormatProvider) interface includes one method, [GetFormat(Type)](xref:System.IFormatProvider.GetFormat(System.Type)), which has a single parameter that specifies the type of object that provides formatting information.</span></span> <span data-ttu-id="d76fd-301">Если метод может предоставить объект указанного типа, то он его возвращает.</span><span class="sxs-lookup"><span data-stu-id="d76fd-301">If the method can provide an object of that type, it returns it.</span></span> <span data-ttu-id="d76fd-302">В противном случае метод возвращает пустую ссылку.</span><span class="sxs-lookup"><span data-stu-id="d76fd-302">Otherwise, it returns a null reference.</span></span>

<span data-ttu-id="d76fd-303">[IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) — это метод обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="d76fd-303">[IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) is a callback method.</span></span> <span data-ttu-id="d76fd-304">При вызове перегрузки метода `ToString`, имеющей параметр [IFormatProvider](xref:System.IFormatProvider), вызывается метод [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) соответствующего объекта [IFormatProvider](xref:System.IFormatProvider).</span><span class="sxs-lookup"><span data-stu-id="d76fd-304">When you call a `ToString` method overload that includes an [IFormatProvider](xref:System.IFormatProvider) parameter, it calls the [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method of that [IFormatProvider](xref:System.IFormatProvider) object.</span></span> <span data-ttu-id="d76fd-305">Метод [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) должен вернуть в метод `ToString` объект, способный предоставить необходимые сведения о форматировании и соответствующий параметру *formatType*.</span><span class="sxs-lookup"><span data-stu-id="d76fd-305">The [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method is responsible for returning an object that provides the necessary formatting information, as specified by its *formatType* parameter, to the `ToString` method.</span></span> 

<span data-ttu-id="d76fd-306">Многие методы форматирования и преобразования строк имеют параметр типа [IFormatProvider](xref:System.IFormatProvider), но во многих случаях значение параметра игнорируется при вызове метода.</span><span class="sxs-lookup"><span data-stu-id="d76fd-306">A number of formatting or string conversion methods include a parameter of type [IFormatProvider](xref:System.IFormatProvider), but in many cases the value of the parameter is ignored when the method is called.</span></span> <span data-ttu-id="d76fd-307">В следующей таблице перечислены некоторые методы форматирования, использующие этот параметр. Для каждого метода также указывается тип объекта [Type](xref:System.Type), передаваемого в метод [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)).</span><span class="sxs-lookup"><span data-stu-id="d76fd-307">The following table lists some of the formatting methods that use the parameter and the type of the [Type](xref:System.Type) object that they pass to the [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method.</span></span> 

<span data-ttu-id="d76fd-308">Метод</span><span class="sxs-lookup"><span data-stu-id="d76fd-308">Method</span></span> | <span data-ttu-id="d76fd-309">Тип параметра *formatType*</span><span class="sxs-lookup"><span data-stu-id="d76fd-309">Type of *formatType* parameter</span></span>
------ | ------------------------------
<span data-ttu-id="d76fd-310">Метод `ToString` для числовых типов</span><span class="sxs-lookup"><span data-stu-id="d76fd-310">`ToString` method of numeric types</span></span> | [<span data-ttu-id="d76fd-311">System.Globalization.NumberFormatInfo</span><span class="sxs-lookup"><span data-stu-id="d76fd-311">System.Globalization.NumberFormatInfo</span></span>](xref:System.Globalization.NumberFormatInfo)
<span data-ttu-id="d76fd-312">Метод `ToString` для типов даты и времени</span><span class="sxs-lookup"><span data-stu-id="d76fd-312">`ToString` method of date and time types</span></span> | [<span data-ttu-id="d76fd-313">System.Globalization.DateTimeFormatInfo</span><span class="sxs-lookup"><span data-stu-id="d76fd-313">System.Globalization.DateTimeFormatInfo</span></span>](xref:System.Globalization.DateTimeFormatInfo)
<span data-ttu-id="d76fd-314">[String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="d76fd-314">[String.Format](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))</span></span> | [<span data-ttu-id="d76fd-315">System.ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="d76fd-315">System.ICustomFormatter</span></span>](xref:System.ICustomFormatter)
<span data-ttu-id="d76fd-316">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span><span class="sxs-lookup"><span data-stu-id="d76fd-316">[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object))</span></span> | [<span data-ttu-id="d76fd-317">System.ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="d76fd-317">System.ICustomFormatter</span></span>](xref:System.ICustomFormatter)

<span data-ttu-id="d76fd-318">В составе платформы .NET есть три класса, реализующих интерфейс [IFormatProvider](xref:System.IFormatProvider).</span><span class="sxs-lookup"><span data-stu-id="d76fd-318">.NET provides three classes that implement [IFormatProvider](xref:System.IFormatProvider):</span></span> 

* <span data-ttu-id="d76fd-319">[DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo): класс, предоставляющий сведения о форматировании значений даты и времени для конкретного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d76fd-319">[DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), a class that provides formatting information for date and time values for a specific culture.</span></span> <span data-ttu-id="d76fd-320">Реализация метода [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) в этом классе возвращает его экземпляр.</span><span class="sxs-lookup"><span data-stu-id="d76fd-320">Its [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) implementation returns an instance of itself.</span></span>

* <span data-ttu-id="d76fd-321">[NumberFormatInfo](xref:System.Globalization.NumberFormatInfo): класс, предоставляющий сведения о форматировании числовых значений для конкретного языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d76fd-321">[NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), a class that provides numeric formatting information for a specific culture.</span></span> <span data-ttu-id="d76fd-322">Реализация метода [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) в этом классе возвращает его экземпляр.</span><span class="sxs-lookup"><span data-stu-id="d76fd-322">Its [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) implementation returns an instance of itself.</span></span>

* <span data-ttu-id="d76fd-323">[CultureInfo](xref:System.Globalization.CultureInfo).</span><span class="sxs-lookup"><span data-stu-id="d76fd-323">[CultureInfo](xref:System.Globalization.CultureInfo).</span></span> <span data-ttu-id="d76fd-324">Реализация метода [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) в этом классе возвращает объект [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), предоставляющий сведения о форматировании числовых значений, либо объект [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), предоставляющий сведения о форматировании значений даты и времени.</span><span class="sxs-lookup"><span data-stu-id="d76fd-324">Its [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) implementation can return either a [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object to provide numeric formatting information or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object to provide formatting information for date and time values.</span></span> 

<span data-ttu-id="d76fd-325">Также можно реализовать пользовательский поставщик форматирования, позволяющий заменить любой из этих классов.</span><span class="sxs-lookup"><span data-stu-id="d76fd-325">You can also implement your own format provider to replace any one of these classes.</span></span> <span data-ttu-id="d76fd-326">При этом пользовательская реализация метода `GetFormat`, рассчитанная на предоставление сведений о форматировании для метода `ToString`, должна возвращать объект одного из типов, перечисленных в приведенной выше таблице.</span><span class="sxs-lookup"><span data-stu-id="d76fd-326">However, your implementation’s `GetFormat` method must return an object of the type listed in the previous table if it has to provide formatting information to the `ToString` method.</span></span>

### <a name="culture-sensitive-formatting-of-numeric-values"></a><span data-ttu-id="d76fd-327">Форматирование числовых значений, зависящее от языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="d76fd-327">Culture-sensitive formatting of numeric values</span></span>

<span data-ttu-id="d76fd-328">По умолчанию форматирование числовых значений зависит от языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d76fd-328">By default, the formatting of numeric values is culture-sensitive.</span></span> <span data-ttu-id="d76fd-329">Если не указать язык и региональные параметры при вызове метода форматирования, используются соглашения о форматировании текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d76fd-329">If you do not specify a culture when you call a formatting method, the formatting conventions of the current thread culture are used.</span></span> <span data-ttu-id="d76fd-330">Это продемонстрировано в следующем примере, который изменяет текущие язык и региональные параметры четыре раза, а затем вызывает метод [Decimal.ToString(String)](xref:System.Decimal.ToString(System.String)).</span><span class="sxs-lookup"><span data-stu-id="d76fd-330">This is illustrated in the following example, which changes the current thread culture four times and then calls the [Decimal.ToString(String)](xref:System.Decimal.ToString(System.String)) method.</span></span> <span data-ttu-id="d76fd-331">В каждом случае результирующая строка отражает соглашения о форматировании текущих языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d76fd-331">In each case, the result string reflects the formatting conventions of the current culture.</span></span> <span data-ttu-id="d76fd-332">Это происходит потому, что методы `ToString` и `ToString(String)` создают оболочки для вызовов метода `ToString(String, IFormatProvider)` каждого числового типа.</span><span class="sxs-lookup"><span data-stu-id="d76fd-332">This is because the `ToString` and `ToString(String)` methods wrap calls to each numeric type's `ToString(String, IFormatProvider)` method.</span></span> 

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] cultureNames = { "en-US", "fr-FR", "es-MX", "de-DE" };
      Decimal value = 1043.17m;

      foreach (var cultureName in cultureNames) {
         // Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName);
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name);
         Console.WriteLine(value.ToString("C2"));
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The current culture is en-US
//       $1,043.17
//       
//       The current culture is fr-FR
//       1 043,17 €
//       
//       The current culture is es-MX
//       $1,043.17
//       
//       The current culture is de-DE
//       1.043,17 €
```

```vb
Imports System.Globalization
Imports System.Threading 

Module Example
   Public Sub Main()
      Dim cultureNames() As String = { "en-US", "fr-FR", "es-MX", "de-DE" }
      Dim value As Decimal = 1043.17d 

      For Each cultureName In cultureNames
         ' Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName)
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name)
         Console.WriteLine(value.ToString("C2"))
         Console.WriteLine()
      Next                  
   End Sub
End Module
' The example displays the following output:
'       The current culture is en-US
'       $1,043.17
'       
'       The current culture is fr-FR
'       1 043,17 €
'       
'       The current culture is es-MX
'       $1,043.17
'       
'       The current culture is de-DE
'       1.043,17 €
```

<span data-ttu-id="d76fd-333">Отформатировать числовое значение для определенных языка и региональных параметров также можно путем вызова перегрузки метода `ToString`, которая имеет параметр *provider*, и передачи ей одного из следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="d76fd-333">You can also format a numeric value for a specific culture by calling a `ToString` overload that has a *provider* parameter and passing it either of the following:</span></span> 

* <span data-ttu-id="d76fd-334">Объекта [CultureInfo](xref:System.Globalization.CultureInfo), представляющего язык и региональные параметры, соглашения о форматировании которых требуется использовать.</span><span class="sxs-lookup"><span data-stu-id="d76fd-334">A [CultureInfo](xref:System.Globalization.CultureInfo) object that represents the culture whose formatting conventions are to be used.</span></span> <span data-ttu-id="d76fd-335">Его метод [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) возвращает значение свойства [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat), которое является объектом [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), предоставляющим сведения о форматировании в соответствии с языком и региональными параметрами для числовых значений.</span><span class="sxs-lookup"><span data-stu-id="d76fd-335">Its [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) method returns the value of the [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat) property, which is the [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object that provides culture-specific formatting information for numeric values.</span></span>

* <span data-ttu-id="d76fd-336">Объекта [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), определяющего соглашения о форматировании для используемых языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d76fd-336">A [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object that defines the culture-specific formatting conventions to be used.</span></span> <span data-ttu-id="d76fd-337">Метод [GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) этого класса возвращает экземпляр его самого.</span><span class="sxs-lookup"><span data-stu-id="d76fd-337">Its [GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) method returns an instance of itself.</span></span>

<span data-ttu-id="d76fd-338">В следующем примере объекты [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), представляющие "Английский (США)" и "Английский (Соединенное Королевство)" язык и региональные параметры, а также "Французский" и "Русский" нейтральные языки и региональные параметры, используются для форматирования числа с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="d76fd-338">The following example uses [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) objects that represent the English (United States) and English (Great Britain) cultures and the French and Russian neutral cultures to format a floating-point number.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {                                                                                                    
      Double value = 1043.62957;
      string[] cultureNames = { "en-US", "en-GB", "ru", "fr" };

      foreach (var name in cultureNames) {
         NumberFormatInfo nfi = CultureInfo.CreateSpecificCulture(name).NumberFormat;
         Console.WriteLine("{0,-6} {1}", name + ":", value.ToString("N3", nfi));
      }   
   }
}
// The example displays the following output:
//       en-US: 1,043.630
//       en-GB: 1,043.630
//       ru:    1 043,630
//       fr:    1 043,630
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim value As Double = 1043.62957
      Dim cultureNames() As String = { "en-US", "en-GB", "ru", "fr" }

      For Each name In cultureNames
         Dim nfi As NumberFormatInfo = CultureInfo.CreateSpecificCulture(name).NumberFormat
         Console.WriteLine("{0,-6} {1}", name + ":", value.ToString("N3", nfi))
      Next   
   End Sub
End Module
' The example displays the following output:
'       en-US: 1,043.630
'       en-GB: 1,043.630
'       ru:    1 043,630
'       fr:    1 043,630
```

### <a name="culture-sensitive-formatting-of-date-and-time-values"></a><span data-ttu-id="d76fd-339">Форматирование значений даты и времени, зависящее от языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="d76fd-339">Culture-sensitive formatting of date and time values</span></span>

<span data-ttu-id="d76fd-340">По умолчанию форматирование значений даты и времени зависит от языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d76fd-340">By default, the formatting of date and time values is culture-sensitive.</span></span> <span data-ttu-id="d76fd-341">Если не указать язык и региональные параметры при вызове метода форматирования, используются соглашения о форматировании текущего языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d76fd-341">If you do not specify a culture when you call a formatting method, the formatting conventions of the current thread culture are used.</span></span> <span data-ttu-id="d76fd-342">Это продемонстрировано в следующем примере, который изменяет текущие язык и региональные параметры четыре раза, а затем вызывает метод [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)).</span><span class="sxs-lookup"><span data-stu-id="d76fd-342">This is illustrated in the following example, which changes the current thread culture four times and then calls the [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)) method.</span></span> <span data-ttu-id="d76fd-343">В каждом случае результирующая строка отражает соглашения о форматировании текущих языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d76fd-343">In each case, the result string reflects the formatting conventions of the current culture.</span></span> <span data-ttu-id="d76fd-344">Это происходит потому, что методы [DateTime.ToString()](xref:System.DateTime.ToString), [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)), [DateTimeOffset.ToString()](xref:System.DateTimeOffset.ToString(System.String)) и [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) создают оболочки для вызовов методов [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) и [DateTimeOffset.ToString(String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)).</span><span class="sxs-lookup"><span data-stu-id="d76fd-344">This is because the [DateTime.ToString()](xref:System.DateTime.ToString), [DateTime.ToString(String)](xref:System.DateTime.ToString(System.String)), [DateTimeOffset.ToString()](xref:System.DateTimeOffset.ToString(System.String)), and [DateTimeOffset.ToString(String)](xref:System.DateTimeOffset.ToString(System.String)) methods wrap calls to the [DateTime.ToString(String, IFormatProvider)](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) and [DateTimeOffset.ToString(String, IFormatProvider)](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) methods.</span></span>

```csharp
using System;
using System.Globalization;
using System.Threading;

public class Example
{
   public static void Main()
   {
      string[] cultureNames = { "en-US", "fr-FR", "es-MX", "de-DE" };
      DateTime dateToFormat = new DateTime(2012, 5, 28, 11, 30, 0);

      foreach (var cultureName in cultureNames) {
         // Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName);
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name);
         Console.WriteLine(dateToFormat.ToString("F"));
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//       The current culture is en-US
//       Monday, May 28, 2012 11:30:00 AM
//       
//       The current culture is fr-FR
//       lundi 28 mai 2012 11:30:00
//       
//       The current culture is es-MX
//       lunes, 28 de mayo de 2012 11:30:00 a.m.
//       
//       The current culture is de-DE
//       Montag, 28. Mai 2012 11:30:00
```

```vb
Imports System.Globalization
Imports System.Threading 

Module Example
   Public Sub Main()
      Dim cultureNames() As String = { "en-US", "fr-FR", "es-MX", "de-DE" }
      Dim dateToFormat As Date = #5/28/2012 11:30AM#

      For Each cultureName In cultureNames
         ' Change the current thread culture.
         Thread.CurrentThread.CurrentCulture = CultureInfo.CreateSpecificCulture(cultureName)
         Console.WriteLine("The current culture is {0}", 
                           Thread.CurrentThread.CurrentCulture.Name)
         Console.WriteLine(dateToFormat.ToString("F"))
         Console.WriteLine()
      Next                  
   End Sub
End Module
' The example displays the following output:
'       The current culture is en-US
'       Monday, May 28, 2012 11:30:00 AM
'       
'       The current culture is fr-FR
'       lundi 28 mai 2012 11:30:00
'       
'       The current culture is es-MX
'       lunes, 28 de mayo de 2012 11:30:00 a.m.
'       
'       The current culture is de-DE
'       Montag, 28. Mai 2012 11:30:00
```

<span data-ttu-id="d76fd-345">Форматировать значения даты и времени для определенных языка и региональных параметров также можно путем вызова перегрузки методов [DateTime.ToString](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) или [DateTimeOffset.ToString](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)), которая имеет параметр provider, и передачи ей одного из следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="d76fd-345">You can also format a date and time value for a specific culture by calling a [DateTime.ToString](xref:System.DateTime.ToString(System.String,System.IFormatProvider)) or [DateTimeOffset.ToString](xref:System.DateTimeOffset.ToString(System.String,System.IFormatProvider)) overload that has a provider parameter and passing it either of the following:</span></span> 

* <span data-ttu-id="d76fd-346">Объекта [CultureInfo](xref:System.Globalization.CultureInfo), представляющего язык и региональные параметры, соглашения о форматировании которых требуется использовать.</span><span class="sxs-lookup"><span data-stu-id="d76fd-346">A [CultureInfo](xref:System.Globalization.CultureInfo) object that represents the culture whose formatting conventions are to be used.</span></span> <span data-ttu-id="d76fd-347">Его метод [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) возвращает значение свойства [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat), которое является объектом [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), предоставляющим сведения о форматировании в соответствии с языком и региональными параметрами для числовых значений.</span><span class="sxs-lookup"><span data-stu-id="d76fd-347">Its [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) method returns the value of the [CultureInfo.NumberFormat](xref:System.Globalization.CultureInfo.NumberFormat) property, which is the [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that provides culture-specific formatting information for numeric values.</span></span>

* <span data-ttu-id="d76fd-348">Объекта [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), определяющего соглашения о форматировании для используемых языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d76fd-348">A [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that defines the culture-specific formatting conventions to be used.</span></span> <span data-ttu-id="d76fd-349">Метод [GetFormat](xref:System.Globalization.DateTimeFormatInfo.GetFormat(System.Type)) этого класса возвращает экземпляр его самого.</span><span class="sxs-lookup"><span data-stu-id="d76fd-349">Its [GetFormat](xref:System.Globalization.DateTimeFormatInfo.GetFormat(System.Type)) method returns an instance of itself.</span></span>

<span data-ttu-id="d76fd-350">В следующем примере объекты [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo), представляющие "Английский (США)" и "Английский (Соединенное Королевство)" язык и региональные параметры, а также "Французский" и "Русский" нейтральные языки и региональные параметры, используются для форматирования даты.</span><span class="sxs-lookup"><span data-stu-id="d76fd-350">The following example uses [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) objects that represent the English (United States) and English (Great Britain) cultures and the French and Russian neutral cultures to format a date.</span></span> 

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {                                                                                                    
      DateTime dat1 = new DateTime(2012, 5, 28, 11, 30, 0);
      string[] cultureNames = { "en-US", "en-GB", "ru", "fr" };

      foreach (var name in cultureNames) {
         DateTimeFormatInfo dtfi = CultureInfo.CreateSpecificCulture(name).DateTimeFormat;
         Console.WriteLine("{0}: {1}", name, dat1.ToString(dtfi));
      }   
   }
}
// The example displays the following output:
//       en-US: 5/28/2012 11:30:00 AM
//       en-GB: 28/05/2012 11:30:00
//       ru: 28.05.2012 11:30:00
//       fr: 28/05/2012 11:30:00
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim dat1 As Date = #5/28/2012 11:30AM#
      Dim cultureNames() As String = { "en-US", "en-GB", "ru", "fr" }

      For Each name In cultureNames
         Dim dtfi As DateTimeFormatInfo = CultureInfo.CreateSpecificCulture(name).DateTimeFormat
         Console.WriteLine("{0}: {1}", name, dat1.ToString(dtfi))
      Next   
   End Sub
End Module
' The example displays the following output:
'       en-US: 5/28/2012 11:30:00 AM
'       en-GB: 28/05/2012 11:30:00
'       ru: 28.05.2012 11:30:00
'       fr: 28/05/2012 11:30:00
```

## <a name="the-iformattable-interface"></a><span data-ttu-id="d76fd-351">Интерфейс IFormattable</span><span class="sxs-lookup"><span data-stu-id="d76fd-351">The IFormattable interface</span></span>

<span data-ttu-id="d76fd-352">Обычно типы, в которых имеется перегрузка метода `ToString`, использующая строку формата и параметр [IFormatProvider](xref:System.IFormatProvider), также реализуют интерфейс [IFormattable](xref:System.IFormattable).</span><span class="sxs-lookup"><span data-stu-id="d76fd-352">Typically, types that overload the `ToString` method with a format string and an [IFormatProvider](xref:System.IFormatProvider) parameter also implement the [IFormattable](xref:System.IFormattable) interface.</span></span> <span data-ttu-id="d76fd-353">Единственный член этого интерфейса — метод [IFormattable.ToString(String, IFormatProvider)](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)), параметрами которого являются строка формата и поставщик форматирования.</span><span class="sxs-lookup"><span data-stu-id="d76fd-353">This interface has a single member, [IFormattable.ToString(String, IFormatProvider)](xref:System.IFormattable.ToString(System.String,System.IFormatProvider)), that includes both a format string and a format provider as parameters.</span></span>

<span data-ttu-id="d76fd-354">Реализация интерфейса [IFormattable](xref:System.IFormattable) в определяемых приложением классах позволяет получить два преимущества:</span><span class="sxs-lookup"><span data-stu-id="d76fd-354">Implementing the [IFormattable](xref:System.IFormattable) interface for your application-defined class offers two advantages:</span></span> 

* <span data-ttu-id="d76fd-355">Поддержка строковых преобразований с помощью класса [Convert](xref:System.Convert).</span><span class="sxs-lookup"><span data-stu-id="d76fd-355">Support for string conversion by the [Convert](xref:System.Convert) class.</span></span> <span data-ttu-id="d76fd-356">При вызове методов [Convert.ToString(Object)](xref:System.Convert.ToString(System.Object)) и [Convert.ToString(Object, IFormatProvider)](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) автоматически вызывается пользовательская реализация [IFormattable](xref:System.IFormattable).</span><span class="sxs-lookup"><span data-stu-id="d76fd-356">Calls to the [Convert.ToString(Object)](xref:System.Convert.ToString(System.Object)) and [Convert.ToString(Object, IFormatProvider)](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) methods call your [IFormattable](xref:System.IFormattable) implementation automatically.</span></span>

* <span data-ttu-id="d76fd-357">Поддержка составного форматирования.</span><span class="sxs-lookup"><span data-stu-id="d76fd-357">Support for composite formatting.</span></span> <span data-ttu-id="d76fd-358">Если для форматирования пользовательского типа используется элемент форматирования, включающий строку формата, то среда CLR автоматически вызывает пользовательскую реализацию [IFormattable](xref:System.IFormattable), передавая ей строку формата.</span><span class="sxs-lookup"><span data-stu-id="d76fd-358">If a format item that includes a format string is used to format your custom type, the Common Language Runtime automatically calls your [IFormattable](xref:System.IFormattable) implementation and passes it the format string.</span></span> <span data-ttu-id="d76fd-359">Дополнительные сведения о составном форматировании при помощи таких методов, как `String.Format` или `Console.WriteLine`, см. в разделе [Составное форматирование](#composite-formatting).</span><span class="sxs-lookup"><span data-stu-id="d76fd-359">For more information about composite formatting with methods such as `String.Format` or `Console.WriteLine`, see the [Composite formatting](#composite-formatting) section.</span></span>

<span data-ttu-id="d76fd-360">В следующем примере определяется класс `Temperature`, реализующий интерфейс [IFormattable](xref:System.IFormattable).</span><span class="sxs-lookup"><span data-stu-id="d76fd-360">The following example defines a `Temperature` class that implements the [IFormattable](xref:System.IFormattable) interface.</span></span> <span data-ttu-id="d76fd-361">Он поддерживает описатели формата "C" и "G", позволяющие отобразить значение температуры в градусах Цельсия, описатель формата "F", позволяющий отобразить значение температуры в градусах Фаренгейта, и описатель формата "K", позволяющий отобразить значение температуры в градусах Кельвина.</span><span class="sxs-lookup"><span data-stu-id="d76fd-361">It supports the "C" or "G" format specifiers to display the temperature in Celsius, the "F" format specifier to display the temperature in Fahrenheit, and the "K" format specifier to display the temperature in Kelvin.</span></span>

```csharp
using System;
using System.Globalization;

public class Temperature : IFormattable
{
   private decimal m_Temp;

   public Temperature(decimal temperature)
   {
      this.m_Temp = temperature;
   }

   public decimal Celsius
   {
      get { return this.m_Temp; }
   }

   public decimal Kelvin
   {
      get { return this.m_Temp + 273.15m; }   
   }

   public decimal Fahrenheit
   {
      get { return Math.Round((decimal) this.m_Temp * 9 / 5 + 32, 2); }
   }

   public override string ToString()
   {
      return this.ToString("G", null);
   }

   public string ToString(string format)
   {
      return this.ToString(format, null);
   }

   public string ToString(string format, IFormatProvider provider)  
   {
      // Handle null or empty arguments.
      if (String.IsNullOrEmpty(format)) format = "G";
      // Remove any white space and convert to uppercase.
      format = format.Trim().ToUpperInvariant();

      if (provider == null) provider = NumberFormatInfo.CurrentInfo;

      switch (format)
      {
         // Convert temperature to Fahrenheit and return string.
         case "F":
            return this.Fahrenheit.ToString("N2", provider) + "°F";
         // Convert temperature to Kelvin and return string.
         case "K":
            return this.Kelvin.ToString("N2", provider) + "K";
         // Return temperature in Celsius.
         case "C":
         case "G":
            return this.Celsius.ToString("N2", provider) + "°C";
         default:
            throw new FormatException(String.Format("The '{0}' format string is not supported.", format));
      }      
   }
}
```

```vb
Imports System.Globalization

Public Class Temperature : Implements IFormattable
   Private m_Temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.m_Temp = temperature
   End Sub

   Public ReadOnly Property Celsius() As Decimal
      Get
         Return Me.m_Temp
      End Get   
   End Property

   Public ReadOnly Property Kelvin() As Decimal
      Get
         Return Me.m_Temp + 273.15d   
      End Get
   End Property

   Public ReadOnly Property Fahrenheit() As Decimal
      Get
         Return Math.Round(CDec(Me.m_Temp * 9 / 5 + 32), 2)
      End Get      
   End Property

   Public Overrides Function ToString() As String
      Return Me.ToString("G", Nothing)
   End Function

   Public Overloads Function ToString(format As String) As String
      Return Me.ToString(format, Nothing)
   End Function

   Public Overloads Function ToString(format As String, provider As IFormatProvider) As String _  
      Implements IFormattable.ToString

      ' Handle null or empty arguments.
      If String.IsNullOrEmpty(format) Then format = "G"
      ' Remove any white space and convert to uppercase.
      format = format.Trim().ToUpperInvariant()

      If provider Is Nothing Then provider = NumberFormatInfo.CurrentInfo

      Select Case format
         ' Convert temperature to Fahrenheit and return string.
         Case "F"
            Return Me.Fahrenheit.ToString("N2", provider) & "°F"
         ' Convert temperature to Kelvin and return string.
         Case "K"
            Return Me.Kelvin.ToString("N2", provider) & "K"
         ' Return temperature in Celsius.
         Case "C", "G"
            Return Me.Celsius.ToString("N2", provider) & "°C"
         Case Else
            Throw New FormatException(String.Format("The '{0}' format string is not supported.", format))
      End Select      
   End Function
End Class
```

<span data-ttu-id="d76fd-362">В следующем примере создается объект `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="d76fd-362">The following example instantiates a `Temperature` object.</span></span> <span data-ttu-id="d76fd-363">Затем в нем вызывается метод [ToString](xref:System.Convert.ToString(System.Object,System.IFormatProvider)). Использование нескольких строк составного формата позволяет получить различные строковые представления объекта `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="d76fd-363">It then calls the [ToString](xref:System.Convert.ToString(System.Object,System.IFormatProvider)) method and uses several composite format strings to obtain different string representations of a `Temperature` object.</span></span> <span data-ttu-id="d76fd-364">В свою очередь каждый из этих вызовов метода вызывает реализацию [IFormattable](xref:System.IFormattable) класса `Temperature`.</span><span class="sxs-lookup"><span data-stu-id="d76fd-364">Each of these method calls, in turn, calls the [IFormattable](xref:System.IFormattable) implementation of the `Temperature` class.</span></span>

```csharp
public class Example
{
   public static void Main()
   {
      Temperature temp1 = new Temperature(22m);
      Console.WriteLine(Convert.ToString(temp1, new CultureInfo("ja-JP")));
      Console.WriteLine("Temperature: {0:K}", temp1);
      Console.WriteLine("Temperature: {0:F}", temp1);
      Console.WriteLine(String.Format(new CultureInfo("fr-FR"), "Temperature: {0:F}", temp1));
   }
}
// The example displays the following output:
//       22.00°C
//       Temperature: 295.15°K
//       Temperature: 71.60°F
//       Temperature: 71,60°F
```

```vb
Public Module Example
   Public Sub Main()
      Dim temp1 As New Temperature(22d)
      Console.WriteLine(Convert.ToString(temp1, New CultureInfo("ja-JP")))
      Console.WriteLine("Temperature: {0:K}", temp1)
      Console.WriteLine("Temperature: {0:F}", temp1)
      Console.WriteLine(String.Format(New CultureInfo("fr-FR"), "Temperature: {0:F}", temp1)) 
   End Sub
End Module
' The example displays the following output:
'       22.00°C
'       Temperature: 295.15°K
'       Temperature: 71.60°F
'       Temperature: 71,60°F
```

## <a name="composite-formatting"></a><span data-ttu-id="d76fd-365">Составное форматирование</span><span class="sxs-lookup"><span data-stu-id="d76fd-365">Composite formatting</span></span>

<span data-ttu-id="d76fd-366">Некоторые методы, например `String.Format` и `StringBuilder.AppendFormat`, поддерживают составное форматирование.</span><span class="sxs-lookup"><span data-stu-id="d76fd-366">Some methods, such as `String.Format` and `StringBuilder.AppendFormat`, support composite formatting.</span></span> <span data-ttu-id="d76fd-367">Строка составного формата — это некий шаблон, возвращающий единую строку, включающую строковое представление нулевого, единичного или другого числа объектов.</span><span class="sxs-lookup"><span data-stu-id="d76fd-367">A composite format string is a kind of template that returns a single string that incorporates the string representation of zero, one, or more objects.</span></span> <span data-ttu-id="d76fd-368">Каждый объект представляется в строке составного формата индексированным элементом форматирования.</span><span class="sxs-lookup"><span data-stu-id="d76fd-368">Each object is represented in the composite format string by an indexed format item.</span></span> <span data-ttu-id="d76fd-369">Индекс элемента форматирования соответствует положению представляющего его объекта в списке параметров метода.</span><span class="sxs-lookup"><span data-stu-id="d76fd-369">The index of the format item corresponds to the position of the object that it represents in the method's parameter list.</span></span> <span data-ttu-id="d76fd-370">Индексы отсчитываются от нуля.</span><span class="sxs-lookup"><span data-stu-id="d76fd-370">Indexes are zero-based.</span></span> <span data-ttu-id="d76fd-371">Например, в вызове метода `String.Format` первый элемент форматирования, `{0:D}`, замещается строковым представлением `thatDate`; второй элемент форматирования, `{1}`, замещается строковым представлением `item1`; а третий элемент форматирования, `{2:C2}`, замещается строковым представлением `item1.Value`.</span><span class="sxs-lookup"><span data-stu-id="d76fd-371">For example, in the following call to the `String.Format` method, the first format item, `{0:D}`, is replaced by the string representation of `thatDate`; the second format item, `{1}`, is replaced by the string representation of `item1`; and the third format item, `{2:C2}`, is replaced by the string representation of `item1.Value`.</span></span>

```csharp
result = String.Format("On {0:d}, the inventory of {1} was worth {2:C2}.", 
                       thatDate, item1, item1.Value);
Console.WriteLine(result);                            
// The example displays output like the following if run on a system
// whose current culture is en-US:
//       On 5/1/2009, the inventory of WidgetA was worth $107.44.
```

```vb
result = String.Format("On {0:d}, the inventory of {1} was worth {2:C2}.", _
                       thatDate, item1, item1.Value)
Console.WriteLine(result)                            
' The example displays output like the following if run on a system
' whose current culture is en-US:
'       On 5/1/2009, the inventory of WidgetA was worth $107.44.
```

<span data-ttu-id="d76fd-372">Помимо замены элементов форматирования строковыми представлениями соответствующего объекта, элементы форматирования также позволяют управлять перечисленными ниже аспектами.</span><span class="sxs-lookup"><span data-stu-id="d76fd-372">In addition to replacing a format item with the string representation of its corresponding object, format items also let you control the following:</span></span> 

* <span data-ttu-id="d76fd-373">Вы можете указать конкретный способ представления объекта в виде строки, если объект реализует интерфейс [IFormattable](xref:System.IFormattable) и поддерживает строки формата.</span><span class="sxs-lookup"><span data-stu-id="d76fd-373">The specific way in which an object is represented as a string, if the object implements the [IFormattable](xref:System.IFormattable) interface and supports format strings.</span></span> <span data-ttu-id="d76fd-374">Для этого после индекса элемента форматирования необходимо ввести ":" (двоеточие), а за ним — допустимую строку формата.</span><span class="sxs-lookup"><span data-stu-id="d76fd-374">You do this by following the format item's index with a : (colon) followed by a valid format string.</span></span> <span data-ttu-id="d76fd-375">В предыдущем примере для этого выполнялось форматирование значения даты с помощью строки формата "d" (шаблон короткого формата даты, например `{0:d}`) и форматирование числового значения с помощью строки формата "C2" (например, `{2:C2}` для представления числа в виде значения валюты с двумя цифрами дробной части).</span><span class="sxs-lookup"><span data-stu-id="d76fd-375">The previous example did this by formatting a date value with the "d" (short date pattern) format string (for example, `{0:d}`) and by formatting a numeric value with the "C2" format string (for example, `{2:C2}` to represent the number as a currency value with two fractional decimal digits).</span></span> 

* <span data-ttu-id="d76fd-376">Вы можете задать ширину поля, содержащего строковое представление объекта, и выравнивание строкового представления в этом поле.</span><span class="sxs-lookup"><span data-stu-id="d76fd-376">The width of the field that contains the object's string representation, and the alignment of the string representation in that field.</span></span> <span data-ttu-id="d76fd-377">Для этого после индекса элемента форматирования необходимо ввести "," (запятую), а за ней — значение ширины поля.</span><span class="sxs-lookup"><span data-stu-id="d76fd-377">You do this by following the format item's index with a , (comma) followed the field width.</span></span> <span data-ttu-id="d76fd-378">Строка выравнивается по правому краю поля, если ширина поля — положительное значение, и по левому краю, если ширина поля — отрицательное значение.</span><span class="sxs-lookup"><span data-stu-id="d76fd-378">The string is right-aligned in the field if the field width is a positive value, and it is left-aligned if the field width is a negative value.</span></span> <span data-ttu-id="d76fd-379">В примере ниже значения даты выравниваются по левому краю поля из 20 символов, а десятичные значения с одной цифрой дробной части — по правом краю поля из 11 символов.</span><span class="sxs-lookup"><span data-stu-id="d76fd-379">The following example left-aligns date values in a 20-character field, and it right-aligns decimal values with one fractional digit in an 11-character field.</span></span> 

```csharp
DateTime startDate = new DateTime(2015, 8, 28, 6, 0, 0);
decimal[] temps = { 73.452m, 68.98m, 72.6m, 69.24563m,
                   74.1m, 72.156m, 72.228m };
Console.WriteLine("{0,-20} {1,11}\n", "Date", "Temperature");
for (int ctr = 0; ctr < temps.Length; ctr++)
   Console.WriteLine("{0,-20:g} {1,11:N1}", startDate.AddDays(ctr), temps[ctr]);

// The example displays the following output:
//       Date                 Temperature
//
//       8/28/2015 6:00 AM           73.5
//       8/29/2015 6:00 AM           69.0
//       8/30/2015 6:00 AM           72.6
//       8/31/2015 6:00 AM           69.2
//       9/1/2015 6:00 AM            74.1
//       9/2/2015 6:00 AM            72.2
//       9/3/2015 6:00 AM            72.2
```

```vb
Dim startDate As New Date(2015, 8, 28, 6, 0, 0)
Dim temps() As Decimal = { 73.452, 68.98, 72.6, 69.24563,
                           74.1, 72.156, 72.228 }
Console.WriteLine("{0,-20} {1,11}", "Date", "Temperature")
Console.WriteLine()
For ctr As Integer = 0 To temps.Length - 1
   Console.WriteLine("{0,-20:g} {1,11:N1}", startDate.AddDays(ctr), temps(ctr))
Next
' The example displays the following output:
'       Date                 Temperature
'
'       8/28/2015 6:00 AM           73.5
'       8/29/2015 6:00 AM           69.0
'       8/30/2015 6:00 AM           72.6
'       8/31/2015 6:00 AM           69.2
'       9/1/2015 6:00 AM            74.1
'       9/2/2015 6:00 AM            72.2
'       9/3/2015 6:00 AM            72.2
```

<span data-ttu-id="d76fd-380">Обратите внимание на то, что если присутствует и компонент выравнивания строки, и компонент строки формата, первый из них предшествует последнему (например, `{0,-20:g}`).</span><span class="sxs-lookup"><span data-stu-id="d76fd-380">Note that, if both the alignment string component and the format string component are present, the former precedes the latter (for example, `{0,-20:g}`.</span></span> 

<span data-ttu-id="d76fd-381">Подробности о составном форматировании см. в разделе [Составное форматирование](composite-format.md).</span><span class="sxs-lookup"><span data-stu-id="d76fd-381">For more information about composite formatting, see [Composite formatting](composite-format.md).</span></span>

## <a name="custom-formatting-with-icustomformatter"></a><span data-ttu-id="d76fd-382">Настраиваемое форматирование с использованием интерфейса ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="d76fd-382">Custom formatting with ICustomFormatter</span></span>

<span data-ttu-id="d76fd-383">У двух методов составного форматирования [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object[])) и [StringBuilder.AppendFormat(IFormatProvider, String, Object[])](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) также имеется параметр, задающий поставщик форматирования, поддерживающий настраиваемое форматирование.</span><span class="sxs-lookup"><span data-stu-id="d76fd-383">Two composite formatting methods, [String.Format(IFormatProvider, String, Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object[])) and [StringBuilder.AppendFormat(IFormatProvider, String, Object[])](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)), include a format provider parameter that supports custom formatting.</span></span> <span data-ttu-id="d76fd-384">При вызове какого-либо из этих методов форматирования объект [Type](xref:System.Type), представляющий интерфейс [ICustomFormatter](xref:System.ICustomFormatter), передается методу `GetFormat` поставщика форматирования.</span><span class="sxs-lookup"><span data-stu-id="d76fd-384">When either of these formatting methods is called, it passes a [Type](xref:System.Type) object that represents an [ICustomFormatter](xref:System.ICustomFormatter) interface to the format provider’s `GetFormat` method.</span></span> <span data-ttu-id="d76fd-385">Метод `GetFormat` должен вернуть реализацию [ICustomFormatter](xref:System.ICustomFormatter), поддерживающую настраиваемое форматирование.</span><span class="sxs-lookup"><span data-stu-id="d76fd-385">The `GetFormat` method is then responsible for returning the [ICustomFormatter](xref:System.ICustomFormatter) implementation that provides custom formatting.</span></span>

<span data-ttu-id="d76fd-386">Единственный метод интерфейса [ICustomFormatter](xref:System.ICustomFormatter), который называется [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)), автоматически вызывается методом составного форматирования по одному разу для каждого элемента форматирования в строке составного формата.</span><span class="sxs-lookup"><span data-stu-id="d76fd-386">The [ICustomFormatter](xref:System.ICustomFormatter) interface has a single method, [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)), that is called automatically by a composite formatting method, once for each format item in a composite format string.</span></span> <span data-ttu-id="d76fd-387">У метода [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) есть три параметра: строка формата, представляющая аргумент *formatString* в элементе форматирования, сам форматируемый объект и объект [IFormatProvider](xref:System.IFormatProvider), предоставляющий услуги форматирования.</span><span class="sxs-lookup"><span data-stu-id="d76fd-387">The [Format(String, Object, IFormatProvider)](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) method has three parameters: a format string, which represents the *formatString* argument in a format item, an object to format, and an [IFormatProvider](xref:System.IFormatProvider) object that provides formatting services.</span></span> <span data-ttu-id="d76fd-388">Обычно класс, реализующий интерфейс [ICustomFormatter](xref:System.ICustomFormatter), также реализует интерфейс [IFormatProvider](xref:System.IFormatProvider), поэтому в таком случае последний параметр будет ссылкой на сам класс настраиваемого форматирования.</span><span class="sxs-lookup"><span data-stu-id="d76fd-388">Typically, the class that implements [ICustomFormatter](xref:System.ICustomFormatter) also implements [IFormatProvider](xref:System.IFormatProvider), so this last parameter is a reference to the custom formatting class itself.</span></span> <span data-ttu-id="d76fd-389">Метод возвращает настраиваемое строковое представление объекта, который нужно было отформатировать.</span><span class="sxs-lookup"><span data-stu-id="d76fd-389">The method returns a custom formatted string representation of the object to be formatted.</span></span> <span data-ttu-id="d76fd-390">Если методу не удается отформатировать объект, он должен вернуть пустую ссылку.</span><span class="sxs-lookup"><span data-stu-id="d76fd-390">If the method cannot format the object, it should return a null reference.</span></span>

<span data-ttu-id="d76fd-391">В следующем примере приведена реализация [ICustomFormatter](xref:System.ICustomFormatter) с именем `ByteByByteFormatter`, отображающая целочисленные значения в виде последовательности пар шестнадцатеричных цифр, разделенных пробелами.</span><span class="sxs-lookup"><span data-stu-id="d76fd-391">The following example provides an [ICustomFormatter](xref:System.ICustomFormatter) implementation named `ByteByByteFormatter` that displays integer values as a sequence of two-digit hexadecimal values followed by a space.</span></span>

```csharp
public class ByteByByteFormatter : IFormatProvider, ICustomFormatter
{
   public object GetFormat(Type formatType)
   { 
      if (formatType == typeof(ICustomFormatter))
         return this;
      else
         return null;
   }

   public string Format(string format, object arg, 
                          IFormatProvider formatProvider)
   {   
      if (! formatProvider.Equals(this)) return null;

      // Handle only hexadecimal format string.
      if (! format.StartsWith("X")) return null;

      byte[] bytes;
      string output = null;

      // Handle only integral types.
      if (arg is Byte) 
         bytes = BitConverter.GetBytes((Byte) arg);
      else if (arg is Int16)
         bytes = BitConverter.GetBytes((Int16) arg);
      else if (arg is Int32)
         bytes = BitConverter.GetBytes((Int32) arg);
      else if (arg is Int64)   
         bytes = BitConverter.GetBytes((Int64) arg);
      else if (arg is SByte)
         bytes = BitConverter.GetBytes((SByte) arg);
      else if (arg is UInt16)
         bytes = BitConverter.GetBytes((UInt16) arg);
      else if (arg is UInt32)
         bytes = BitConverter.GetBytes((UInt32) arg);
      else if (arg is UInt64)
         bytes = BitConverter.GetBytes((UInt64) arg);
      else
         return null;

      for (int ctr = bytes.Length - 1; ctr >= 0; ctr--)
         output += String.Format("{0:X2} ", bytes[ctr]);   

      return output.Trim();
   }
}
```

```vb
Public Class ByteByByteFormatter : Implements IFormatProvider, ICustomFormatter
   Public Function GetFormat(formatType As Type) As Object _
                   Implements IFormatProvider.GetFormat
      If formatType Is GetType(ICustomFormatter) Then
         Return Me
      Else
         Return Nothing
      End If
   End Function

   Public Function Format(fmt As String, arg As Object, 
                          formatProvider As IFormatProvider) As String _
                          Implements ICustomFormatter.Format

      If Not formatProvider.Equals(Me) Then Return Nothing

      ' Handle only hexadecimal format string.
      If Not fmt.StartsWith("X") Then 
            Return Nothing
      End If

      ' Handle only integral types.
      If Not typeof arg Is Byte AndAlso
         Not typeof arg Is Int16 AndAlso
         Not typeof arg Is Int32 AndAlso
         Not typeof arg Is Int64 AndAlso
         Not typeof arg Is SByte AndAlso
         Not typeof arg Is UInt16 AndAlso
         Not typeof arg Is UInt32 AndAlso
         Not typeof arg Is UInt64 Then _
            Return Nothing

      Dim bytes() As Byte = BitConverter.GetBytes(arg)
      Dim output As String = Nothing

      For ctr As Integer = bytes.Length - 1 To 0 Step -1
         output += String.Format("{0:X2} ", bytes(ctr))   
      Next

      Return output.Trim()
   End Function
End Class
```

<span data-ttu-id="d76fd-392">В следующем примере класс `ByteByByteFormatter` используется для форматирования целочисленных значений.</span><span class="sxs-lookup"><span data-stu-id="d76fd-392">The following example uses the `ByteByByteFormatter` class to format integer values.</span></span> <span data-ttu-id="d76fd-393">Обратите внимание, что метод [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) вызывается во втором вызове метода [String.Format(IFormatProvider, String, Object[])](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) несколько раз и что в третьем вызове метода используется поставщик [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) по умолчанию, поскольку метод `.ByteByByteFormatter.Format` не распознает строку формата "N0" и возвращает пустую ссылку.</span><span class="sxs-lookup"><span data-stu-id="d76fd-393">Note that the [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) method is called more than once in the second [String.Format(IFormatProvider, String, Object[])](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) method call, and that the default [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) provider is used in the third method call because the `.ByteByByteFormatter.Format` method does not recognize the "N0" format string and returns a null reference.</span></span>

```csharp
public class Example
{
   public static void Main()
   {
      long value = 3210662321; 
      byte value1 = 214;
      byte value2 = 19;

      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0:X}", value));
      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0:X} And {1:X} = {2:X} ({2:000})", 
                                      value1, value2, value1 & value2));                                
      Console.WriteLine(String.Format(new ByteByByteFormatter(), "{0,10:N0}", value));
   }
}
// The example displays the following output:
//       00 00 00 00 BF 5E D1 B1
//       00 D6 And 00 13 = 00 12 (018)
//       3,210,662,321
```

```vb
Public Module Example
   Public Sub Main()
      Dim value As Long = 3210662321 
      Dim value1 As Byte = 214
      Dim value2 As Byte = 19

      Console.WriteLine((String.Format(New ByteByByteFormatter(), "{0:X}", value)))
      Console.WriteLine((String.Format(New ByteByByteFormatter(), "{0:X} And {1:X} = {2:X} ({2:000})", 
                                      value1, value2, value1 And value2)))                                
      Console.WriteLine(String.Format(New ByteByByteFormatter(), "{0,10:N0}", value))
   End Sub
End Module
' The example displays the following output:
'       00 00 00 00 BF 5E D1 B1
'       00 D6 And 00 13 = 00 12 (018)
'       3,210,662,321
```

## <a name="related-topics"></a><span data-ttu-id="d76fd-394">См. также</span><span class="sxs-lookup"><span data-stu-id="d76fd-394">Related topics</span></span>

<span data-ttu-id="d76fd-395">Заголовок</span><span class="sxs-lookup"><span data-stu-id="d76fd-395">Title</span></span> | <span data-ttu-id="d76fd-396">Определение</span><span class="sxs-lookup"><span data-stu-id="d76fd-396">Definition</span></span>
----- | ----------
[<span data-ttu-id="d76fd-397">Строки стандартных числовых форматов</span><span class="sxs-lookup"><span data-stu-id="d76fd-397">Standard numeric format strings</span></span>](standard-numeric.md) | <span data-ttu-id="d76fd-398">Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления числовых значений.</span><span class="sxs-lookup"><span data-stu-id="d76fd-398">Describes standard format strings that create commonly used string representations of numeric values.</span></span> 
[<span data-ttu-id="d76fd-399">Строки настраиваемых числовых форматов</span><span class="sxs-lookup"><span data-stu-id="d76fd-399">Custom numeric format strings</span></span>](custom-numeric.md) | <span data-ttu-id="d76fd-400">Описание строк настраиваемого формата, позволяющих создавать прикладные строковые представления числовых значений.</span><span class="sxs-lookup"><span data-stu-id="d76fd-400">Describes custom format strings that create application-specific formats for numeric values.</span></span>
[<span data-ttu-id="d76fd-401">Строки стандартных форматов даты и времени</span><span class="sxs-lookup"><span data-stu-id="d76fd-401">Standard date and time format strings</span></span>](standard-datetime.md) |  <span data-ttu-id="d76fd-402">Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления значений [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="d76fd-402">Describes standard format strings that create commonly used string representations of [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="d76fd-403">Строки настраиваемых форматов даты и времени</span><span class="sxs-lookup"><span data-stu-id="d76fd-403">Custom date and time format strings</span></span>](custom-datetime.md) | <span data-ttu-id="d76fd-404">Описание строк настраиваемого формата, позволяющих создавать характерные для приложений форматы для значений [DateTime](xref:System.DateTime).</span><span class="sxs-lookup"><span data-stu-id="d76fd-404">Describes custom format strings that create application-specific formats for [DateTime](xref:System.DateTime) values.</span></span>
[<span data-ttu-id="d76fd-405">Строки стандартного формата TimeSpan</span><span class="sxs-lookup"><span data-stu-id="d76fd-405">Standard TimeSpan format strings</span></span>](standard-timespan.md) | <span data-ttu-id="d76fd-406">Описание строк стандартного формата, позволяющих создавать общеупотребимые строковые представления интервалов времени.</span><span class="sxs-lookup"><span data-stu-id="d76fd-406">Describes standard format strings that create commonly used string representations of time intervals.</span></span>
[<span data-ttu-id="d76fd-407">Строки настраиваемого формата TimeSpan</span><span class="sxs-lookup"><span data-stu-id="d76fd-407">Custom TimeSpan format strings</span></span>](custom-timespan.md) | <span data-ttu-id="d76fd-408">Описание строк настраиваемого формата, позволяющих создавать прикладные строковые представления интервалов времени.</span><span class="sxs-lookup"><span data-stu-id="d76fd-408">Describes custom format strings that create application-specific formats for time intervals.</span></span>
[<span data-ttu-id="d76fd-409">Строки форматов перечисления</span><span class="sxs-lookup"><span data-stu-id="d76fd-409">Enumeration format strings</span></span>](enumeration-format.md) | <span data-ttu-id="d76fd-410">Описание строк стандартного формата, используемых для создания строковых представлений значений перечислений.</span><span class="sxs-lookup"><span data-stu-id="d76fd-410">Describes standard format strings that are used to create string representations of enumeration values.</span></span>
[<span data-ttu-id="d76fd-411">Составное форматирование</span><span class="sxs-lookup"><span data-stu-id="d76fd-411">Composite formatting</span></span>](composite-format.md) | <span data-ttu-id="d76fd-412">Описание способа совмещения нескольких форматируемых значений в строке.</span><span class="sxs-lookup"><span data-stu-id="d76fd-412">Describes how to embed one or more formatted values in a string.</span></span> <span data-ttu-id="d76fd-413">Строка может быть последовательно отображена в консоли или выведена в поток.</span><span class="sxs-lookup"><span data-stu-id="d76fd-413">The string can subsequently be displayed on the console or written to a stream.</span></span>
[<span data-ttu-id="d76fd-414">Выполнение операций форматирования</span><span class="sxs-lookup"><span data-stu-id="d76fd-414">Performing formatting operations</span></span>](performing-formatting-operations.md) | <span data-ttu-id="d76fd-415">Перечень разделов, содержащих пошаговые инструкции для выполнения конкретных операций форматирования.</span><span class="sxs-lookup"><span data-stu-id="d76fd-415">Lists topics that provide step-by-step instructions for performing specific formatting operations.</span></span>
[<span data-ttu-id="d76fd-416">Анализ строк</span><span class="sxs-lookup"><span data-stu-id="d76fd-416">Parsing strings</span></span>](parsing-strings.md) | <span data-ttu-id="d76fd-417">Описание способов инициализации объектов со значениями, описанными строковыми представлениями этих объектов.</span><span class="sxs-lookup"><span data-stu-id="d76fd-417">Describes how to initialize objects to the values described by string representations of those objects.</span></span> <span data-ttu-id="d76fd-418">Разбор является операцией, обратной форматированию.</span><span class="sxs-lookup"><span data-stu-id="d76fd-418">Parsing is the inverse operation of formatting.</span></span>

## <a name="reference"></a><span data-ttu-id="d76fd-419">Ссылка</span><span class="sxs-lookup"><span data-stu-id="d76fd-419">Reference</span></span>

[<span data-ttu-id="d76fd-420">System.IFormattable</span><span class="sxs-lookup"><span data-stu-id="d76fd-420">System.IFormattable</span></span>](xref:System.IFormattable)

[<span data-ttu-id="d76fd-421">System.IFormatProvider</span><span class="sxs-lookup"><span data-stu-id="d76fd-421">System.IFormatProvider</span></span>](xref:System.IFormatProvider)

[<span data-ttu-id="d76fd-422">System.ICustomFormatter</span><span class="sxs-lookup"><span data-stu-id="d76fd-422">System.ICustomFormatter</span></span>](xref:System.ICustomFormatter)

