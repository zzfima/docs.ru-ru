---
title: "Типы указателей (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- unsafe code [C#], pointers
- pointers [C#]
ms.assetid: 3319faf9-336d-4148-9af2-1da2579cdd1e
caps.latest.revision: 19
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
ms.openlocfilehash: 1a4ebc69762f18dc630100b544c18df0f43734ac
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="pointer-types-c-programming-guide"></a><span data-ttu-id="a29fd-102">Типы указателей (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="a29fd-102">Pointer types (C# Programming Guide)</span></span>
<span data-ttu-id="a29fd-103">В небезопасном контексте тип может быть типом указателя, типом значения или ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="a29fd-103">In an unsafe context, a type may be a pointer type, a value type, or a reference type.</span></span> <span data-ttu-id="a29fd-104">Объявления типа указателя выполняется одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="a29fd-104">A pointer type declaration takes one of the following forms:</span></span>  
  
```  
type* identifier;  
void* identifier; //allowed but not recommended  
```  
  
 <span data-ttu-id="a29fd-105">Любой из указанных ниже типов может быть типом указателя:</span><span class="sxs-lookup"><span data-stu-id="a29fd-105">Any of the following types may be a pointer type:</span></span>  
  
-   <span data-ttu-id="a29fd-106">[sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [char](../../../csharp/language-reference/keywords/char.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), [decimal](../../../csharp/language-reference/keywords/decimal.md) или [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="a29fd-106">[sbyte](../../../csharp/language-reference/keywords/sbyte.md), [byte](../../../csharp/language-reference/keywords/byte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [char](../../../csharp/language-reference/keywords/char.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), [decimal](../../../csharp/language-reference/keywords/decimal.md), or [bool](../../../csharp/language-reference/keywords/bool.md).</span></span>  
  
-   <span data-ttu-id="a29fd-107">Любой тип [enum](../../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="a29fd-107">Any [enum](../../../csharp/language-reference/keywords/enum.md) type.</span></span>  
  
-   <span data-ttu-id="a29fd-108">Любой тип указателя.</span><span class="sxs-lookup"><span data-stu-id="a29fd-108">Any pointer type.</span></span>  
  
-   <span data-ttu-id="a29fd-109">Любой пользовательский тип структуры, содержащий поля только неуправляемых типов.</span><span class="sxs-lookup"><span data-stu-id="a29fd-109">Any user-defined struct type that contains fields of unmanaged types only.</span></span>  
  
 <span data-ttu-id="a29fd-110">Типы указателей не наследуются от [объекта](../../../csharp/language-reference/keywords/object.md), а типы указателей не преобразуются в `object`.</span><span class="sxs-lookup"><span data-stu-id="a29fd-110">Pointer types do not inherit from [object](../../../csharp/language-reference/keywords/object.md) and no conversions exist between pointer types and `object`.</span></span> <span data-ttu-id="a29fd-111">Кроме того, упаковка-преобразование и распаковка-преобразование не поддерживают указатели.</span><span class="sxs-lookup"><span data-stu-id="a29fd-111">Also, boxing and unboxing do not support pointers.</span></span> <span data-ttu-id="a29fd-112">Однако можно выполнять преобразования между различными типами указателей, а также между типами указателей и целочисленными типами.</span><span class="sxs-lookup"><span data-stu-id="a29fd-112">However, you can convert between different pointer types and between pointer types and integral types.</span></span>  
  
 <span data-ttu-id="a29fd-113">При объявлении нескольких указателей в одном объявлении знак * указывается только с базовым типом; он не используется в качестве префикса для каждого имени указателя.</span><span class="sxs-lookup"><span data-stu-id="a29fd-113">When you declare multiple pointers in the same declaration, the asterisk (*) is written together with the underlying type only; it is not used as a prefix to each pointer name.</span></span> <span data-ttu-id="a29fd-114">Пример:</span><span class="sxs-lookup"><span data-stu-id="a29fd-114">For example:</span></span>  
  
```  
int* p1, p2, p3;   // Ok  
int *p1, *p2, *p3;   // Invalid in C#  
```  
  
 <span data-ttu-id="a29fd-115">Указатель не может указывать на ссылку или на [структуру](../../../csharp/language-reference/keywords/struct.md), содержащую ссылки, поскольку ссылка на объект может быть подвергнута сбору мусора, даже если на нее указывает указатель.</span><span class="sxs-lookup"><span data-stu-id="a29fd-115">A pointer cannot point to a reference or to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains references, because an object reference can be garbage collected even if a pointer is pointing to it.</span></span> <span data-ttu-id="a29fd-116">Сборщик мусора не отслеживает наличие указателей любых типов, указывающих на объекты.</span><span class="sxs-lookup"><span data-stu-id="a29fd-116">The garbage collector does not keep track of whether an object is being pointed to by any pointer types.</span></span>  
  
 <span data-ttu-id="a29fd-117">Значением переменной-указателя типа `myType*` является адрес переменной типа `myType`.</span><span class="sxs-lookup"><span data-stu-id="a29fd-117">The value of the pointer variable of type `myType*` is the address of a variable of type `myType`.</span></span> <span data-ttu-id="a29fd-118">Ниже приведены примеры объявлений типов указателей.</span><span class="sxs-lookup"><span data-stu-id="a29fd-118">The following are examples of pointer type declarations:</span></span>  
  
|<span data-ttu-id="a29fd-119">Пример</span><span class="sxs-lookup"><span data-stu-id="a29fd-119">Example</span></span>|<span data-ttu-id="a29fd-120">Описание</span><span class="sxs-lookup"><span data-stu-id="a29fd-120">Description</span></span>|  
|-------------|-----------------|  
|`int* p`|<span data-ttu-id="a29fd-121">`p` — указатель на целое число.</span><span class="sxs-lookup"><span data-stu-id="a29fd-121">`p` is a pointer to an integer.</span></span>|  
|`int** p`|<span data-ttu-id="a29fd-122">`p` — указатель на указатель на целое число.</span><span class="sxs-lookup"><span data-stu-id="a29fd-122">`p` is a pointer to a pointer to an integer.</span></span>|  
|`int*[] p`|<span data-ttu-id="a29fd-123">`p` — одномерный массив указателей на целые числа.</span><span class="sxs-lookup"><span data-stu-id="a29fd-123">`p` is a single-dimensional array of pointers to integers.</span></span>|  
|`char* p`|<span data-ttu-id="a29fd-124">`p` — указатель на тип char.</span><span class="sxs-lookup"><span data-stu-id="a29fd-124">`p` is a pointer to a char.</span></span>|  
|`void* p`|<span data-ttu-id="a29fd-125">`p` — указатель на неизвестный тип.</span><span class="sxs-lookup"><span data-stu-id="a29fd-125">`p` is a pointer to an unknown type.</span></span>|  
  
 <span data-ttu-id="a29fd-126">Оператор косвенного обращения указателя * можно использовать для доступа к содержимому, на которое указывает переменная-указатель.</span><span class="sxs-lookup"><span data-stu-id="a29fd-126">The pointer indirection operator * can be used to access the contents at the location pointed to by the pointer variable.</span></span> <span data-ttu-id="a29fd-127">В качестве примера рассмотрим следующее объявление:</span><span class="sxs-lookup"><span data-stu-id="a29fd-127">For example, consider the following declaration:</span></span>  
  
```  
int* myVariable;  
```  
  
 <span data-ttu-id="a29fd-128">Выражение `*myVariable` обозначает переменную `int`, находящуюся по адресу, содержащемуся в `myVariable`.</span><span class="sxs-lookup"><span data-stu-id="a29fd-128">The expression `*myVariable` denotes the `int` variable found at the address contained in `myVariable`.</span></span>  
  
 <span data-ttu-id="a29fd-129">Разделы [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md) и [Преобразования указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md) содержат несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="a29fd-129">There are several examples of pointers in the topics [fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) and [Pointer Conversions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md).</span></span>  <span data-ttu-id="a29fd-130">В следующем примере показана необходимость наличия ключевого слова `unsafe` и оператора `fixed`, а также продемонстрирован способ инкрементирования внутреннего указателя.</span><span class="sxs-lookup"><span data-stu-id="a29fd-130">The following example shows the need for the `unsafe` keyword and the `fixed` statement, and how to increment an interior pointer.</span></span>  <span data-ttu-id="a29fd-131">Этот код можно вставить в функцию Main консольного приложения для его запуска.</span><span class="sxs-lookup"><span data-stu-id="a29fd-131">You can paste this code into the Main function of a console application to run it.</span></span> <span data-ttu-id="a29fd-132">(Не забудьте включить небезопасный код в **Конструктор проектов**. Для этого в строке меню выберите **Проект**, **Свойства**, а затем на вкладке **Сборка** — **Разрешить небезопасный код**.)</span><span class="sxs-lookup"><span data-stu-id="a29fd-132">(Remember to enable unsafe code in the **Project Designer**; choose **Project**, **Properties** on the menu bar, and then select **Allow unsafe code** in the **Build** tab.)</span></span>  
  
```  
// Normal pointer to an object.  
int[] a = new int[5] {10, 20, 30, 40, 50};  
// Must be in unsafe code to use interior pointers.  
unsafe  
{  
    // Must pin object on heap so that it doesn't move while using interior pointers.  
    fixed (int* p = &a[0])  
    {  
        // p is pinned as well as object, so create another pointer to show incrementing it.  
        int* p2 = p;  
        Console.WriteLine(*p2);  
        // Incrementing p2 bumps the pointer by four bytes due to its type ...  
        p2 += 1;  
        Console.WriteLine(*p2);  
        p2 += 1;  
        Console.WriteLine(*p2);  
        Console.WriteLine("--------");  
        Console.WriteLine(*p);  
        // Deferencing p and incrementing changes the value of a[0] ...  
        *p += 1;  
        Console.WriteLine(*p);  
        *p += 1;  
        Console.WriteLine(*p);  
    }  
}  
  
Console.WriteLine("--------");  
Console.WriteLine(a[0]);  
Console.ReadLine();  
  
// Output:  
//10  
//20  
//30  
//--------  
//10  
//11  
//12  
//--------  
//12  
```  
  
 <span data-ttu-id="a29fd-133">Для указателя типа `void*` использовать оператор косвенного обращения нельзя.</span><span class="sxs-lookup"><span data-stu-id="a29fd-133">You cannot apply the indirection operator to a pointer of type `void*`.</span></span> <span data-ttu-id="a29fd-134">Однако можно использовать приведение для преобразования указателя типа void в любой другой тип и наоборот.</span><span class="sxs-lookup"><span data-stu-id="a29fd-134">However, you can use a cast to convert a void pointer to any other pointer type, and vice versa.</span></span>  
  
 <span data-ttu-id="a29fd-135">Указатель может иметь значение `null`.</span><span class="sxs-lookup"><span data-stu-id="a29fd-135">A pointer can be `null`.</span></span> <span data-ttu-id="a29fd-136">При применении оператора косвенного обращения к указателю со значением null результат зависит от конкретной реализации.</span><span class="sxs-lookup"><span data-stu-id="a29fd-136">Applying the indirection operator to a null pointer causes an implementation-defined behavior.</span></span>  
  
 <span data-ttu-id="a29fd-137">Обратите внимание, что при передаче указателей между методами может возникнуть неопределенное поведение.</span><span class="sxs-lookup"><span data-stu-id="a29fd-137">Be aware that passing pointers between methods can cause undefined behavior.</span></span> <span data-ttu-id="a29fd-138">В примерах указатель возвращается в локальную переменную через параметр Out или Ref либо в виде результата функции.</span><span class="sxs-lookup"><span data-stu-id="a29fd-138">Examples are returning a pointer to a local variable through an Out or Ref parameter or as the function result.</span></span> <span data-ttu-id="a29fd-139">Если указатель был задан в фиксированном блоке, переменная, на которую он указывает, больше не может быть фиксированной.</span><span class="sxs-lookup"><span data-stu-id="a29fd-139">If the pointer was set in a fixed block, the variable to which it points may no longer be fixed.</span></span>  
  
 <span data-ttu-id="a29fd-140">В следующей таблице перечислены операторы, которые можно использовать для указателей в небезопасном контексте.</span><span class="sxs-lookup"><span data-stu-id="a29fd-140">The following table lists the operators and statements that can operate on pointers in an unsafe context:</span></span>  
  
|<span data-ttu-id="a29fd-141">Оператор</span><span class="sxs-lookup"><span data-stu-id="a29fd-141">Operator/Statement</span></span>|<span data-ttu-id="a29fd-142">Применение</span><span class="sxs-lookup"><span data-stu-id="a29fd-142">Use</span></span>|  
|-------------------------|---------|  
|*|<span data-ttu-id="a29fd-143">Косвенное обращение к указателю.</span><span class="sxs-lookup"><span data-stu-id="a29fd-143">Performs pointer indirection.</span></span>|  
|->|<span data-ttu-id="a29fd-144">Доступ к члену структуры через указатель.</span><span class="sxs-lookup"><span data-stu-id="a29fd-144">Accesses a member of a struct through a pointer.</span></span>|  
|<span data-ttu-id="a29fd-145">[]</span><span class="sxs-lookup"><span data-stu-id="a29fd-145">[]</span></span>|<span data-ttu-id="a29fd-146">Индексирование указателя.</span><span class="sxs-lookup"><span data-stu-id="a29fd-146">Indexes a pointer.</span></span>|  
|`&`|<span data-ttu-id="a29fd-147">Получение адреса переменной.</span><span class="sxs-lookup"><span data-stu-id="a29fd-147">Obtains the address of a variable.</span></span>|  
|<span data-ttu-id="a29fd-148">++ и --</span><span class="sxs-lookup"><span data-stu-id="a29fd-148">++ and --</span></span>|<span data-ttu-id="a29fd-149">Увеличение и уменьшение указателей.</span><span class="sxs-lookup"><span data-stu-id="a29fd-149">Increments and decrements pointers.</span></span>|  
|<span data-ttu-id="a29fd-150">+ и -</span><span class="sxs-lookup"><span data-stu-id="a29fd-150">+ and -</span></span>|<span data-ttu-id="a29fd-151">Арифметические действия с указателем.</span><span class="sxs-lookup"><span data-stu-id="a29fd-151">Performs pointer arithmetic.</span></span>|  
|<span data-ttu-id="a29fd-152">==, !=, \<, >, \<= и >=</span><span class="sxs-lookup"><span data-stu-id="a29fd-152">==, !=, \<, >, \<=, and >=</span></span>|<span data-ttu-id="a29fd-153">Сравнение указателей.</span><span class="sxs-lookup"><span data-stu-id="a29fd-153">Compares pointers.</span></span>|  
|`stackalloc`|<span data-ttu-id="a29fd-154">Выделение памяти в стеке.</span><span class="sxs-lookup"><span data-stu-id="a29fd-154">Allocates memory on the stack.</span></span>|  
|<span data-ttu-id="a29fd-155">Оператор `fixed`</span><span class="sxs-lookup"><span data-stu-id="a29fd-155">`fixed` statement</span></span>|<span data-ttu-id="a29fd-156">Временная фиксация переменной, чтобы можно было найти ее адрес.</span><span class="sxs-lookup"><span data-stu-id="a29fd-156">Temporarily fixes a variable so that its address may be found.</span></span>|  
  
## <a name="c-language-specification"></a><span data-ttu-id="a29fd-157">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a29fd-157">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a29fd-158">См. также</span><span class="sxs-lookup"><span data-stu-id="a29fd-158">See Also</span></span>  
 <span data-ttu-id="a29fd-159">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a29fd-159">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a29fd-160">[Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="a29fd-160">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="a29fd-161">[Преобразования указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="a29fd-161">[Pointer Conversions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-conversions.md) </span></span>  
 <span data-ttu-id="a29fd-162">[Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="a29fd-162">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="a29fd-163">[Типы](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="a29fd-163">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="a29fd-164">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="a29fd-164">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="a29fd-165">[Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a29fd-165">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 <span data-ttu-id="a29fd-166">[stackalloc](../../../csharp/language-reference/keywords/stackalloc.md) </span><span class="sxs-lookup"><span data-stu-id="a29fd-166">[stackalloc](../../../csharp/language-reference/keywords/stackalloc.md) </span></span>  
 [<span data-ttu-id="a29fd-167">Упаковка-преобразование и распаковка-преобразование</span><span class="sxs-lookup"><span data-stu-id="a29fd-167">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)

