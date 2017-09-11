---
title: "enum (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- enum
- enum_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- enum keyword [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
caps.latest.revision: 36
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
ms.openlocfilehash: cf12724ec9e450a2bc237db614f235d7f03a4a7e
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="enum-c-reference"></a><span data-ttu-id="4a69f-102">enum (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="4a69f-102">enum (C# Reference)</span></span>
<span data-ttu-id="4a69f-103">Ключевое слово `enum` используется для объявления перечисления — отдельного типа, который состоит из набора именованных констант, называемого списком перечислителей.</span><span class="sxs-lookup"><span data-stu-id="4a69f-103">The `enum` keyword is used to declare an enumeration, a distinct type that consists of a set of named constants called the enumerator list.</span></span>  
  
 <span data-ttu-id="4a69f-104">Обычно лучше всего определять перечисление непосредственно в пространстве имен, чтобы всем классам в пространстве имен было одинаково удобно обращаться к нему.</span><span class="sxs-lookup"><span data-stu-id="4a69f-104">Usually it is best to define an enum directly within a namespace so that all classes in the namespace can access it with equal convenience.</span></span> <span data-ttu-id="4a69f-105">Однако перечисление также может быть вложенным в классе или структуре.</span><span class="sxs-lookup"><span data-stu-id="4a69f-105">However, an enum can also be nested within a class or struct.</span></span>  
  
 <span data-ttu-id="4a69f-106">По умолчанию первый перечислитель имеет значение 0, и значение каждого последующего перечислителя увеличивается на 1.</span><span class="sxs-lookup"><span data-stu-id="4a69f-106">By default, the first enumerator has the value 0, and the value of each successive enumerator is increased by 1.</span></span> <span data-ttu-id="4a69f-107">Например, в следующем перечислении `Sat` — `0`, `Sun` — `1`, `Mon` — `2`и т. д.</span><span class="sxs-lookup"><span data-stu-id="4a69f-107">For example, in the following enumeration, `Sat` is `0`, `Sun` is `1`, `Mon` is `2`, and so forth.</span></span>  
  
```  
enum Days {Sat, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 <span data-ttu-id="4a69f-108">Перечисления могут использовать инициализаторы для переопределения значений по умолчанию, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4a69f-108">Enumerators can use initializers to override the default values, as shown in the following example.</span></span>  
  
```  
enum Days {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 <span data-ttu-id="4a69f-109">В этом перечислении последовательность элементов принудительно начинается с `1` вместо `0`.</span><span class="sxs-lookup"><span data-stu-id="4a69f-109">In this enumeration, the sequence of elements is forced to start from `1` instead of `0`.</span></span> <span data-ttu-id="4a69f-110">Тем не менее рекомендуется, включая константу, которая имеет значение “0”.</span><span class="sxs-lookup"><span data-stu-id="4a69f-110">However, including a constant that has the value of 0 is recommended.</span></span> <span data-ttu-id="4a69f-111">Дополнительные сведения см. в разделе [Типы перечислений](../../../csharp/programming-guide/enumeration-types.md).</span><span class="sxs-lookup"><span data-stu-id="4a69f-111">For more information, see [Enumeration Types](../../../csharp/programming-guide/enumeration-types.md).</span></span>  
  
 <span data-ttu-id="4a69f-112">Каждый тип перечисления имеет базовый тип, который может быть любым целочисленным типом за исключением [char](../../../csharp/language-reference/keywords/char.md).</span><span class="sxs-lookup"><span data-stu-id="4a69f-112">Every enumeration type has an underlying type, which can be any integral type except [char](../../../csharp/language-reference/keywords/char.md).</span></span> <span data-ttu-id="4a69f-113">Базовым типом перечисления элементов по умолчанию является [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="4a69f-113">The default underlying type of enumeration elements is [int](../../../csharp/language-reference/keywords/int.md).</span></span> <span data-ttu-id="4a69f-114">Чтобы объявить перечисление другого целого типа, например [byte](../../../csharp/language-reference/keywords/byte.md), используется двоеточие после идентификатора, за которым следует тип, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4a69f-114">To declare an enum of another integral type, such as [byte](../../../csharp/language-reference/keywords/byte.md), use a colon after the identifier followed by the type, as shown in the following example.</span></span>  
  
```  
enum Days : byte {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 <span data-ttu-id="4a69f-115">Утвержденные типы для перечисления: `byte`, [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md)и [ulong](../../../csharp/language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="4a69f-115">The approved types for an enum are `byte`, [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
 <span data-ttu-id="4a69f-116">Переменной типа `Days` может быть присвоено любое значение в диапазоне базового типа; значения не ограничиваются именованными константами.</span><span class="sxs-lookup"><span data-stu-id="4a69f-116">A variable of type `Days` can be assigned any value in the range of the underlying type; the values are not limited to the named constants.</span></span>  
  
 <span data-ttu-id="4a69f-117">Значение по умолчанию `enum E` является значением, полученным с помощью выражения `(E)0`.</span><span class="sxs-lookup"><span data-stu-id="4a69f-117">The default value of an `enum E` is the value produced by the expression `(E)0`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a69f-118">Перечислитель не может содержать пробелы в имени.</span><span class="sxs-lookup"><span data-stu-id="4a69f-118">An enumerator cannot contain white space in its name.</span></span>  
  
 <span data-ttu-id="4a69f-119">Базовый тип указывает, какой объем хранилища выделяется для каждого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="4a69f-119">The underlying type specifies how much storage is allocated for each enumerator.</span></span> <span data-ttu-id="4a69f-120">Тем не менее необходимо явное приведение, чтобы преобразовывать из типа `enum` в целочисленный тип.</span><span class="sxs-lookup"><span data-stu-id="4a69f-120">However, an explicit cast is necessary to convert from `enum` type to an integral type.</span></span> <span data-ttu-id="4a69f-121">Например, следующий оператор назначает перечислитель `Sun` для переменной типа [int](../../../csharp/language-reference/keywords/int.md) с помощью приведения, чтобы преобразовать `enum` в `int`.</span><span class="sxs-lookup"><span data-stu-id="4a69f-121">For example, the following statement assigns the enumerator `Sun` to a variable of the type [int](../../../csharp/language-reference/keywords/int.md) by using a cast to convert from `enum` to `int`.</span></span>  
  
```  
int x = (int)Days.Sun;  
```  
  
 <span data-ttu-id="4a69f-122">При применении <xref:System.FlagsAttribute?displayProperty=fullName> к перечислению, содержащему элементы, которые могут быть объединены с помощью побитовой операции `OR` , атрибут влияет на поведение `enum` при использовании с некоторыми средствами.</span><span class="sxs-lookup"><span data-stu-id="4a69f-122">When you apply <xref:System.FlagsAttribute?displayProperty=fullName> to an enumeration that contains elements that can be combined with a bitwise `OR` operation, the attribute affects the behavior of the `enum` when it is used with some tools.</span></span> <span data-ttu-id="4a69f-123">Эти изменения можно заметить при использовании таких средств, как методы класса <xref:System.Console> и вычислитель выражений.</span><span class="sxs-lookup"><span data-stu-id="4a69f-123">You can notice these changes when you use tools such as the <xref:System.Console> class methods and the Expression Evaluator.</span></span> <span data-ttu-id="4a69f-124">(См. третий пример.)</span><span class="sxs-lookup"><span data-stu-id="4a69f-124">(See the third example.)</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4a69f-125">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="4a69f-125">Robust Programming</span></span>  
 <span data-ttu-id="4a69f-126">Как и в случае с любой другой константой, все ссылки на отдельные значения перечисления преобразуются в числовые литералы во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="4a69f-126">Just as with any constant, all references to the individual values of an enum are converted to numeric literals at compile time.</span></span> <span data-ttu-id="4a69f-127">Это может создать потенциальные проблемы с управлением версиями, как описано в разделе [Константы](../../../csharp/programming-guide/classes-and-structs/constants.md).</span><span class="sxs-lookup"><span data-stu-id="4a69f-127">This can create potential versioning issues as described in [Constants](../../../csharp/programming-guide/classes-and-structs/constants.md).</span></span>  
  
 <span data-ttu-id="4a69f-128">Назначение дополнительных значений для новых версий перечислений или изменение значений элементов перечислений в новой версии может вызвать проблемы в зависимом исходном коде.</span><span class="sxs-lookup"><span data-stu-id="4a69f-128">Assigning additional values to new versions of enums, or changing the values of the enum members in a new version, can cause problems for dependent source code.</span></span> <span data-ttu-id="4a69f-129">Значения перечислений часто используются в инструкциях [switсh](../../../csharp/language-reference/keywords/switch.md) .</span><span class="sxs-lookup"><span data-stu-id="4a69f-129">Enum values often are used in [switch](../../../csharp/language-reference/keywords/switch.md) statements.</span></span> <span data-ttu-id="4a69f-130">Если были добавлены дополнительные элементы для типа `enum` , раздел по умолчанию инструкции switch может быть выбран неожиданным образом.</span><span class="sxs-lookup"><span data-stu-id="4a69f-130">If additional elements have been added to the `enum` type, the default section of the switch statement can be selected unexpectedly.</span></span>  
  
 <span data-ttu-id="4a69f-131">Если другие разработчики используют ваш код, необходимо предоставить рекомендации о том, как их код должен реагировать при добавлении новых элементов к любому типу `enum` .</span><span class="sxs-lookup"><span data-stu-id="4a69f-131">If other developers use your code, you should provide guidelines about how their code should react if new elements are added to any `enum` types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a69f-132">Пример</span><span class="sxs-lookup"><span data-stu-id="4a69f-132">Example</span></span>  
 <span data-ttu-id="4a69f-133">В следующем примере объявлено перечисление `Days`.</span><span class="sxs-lookup"><span data-stu-id="4a69f-133">In the following example, an enumeration, `Days`, is declared.</span></span> <span data-ttu-id="4a69f-134">Два перечислителя явно преобразуются в целое число и назначаются для целочисленных переменных.</span><span class="sxs-lookup"><span data-stu-id="4a69f-134">Two enumerators are explicitly converted to integer and assigned to integer variables.</span></span>  
  
 <span data-ttu-id="4a69f-135">[!code-cs[csrefKeywordsTypes#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4a69f-135">[!code-cs[csrefKeywordsTypes#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a69f-136">Пример</span><span class="sxs-lookup"><span data-stu-id="4a69f-136">Example</span></span>  
 <span data-ttu-id="4a69f-137">В следующем примере используется параметр базового типа для объявления `enum` , члены которого имеют тип `long`.</span><span class="sxs-lookup"><span data-stu-id="4a69f-137">In the following example, the base-type option is used to declare an `enum` whose members are of type `long`.</span></span> <span data-ttu-id="4a69f-138">Обратите внимание, что, даже если базовый тип перечисления является `long`, члены перечисления по-прежнему должны быть явно преобразованы в тип `long` с помощью приведения.</span><span class="sxs-lookup"><span data-stu-id="4a69f-138">Notice that even though the underlying type of the enumeration is `long`, the enumeration members still must be explicitly converted to type `long` by using a cast.</span></span>  
  
 <span data-ttu-id="4a69f-139">[!code-cs[csrefKeywordsTypes#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4a69f-139">[!code-cs[csrefKeywordsTypes#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a69f-140">Пример</span><span class="sxs-lookup"><span data-stu-id="4a69f-140">Example</span></span>  
 <span data-ttu-id="4a69f-141">В следующем примере кода показано использование и влияние атрибута <xref:System.FlagsAttribute?displayProperty=fullName> на объявление `enum` .</span><span class="sxs-lookup"><span data-stu-id="4a69f-141">The following code example illustrates the use and effect of the <xref:System.FlagsAttribute?displayProperty=fullName> attribute on an `enum` declaration.</span></span>  
  
 <span data-ttu-id="4a69f-142">[!code-cs[csrefKeywordsTypes#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="4a69f-142">[!code-cs[csrefKeywordsTypes#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_3.cs)]</span></span>  
  
## <a name="comments"></a><span data-ttu-id="4a69f-143">Комментарии</span><span class="sxs-lookup"><span data-stu-id="4a69f-143">Comments</span></span>  
 <span data-ttu-id="4a69f-144">Если удалить `Flags`, в примере будут показаны следующие значения.</span><span class="sxs-lookup"><span data-stu-id="4a69f-144">If you remove `Flags`, the example displays the following values:</span></span>  
  
 `5`  
  
 `5`  
  
## <a name="c-language-specification"></a><span data-ttu-id="4a69f-145">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="4a69f-145">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4a69f-146">См. также</span><span class="sxs-lookup"><span data-stu-id="4a69f-146">See Also</span></span>  
 <span data-ttu-id="4a69f-147">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4a69f-147">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4a69f-148">[Типы перечисления](../../../csharp/programming-guide/enumeration-types.md) </span><span class="sxs-lookup"><span data-stu-id="4a69f-148">[Enumeration Types](../../../csharp/programming-guide/enumeration-types.md) </span></span>  
 <span data-ttu-id="4a69f-149">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="4a69f-149">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="4a69f-150">[Таблица целых типов](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="4a69f-150">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="4a69f-151">[Таблица встроенных типов](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="4a69f-151">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="4a69f-152">[Таблица неявных числовых преобразований](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="4a69f-152">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="4a69f-153">Таблица явных числовых преобразований</span><span class="sxs-lookup"><span data-stu-id="4a69f-153">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

