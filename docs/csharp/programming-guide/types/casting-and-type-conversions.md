---
title: "Приведение и преобразование типов (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- type conversion [C#]
- data type conversion [C#]
- numeric conversions [C#]
- conversions [C#], type
- casting [C#]
- converting types [C#]
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
caps.latest.revision: 52
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 20743c07c8e9c6b7ec24cf52a28bb9f451ba9df5
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="casting-and-type-conversions-c-programming-guide"></a><span data-ttu-id="5bcfa-102">Приведение и преобразование типов (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="5bcfa-102">Casting and Type Conversions (C# Programming Guide)</span></span>
<span data-ttu-id="5bcfa-103">Поскольку код C# является статически типизированным во время компиляции, после объявления переменной ее нельзя объявить повторно или использовать для хранения значений другого типа, если этот тип не преобразуется в тип переменной.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-103">Because C# is statically-typed at compile time, after a variable is declared, it cannot be declared again or used to store values of another type unless that type is convertible to the variable's type.</span></span> <span data-ttu-id="5bcfa-104">Например, отсутствует преобразование из целого числа в произвольную строку.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-104">For example, there is no conversion from an integer to any arbitrary string.</span></span> <span data-ttu-id="5bcfa-105">Поэтому после объявления `i` как целого числа нельзя назначить ей строку "Hello", как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-105">Therefore, after you declare `i` as an integer, you cannot assign the string "Hello" to it, as is shown in the following code.</span></span>  
  
```csharp  
int i;  
i = "Hello"; // Error: "Cannot implicitly convert type 'string' to 'int'"  
```  
  
 <span data-ttu-id="5bcfa-106">Тем не менее иногда может потребоваться скопировать значение в переменную или параметр метода другого типа.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-106">However, you might sometimes need to copy a value into a variable or method parameter of another type.</span></span> <span data-ttu-id="5bcfa-107">Например, может потребоваться передать целочисленную переменную в метод, параметр которого имеет тип `double`.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-107">For example, you might have an integer variable that you need to pass to a method whose parameter is typed as `double`.</span></span> <span data-ttu-id="5bcfa-108">Или может понадобиться присвоить переменную класса переменной типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-108">Or you might need to assign a class variable to a variable of an interface type.</span></span> <span data-ttu-id="5bcfa-109">Такого рода операции называются *преобразованиями типа*.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-109">These kinds of operations are called *type conversions*.</span></span> <span data-ttu-id="5bcfa-110">В C# можно выполнять следующие виды преобразований.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-110">In C#, you can perform the following kinds of conversions:</span></span>  
  
-   <span data-ttu-id="5bcfa-111">**Неявные преобразования**: никакой специальный синтаксис не требуется, поскольку преобразование является строго типизированным и данные не будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-111">**Implicit conversions**: No special syntax is required because the conversion is type safe and no data will be lost.</span></span> <span data-ttu-id="5bcfa-112">Примеры включают преобразования из меньших в большие целочисленные типы и преобразования из производных классов в базовые классы.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-112">Examples include conversions from smaller to larger integral types, and conversions from derived classes to base classes.</span></span>  
  
-   <span data-ttu-id="5bcfa-113">**Явные преобразования (приведения)**: явные преобразования требуют оператора приведения.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-113">**Explicit conversions (casts)**: Explicit conversions require a cast operator.</span></span> <span data-ttu-id="5bcfa-114">Приведение требуется, если в ходе преобразования данные могут быть утрачены или преобразование может завершиться сбоем по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-114">Casting is required when information might be lost in the conversion, or when the conversion might not succeed for other reasons.</span></span>  <span data-ttu-id="5bcfa-115">Типичными примерами являются числовое преобразование в тип с меньшей точностью или меньшим диапазоном и преобразование экземпляра базового класса в производный класс.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-115">Typical examples include numeric conversion to a type that has less precision or a smaller range, and conversion of a base-class instance to a derived class.</span></span>  
  
-   <span data-ttu-id="5bcfa-116">**Заданные пользователем преобразования**: пользовательские преобразования выполняются специальными методами, которые можно определить для включения явных и неявных преобразований между пользовательскими типами, не имеющими отношения "базовый класс-производный класс".</span><span class="sxs-lookup"><span data-stu-id="5bcfa-116">**User-defined conversions**: User-defined conversions are performed by special methods that you can define to enable explicit and implicit conversions between custom types that do not have a base class–derived class relationship.</span></span> <span data-ttu-id="5bcfa-117">Дополнительные сведения см. в разделе [Операторы преобразования](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="5bcfa-117">For more information, see [Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md).</span></span>  
  
-   <span data-ttu-id="5bcfa-118">**Преобразования с использованием вспомогательных классов**. Чтобы выполнить преобразование между несовместимыми типами, например целыми числами и объектами <xref:System.DateTime?displayProperty=fullName> или шестнадцатеричными строками и массивами байтов, можно использовать классы <xref:System.BitConverter?displayProperty=fullName> и <xref:System.Convert?displayProperty=fullName>, а также методы `Parse` встроенных числовых типов, такие как <xref:System.Int32.Parse%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-118">**Conversions with helper classes**: To convert between non-compatible types, such as integers and <xref:System.DateTime?displayProperty=fullName> objects, or hexadecimal strings and byte arrays, you can use the <xref:System.BitConverter?displayProperty=fullName> class, the <xref:System.Convert?displayProperty=fullName> class, and the `Parse` methods of the built-in numeric types, such as <xref:System.Int32.Parse%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="5bcfa-119">Дополнительные сведения см. в разделе [Практическое руководство. Преобразование массива байтов в значение типа int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Практическое руководство. Преобразование строки в число](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) и [Практическое руководство. Преобразование из шестнадцатеричных строк в числовые типы](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="5bcfa-119">For more information, see [How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), and [How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="5bcfa-120">Неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="5bcfa-120">Implicit Conversions</span></span>  
 <span data-ttu-id="5bcfa-121">Для встроенных числовых типов неявное преобразование можно выполнить, если сохраняемое значение может уместиться в переменной без усечения или округления.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-121">For built-in numeric types, an implicit conversion can be made when the value to be stored can fit into the variable without being truncated or rounded off.</span></span> <span data-ttu-id="5bcfa-122">Например, переменная типа [long](../../../csharp/language-reference/keywords/long.md) (8-байтное целое число) может хранить любое значение, которое может хранить переменная [int](../../../csharp/language-reference/keywords/int.md) (4 байта в 32-разрядных системах).</span><span class="sxs-lookup"><span data-stu-id="5bcfa-122">For example, a variable of type [long](../../../csharp/language-reference/keywords/long.md) (8 byte integer) can store any value that an [int](../../../csharp/language-reference/keywords/int.md) (4 bytes on a 32-bit computer) can store.</span></span> <span data-ttu-id="5bcfa-123">В следующем примере компилятор неявно преобразует значение справа в тип `long` перед назначением его `bigNum`.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-123">In the following example, the compiler implicitly converts the value on the right to a type `long` before assigning it to `bigNum`.</span></span>  
  
 <span data-ttu-id="5bcfa-124">[!code-cs[csProgGuideTypes#34](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="5bcfa-124">[!code-cs[csProgGuideTypes#34](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_1.cs)]</span></span>  
  
 <span data-ttu-id="5bcfa-125">Полный список всех неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="5bcfa-125">For a complete list of all implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="5bcfa-126">Для ссылочных типов неявное преобразование всегда предусмотрено из класса в любой из его прямых или косвенных базовых классов или интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-126">For reference types, an implicit conversion always exists from a class to any one of its direct or indirect base classes or interfaces.</span></span> <span data-ttu-id="5bcfa-127">Никакой специальный синтаксис не требуется, поскольку производный класс всегда содержит все члены базового класса.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-127">No special syntax is necessary because a derived class always contains all the members of a base class.</span></span>  
  
```  
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## <a name="explicit-conversions"></a><span data-ttu-id="5bcfa-128">Явные преобразования</span><span class="sxs-lookup"><span data-stu-id="5bcfa-128">Explicit Conversions</span></span>  
 <span data-ttu-id="5bcfa-129">Тем не менее если преобразование нельзя выполнить без риска потери данных, компилятор требует выполнения явного преобразования, которое называется *приведением*.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-129">However, if a conversion cannot be made without a risk of losing information, the compiler requires that you perform an explicit conversion, which is called a *cast*.</span></span> <span data-ttu-id="5bcfa-130">Приведение — это способ явно указать компилятору, что необходимо выполнить преобразование и что вам известно, что может произойти потеря данных.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-130">A cast is a way of explicitly informing the compiler that you intend to make the conversion and that you are aware that data loss might occur.</span></span> <span data-ttu-id="5bcfa-131">Чтобы выполнить приведение, укажите тип, в который производится приведение, в круглых скобках перед преобразуемым значением или переменной.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-131">To perform a cast, specify the type that you are casting to in parentheses in front of the value or variable to be converted.</span></span> <span data-ttu-id="5bcfa-132">В следующей программе выполняется приведение типа [double](../../../csharp/language-reference/keywords/double.md) в [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="5bcfa-132">The following program casts a [double](../../../csharp/language-reference/keywords/double.md) to an [int](../../../csharp/language-reference/keywords/int.md).</span></span> <span data-ttu-id="5bcfa-133">Программа не будет компилироваться без приведения.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-133">The program will not compile without the cast.</span></span>  
  
 <span data-ttu-id="5bcfa-134">[!code-cs[csProgGuideTypes#2](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="5bcfa-134">[!code-cs[csProgGuideTypes#2](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_2.cs)]</span></span>  
  
 <span data-ttu-id="5bcfa-135">Список разрешенных явных числовых преобразований см. в разделе [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="5bcfa-135">For a list of the explicit numeric conversions that are allowed, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="5bcfa-136">Для ссылочных типов явное приведение является обязательным, если необходимо преобразовать базовый тип в производный тип:</span><span class="sxs-lookup"><span data-stu-id="5bcfa-136">For reference types, an explicit cast is required if you need to convert from a base type to a derived type:</span></span>  
  
```csharp  
// Create a new derived type.  
Giraffe g = new Giraffe();  
  
// Implicit conversion to base type is safe.  
Animal a = g;  
  
// Explicit conversion is required to cast back  
// to derived type. Note: This will compile but will  
// throw an exception at run time if the right-side  
// object is not in fact a Giraffe.  
Giraffe g2 = (Giraffe) a;  
```  
  
 <span data-ttu-id="5bcfa-137">Операция приведения между ссылочными типами не меняет тип времени выполнения базового объекта; изменяется только тип значения, который используется в качестве ссылки на этот объект.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-137">A cast operation between reference types does not change the run-time type of the underlying object; it only changes the type of the value that is being used as a reference to that object.</span></span> <span data-ttu-id="5bcfa-138">Дополнительные сведения см. в разделе [Полиморфизм](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).</span><span class="sxs-lookup"><span data-stu-id="5bcfa-138">For more information, see [Polymorphism](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).</span></span>  
  
## <a name="type-conversion-exceptions-at-run-time"></a><span data-ttu-id="5bcfa-139">Исключения преобразования типов во время выполнения</span><span class="sxs-lookup"><span data-stu-id="5bcfa-139">Type Conversion Exceptions at Run Time</span></span>  
 <span data-ttu-id="5bcfa-140">В некоторых преобразованиях ссылочных типов компилятор не может определить, будет ли приведение допустимым.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-140">In some reference type conversions, the compiler cannot determine whether a cast will be valid.</span></span> <span data-ttu-id="5bcfa-141">Есть вероятность, что правильно скомпилированная операция приведения завершится сбоем во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-141">It is possible for a cast operation that compiles correctly to fail at run time.</span></span> <span data-ttu-id="5bcfa-142">Как показано в следующем примере, приведение типа, завершившееся сбоем во время выполнения, вызывает исключение <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-142">As shown in the following example, a type cast that fails at run time will cause an <xref:System.InvalidCastException> to be thrown.</span></span>  
  
 <span data-ttu-id="5bcfa-143">[!code-cs[csProgGuideTypes#41](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="5bcfa-143">[!code-cs[csProgGuideTypes#41](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/casting-and-type-conversions_3.cs)]</span></span>  
  
 <span data-ttu-id="5bcfa-144">C# предоставляет операторы [is](../../../csharp/language-reference/keywords/is.md) и [as](../../../csharp/language-reference/keywords/as.md), чтобы можно было проверить совместимость перед фактическим выполнением приведения.</span><span class="sxs-lookup"><span data-stu-id="5bcfa-144">C# provides the [is](../../../csharp/language-reference/keywords/is.md) and [as](../../../csharp/language-reference/keywords/as.md) operators to enable you to test for compatibility before actually performing a cast.</span></span> <span data-ttu-id="5bcfa-145">Дополнительные сведения см. в разделе [Практическое руководство. Безопасное приведение с помощью операторов as и is](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md).</span><span class="sxs-lookup"><span data-stu-id="5bcfa-145">For more information, see [How to: Safely Cast by Using as and is Operators](../../../csharp/programming-guide/types/how-to-safely-cast-by-using-as-and-is-operators.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5bcfa-146">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="5bcfa-146">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a><span data-ttu-id="5bcfa-147">См. также</span><span class="sxs-lookup"><span data-stu-id="5bcfa-147">See Also</span></span>  
 <span data-ttu-id="5bcfa-148">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="5bcfa-148">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="5bcfa-149">[Типы](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="5bcfa-149">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="5bcfa-150">[Оператор ()](../../../csharp/language-reference/operators/invocation-operator.md) </span><span class="sxs-lookup"><span data-stu-id="5bcfa-150">[() Operator](../../../csharp/language-reference/operators/invocation-operator.md) </span></span>  
 <span data-ttu-id="5bcfa-151">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span><span class="sxs-lookup"><span data-stu-id="5bcfa-151">[explicit](../../../csharp/language-reference/keywords/explicit.md) </span></span>  
 <span data-ttu-id="5bcfa-152">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span><span class="sxs-lookup"><span data-stu-id="5bcfa-152">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span></span>  
 <span data-ttu-id="5bcfa-153">[Операторы преобразования](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md) </span><span class="sxs-lookup"><span data-stu-id="5bcfa-153">[Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md) </span></span>  
 <span data-ttu-id="5bcfa-154">[Обобщенное преобразование типов](http://msdn.microsoft.com/library/49253ae6-7657-4810-82ab-1176a6feeada) </span><span class="sxs-lookup"><span data-stu-id="5bcfa-154">[Generalized Type Conversion](http://msdn.microsoft.com/library/49253ae6-7657-4810-82ab-1176a6feeada) </span></span>  
 <span data-ttu-id="5bcfa-155">[Преобразование экспортированного типа](http://msdn.microsoft.com/en-us/1dfe55f4-07a2-4b61-aabf-a8cf65783a6b) </span><span class="sxs-lookup"><span data-stu-id="5bcfa-155">[Exported Type Conversion](http://msdn.microsoft.com/en-us/1dfe55f4-07a2-4b61-aabf-a8cf65783a6b) </span></span>  
 [<span data-ttu-id="5bcfa-156">Практическое руководство. Преобразование строки в число</span><span class="sxs-lookup"><span data-stu-id="5bcfa-156">How to: Convert a String to a Number</span></span>](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)

