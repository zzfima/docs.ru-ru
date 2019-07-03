---
title: Руководство по программированию на C#. Приведение и преобразование типов
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- type conversion [C#]
- data type conversion [C#]
- numeric conversions [C#]
- conversions [C#], type
- casting [C#]
- converting types [C#]
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
ms.openlocfilehash: cd989b47c87ef32371b45650d531bd8cbeb85032
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306956"
---
# <a name="casting-and-type-conversions-c-programming-guide"></a><span data-ttu-id="0f81c-102">Руководство по программированию на C#. Приведение и преобразование типов</span><span class="sxs-lookup"><span data-stu-id="0f81c-102">Casting and type conversions (C# Programming Guide)</span></span>

<span data-ttu-id="0f81c-103">Поскольку код C# является статически типизированным во время компиляции, после объявления переменной ее нельзя объявить повторно или назначить ей значения другого типа, если этот тип невозможно неявно преобразовать в тип переменной.</span><span class="sxs-lookup"><span data-stu-id="0f81c-103">Because C# is statically-typed at compile time, after a variable is declared, it cannot be declared again or assigned a value of another type unless that type is implicitly convertible to the variable's type.</span></span> <span data-ttu-id="0f81c-104">Например, `string` невозможно неявно преобразовать в `int`.</span><span class="sxs-lookup"><span data-stu-id="0f81c-104">For example, the `string` cannot be implicitly converted to `int`.</span></span> <span data-ttu-id="0f81c-105">Поэтому после объявления `i` как `int` нельзя назначить ей строку "Hello", как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="0f81c-105">Therefore, after you declare `i` as an `int`, you cannot assign the string "Hello" to it, as the following code shows:</span></span>
  
```csharp  
int i;  
i = "Hello"; // error CS0029: Cannot implicitly convert type 'string' to 'int'
```  
  
 <span data-ttu-id="0f81c-106">Тем не менее иногда может потребоваться скопировать значение в переменную или параметр метода другого типа.</span><span class="sxs-lookup"><span data-stu-id="0f81c-106">However, you might sometimes need to copy a value into a variable or method parameter of another type.</span></span> <span data-ttu-id="0f81c-107">Например, может потребоваться передать целочисленную переменную в метод, параметр которого имеет тип `double`.</span><span class="sxs-lookup"><span data-stu-id="0f81c-107">For example, you might have an integer variable that you need to pass to a method whose parameter is typed as `double`.</span></span> <span data-ttu-id="0f81c-108">Или может понадобиться присвоить переменную класса переменной типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0f81c-108">Or you might need to assign a class variable to a variable of an interface type.</span></span> <span data-ttu-id="0f81c-109">Такого рода операции называются *преобразованиями типа*.</span><span class="sxs-lookup"><span data-stu-id="0f81c-109">These kinds of operations are called *type conversions*.</span></span> <span data-ttu-id="0f81c-110">В C# можно выполнять следующие виды преобразований.</span><span class="sxs-lookup"><span data-stu-id="0f81c-110">In C#, you can perform the following kinds of conversions:</span></span>  
  
- <span data-ttu-id="0f81c-111">**Неявные преобразования**. Специальный синтаксис не требуется, так как преобразование является строго типизированным и данные не будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="0f81c-111">**Implicit conversions**: No special syntax is required because the conversion is type safe and no data will be lost.</span></span> <span data-ttu-id="0f81c-112">Примеры включают преобразования из меньших в большие целочисленные типы и преобразования из производных классов в базовые классы.</span><span class="sxs-lookup"><span data-stu-id="0f81c-112">Examples include conversions from smaller to larger integral types, and conversions from derived classes to base classes.</span></span>  
  
- <span data-ttu-id="0f81c-113">**Явные преобразования (приведения)** . Для явных преобразований требуется оператор приведения.</span><span class="sxs-lookup"><span data-stu-id="0f81c-113">**Explicit conversions (casts)**: Explicit conversions require a cast operator.</span></span> <span data-ttu-id="0f81c-114">Приведение требуется, если в ходе преобразования данные могут быть утрачены или преобразование может завершиться сбоем по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="0f81c-114">Casting is required when information might be lost in the conversion, or when the conversion might not succeed for other reasons.</span></span>  <span data-ttu-id="0f81c-115">Типичными примерами являются числовое преобразование в тип с меньшей точностью или меньшим диапазоном и преобразование экземпляра базового класса в производный класс.</span><span class="sxs-lookup"><span data-stu-id="0f81c-115">Typical examples include numeric conversion to a type that has less precision or a smaller range, and conversion of a base-class instance to a derived class.</span></span>  
  
- <span data-ttu-id="0f81c-116">**Пользовательские преобразования**. Такие преобразования выполняются специальными методами, которые можно определить для включения явных и неявных преобразований между пользовательскими типами без связи "базовый класс — производный класс".</span><span class="sxs-lookup"><span data-stu-id="0f81c-116">**User-defined conversions**: User-defined conversions are performed by special methods that you can define to enable explicit and implicit conversions between custom types that do not have a base class–derived class relationship.</span></span> <span data-ttu-id="0f81c-117">Дополнительные сведения см. в разделе [Операторы преобразования](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="0f81c-117">For more information, see [Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md).</span></span>  
  
- <span data-ttu-id="0f81c-118">**Преобразования с использованием вспомогательных классов**. Чтобы выполнить преобразование между несовместимыми типами, например целыми числами и объектами <xref:System.DateTime?displayProperty=nameWithType> или шестнадцатеричными строками и массивами байтов, можно использовать классы <xref:System.BitConverter?displayProperty=nameWithType> и <xref:System.Convert?displayProperty=nameWithType>, а также методы `Parse` встроенных числовых типов, такие как <xref:System.Int32.Parse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0f81c-118">**Conversions with helper classes**: To convert between non-compatible types, such as integers and <xref:System.DateTime?displayProperty=nameWithType> objects, or hexadecimal strings and byte arrays, you can use the <xref:System.BitConverter?displayProperty=nameWithType> class, the <xref:System.Convert?displayProperty=nameWithType> class, and the `Parse` methods of the built-in numeric types, such as <xref:System.Int32.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0f81c-119">Дополнительные сведения см. в разделе [Практическое руководство. преобразованию массива байтов в значение типа int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [ преобразованию строки в число](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) и [ преобразованию из шестнадцатеричных строк в числовые типы](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="0f81c-119">For more information, see [How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), and [How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).</span></span>  
  
## <a name="implicit-conversions"></a><span data-ttu-id="0f81c-120">Неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="0f81c-120">Implicit conversions</span></span>

 <span data-ttu-id="0f81c-121">Для встроенных числовых типов неявное преобразование можно выполнить, если сохраняемое значение может уместиться в переменной без усечения или округления.</span><span class="sxs-lookup"><span data-stu-id="0f81c-121">For built-in numeric types, an implicit conversion can be made when the value to be stored can fit into the variable without being truncated or rounded off.</span></span> <span data-ttu-id="0f81c-122">Например, переменная типа [long](../../../csharp/language-reference/keywords/long.md) (64-разрядное целое число) может хранить любое значение, которое может хранить переменная [int](../../../csharp/language-reference/keywords/int.md) (32-разрядное целое число).</span><span class="sxs-lookup"><span data-stu-id="0f81c-122">For example, a variable of type [long](../../../csharp/language-reference/keywords/long.md) (64-bit integer) can store any value that an [int](../../../csharp/language-reference/keywords/int.md) (32-bit integer) can store.</span></span> <span data-ttu-id="0f81c-123">В следующем примере компилятор неявно преобразует значение `num` справа в тип `long` перед назначением `bigNum`.</span><span class="sxs-lookup"><span data-stu-id="0f81c-123">In the following example, the compiler implicitly converts the value of `num` on the right to a type `long` before assigning it to `bigNum`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#34)]  
  
 <span data-ttu-id="0f81c-124">Полный список всех неявных числовых преобразований см. в разделе [Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="0f81c-124">For a complete list of all implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="0f81c-125">Для ссылочных типов неявное преобразование всегда предусмотрено из класса в любой из его прямых или косвенных базовых классов или интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="0f81c-125">For reference types, an implicit conversion always exists from a class to any one of its direct or indirect base classes or interfaces.</span></span> <span data-ttu-id="0f81c-126">Никакой специальный синтаксис не требуется, поскольку производный класс всегда содержит все члены базового класса.</span><span class="sxs-lookup"><span data-stu-id="0f81c-126">No special syntax is necessary because a derived class always contains all the members of a base class.</span></span>  
  
```  
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## <a name="explicit-conversions"></a><span data-ttu-id="0f81c-127">Явные преобразования</span><span class="sxs-lookup"><span data-stu-id="0f81c-127">Explicit conversions</span></span>

 <span data-ttu-id="0f81c-128">Тем не менее если преобразование нельзя выполнить без риска потери данных, компилятор требует выполнения явного преобразования, которое называется *приведением*.</span><span class="sxs-lookup"><span data-stu-id="0f81c-128">However, if a conversion cannot be made without a risk of losing information, the compiler requires that you perform an explicit conversion, which is called a *cast*.</span></span> <span data-ttu-id="0f81c-129">Приведение — это способ явно указать компилятору, что необходимо выполнить преобразование и что вам известно, что может произойти потеря данных.</span><span class="sxs-lookup"><span data-stu-id="0f81c-129">A cast is a way of explicitly informing the compiler that you intend to make the conversion and that you are aware that data loss might occur.</span></span> <span data-ttu-id="0f81c-130">Чтобы выполнить приведение, укажите тип, в который производится приведение, в круглых скобках перед преобразуемым значением или переменной.</span><span class="sxs-lookup"><span data-stu-id="0f81c-130">To perform a cast, specify the type that you are casting to in parentheses in front of the value or variable to be converted.</span></span> <span data-ttu-id="0f81c-131">В следующей программе выполняется приведение типа [double](../../../csharp/language-reference/keywords/double.md) в [int](../../../csharp/language-reference/keywords/int.md). Программа не будет компилироваться без приведения.</span><span class="sxs-lookup"><span data-stu-id="0f81c-131">The following program casts a [double](../../../csharp/language-reference/keywords/double.md) to an [int](../../../csharp/language-reference/keywords/int.md). The program will not compile without the cast.</span></span>  
  
 [!code-csharp[csProgGuideTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#2)]  
  
 <span data-ttu-id="0f81c-132">Список разрешенных явных числовых преобразований см. в разделе [Таблица явных числовых преобразований](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="0f81c-132">For a list of the explicit numeric conversions that are allowed, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="0f81c-133">Для ссылочных типов явное приведение является обязательным, если необходимо преобразовать базовый тип в производный тип:</span><span class="sxs-lookup"><span data-stu-id="0f81c-133">For reference types, an explicit cast is required if you need to convert from a base type to a derived type:</span></span>  
  
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
  
 <span data-ttu-id="0f81c-134">Операция приведения между ссылочными типами не меняет тип времени выполнения базового объекта; изменяется только тип значения, который используется в качестве ссылки на этот объект.</span><span class="sxs-lookup"><span data-stu-id="0f81c-134">A cast operation between reference types does not change the run-time type of the underlying object; it only changes the type of the value that is being used as a reference to that object.</span></span> <span data-ttu-id="0f81c-135">Дополнительные сведения см. в разделе [Полиморфизм](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).</span><span class="sxs-lookup"><span data-stu-id="0f81c-135">For more information, see [Polymorphism](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).</span></span>  
  
## <a name="type-conversion-exceptions-at-run-time"></a><span data-ttu-id="0f81c-136">Исключения преобразования типов во время выполнения</span><span class="sxs-lookup"><span data-stu-id="0f81c-136">Type conversion exceptions at run time</span></span>

 <span data-ttu-id="0f81c-137">В некоторых преобразованиях ссылочных типов компилятор не может определить, будет ли приведение допустимым.</span><span class="sxs-lookup"><span data-stu-id="0f81c-137">In some reference type conversions, the compiler cannot determine whether a cast will be valid.</span></span> <span data-ttu-id="0f81c-138">Есть вероятность, что правильно скомпилированная операция приведения завершится сбоем во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="0f81c-138">It is possible for a cast operation that compiles correctly to fail at run time.</span></span> <span data-ttu-id="0f81c-139">Как показано в следующем примере, приведение типа, завершившееся сбоем во время выполнения, вызывает исключение <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="0f81c-139">As shown in the following example, a type cast that fails at run time will cause an <xref:System.InvalidCastException> to be thrown.</span></span>  
  
 [!code-csharp[csProgGuideTypes#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#41)]  
  
 <span data-ttu-id="0f81c-140">C# предоставляет оператор [is](../../language-reference/operators/type-testing-and-conversion-operators.md#is-operator), чтобы можно было проверить совместимость перед фактическим выполнением приведения.</span><span class="sxs-lookup"><span data-stu-id="0f81c-140">C# provides the [is](../../language-reference/operators/type-testing-and-conversion-operators.md#is-operator) operator to enable you to test for compatibility before actually performing a cast.</span></span> <span data-ttu-id="0f81c-141">Дополнительные сведения см. в статье [Практическое руководство. Безопасное приведение с помощью сопоставления шаблонов и операторы is и as](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md).</span><span class="sxs-lookup"><span data-stu-id="0f81c-141">For more information, see [How to: safely cast using pattern matching and the as and is operators](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0f81c-142">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0f81c-142">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a><span data-ttu-id="0f81c-143">См. также</span><span class="sxs-lookup"><span data-stu-id="0f81c-143">See also</span></span>

- [<span data-ttu-id="0f81c-144">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0f81c-144">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="0f81c-145">Типы</span><span class="sxs-lookup"><span data-stu-id="0f81c-145">Types</span></span>](../../../csharp/programming-guide/types/index.md)
- [<span data-ttu-id="0f81c-146">Оператор ()</span><span class="sxs-lookup"><span data-stu-id="0f81c-146">() Operator</span></span>](../../../csharp/language-reference/operators/type-testing-and-conversion-operators.md#cast-operator-)
- [<span data-ttu-id="0f81c-147">explicit</span><span class="sxs-lookup"><span data-stu-id="0f81c-147">explicit</span></span>](../../../csharp/language-reference/keywords/explicit.md)
- [<span data-ttu-id="0f81c-148">implicit</span><span class="sxs-lookup"><span data-stu-id="0f81c-148">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)
- [<span data-ttu-id="0f81c-149">Операторы преобразования</span><span class="sxs-lookup"><span data-stu-id="0f81c-149">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
- <span data-ttu-id="0f81c-150">[Обобщенное преобразование типов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/yy580hbd(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="0f81c-150">[Generalized Type Conversion](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/yy580hbd(v=vs.120))</span></span>
- [<span data-ttu-id="0f81c-151">Практическое руководство. Преобразование строки в число</span><span class="sxs-lookup"><span data-stu-id="0f81c-151">How to: Convert a String to a Number</span></span>](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)
