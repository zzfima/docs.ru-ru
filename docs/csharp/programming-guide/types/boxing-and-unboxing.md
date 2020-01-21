---
title: Руководство по программированию на C#. Упаковка-преобразование и распаковка-преобразование
ms.date: 07/20/2015
f1_keywords:
- cs.boxing
helpviewer_keywords:
- C# language, boxing
- C# language, unboxing
- unboxing [C#]
- boxing [C#]
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
ms.openlocfilehash: 32156ad0fe4b3dce4371fe757d15f5b8040aaf19
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "76115852"
---
# <a name="boxing-and-unboxing-c-programming-guide"></a><span data-ttu-id="124aa-102">Упаковка-преобразование и распаковка-преобразование (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="124aa-102">Boxing and Unboxing (C# Programming Guide)</span></span>

<span data-ttu-id="124aa-103">Упаковка представляет собой процесс преобразования [типа значения](../../language-reference/keywords/value-types.md) в тип `object` или в любой другой тип интерфейса, реализуемый этим типом значения.</span><span class="sxs-lookup"><span data-stu-id="124aa-103">Boxing is the process of converting a [value type](../../language-reference/keywords/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="124aa-104">Когда тип значения упаковывается общеязыковой средой выполнения (CLR), он инкапсулирует значение внутри экземпляра <xref:System.Object?displayProperty=nameWithType> и сохраняет его в управляемой куче.</span><span class="sxs-lookup"><span data-stu-id="124aa-104">When the common language runtime (CLR) boxes a value type, it wraps the value inside a <xref:System.Object?displayProperty=nameWithType> instance and stores it on the managed heap.</span></span> <span data-ttu-id="124aa-105">Операция распаковки извлекает тип значения из объекта.</span><span class="sxs-lookup"><span data-stu-id="124aa-105">Unboxing extracts the value type from the object.</span></span> <span data-ttu-id="124aa-106">Упаковка является неявной; распаковка является явной.</span><span class="sxs-lookup"><span data-stu-id="124aa-106">Boxing is implicit; unboxing is explicit.</span></span> <span data-ttu-id="124aa-107">Понятия упаковки и распаковки лежат в основе единой системы типов C#, в которой значение любого типа можно рассматривать как объект.</span><span class="sxs-lookup"><span data-stu-id="124aa-107">The concept of boxing and unboxing underlies the C# unified view of the type system in which a value of any type can be treated as an object.</span></span>

<span data-ttu-id="124aa-108">В следующем примере выполнена операция `i`упаковки *целочисленной переменной*, которая присвоена объекту `o`.</span><span class="sxs-lookup"><span data-stu-id="124aa-108">In the following example, the integer variable `i` is *boxed* and assigned to object `o`.</span></span>

[!code-csharp[csProgGuideTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#14)]

<span data-ttu-id="124aa-109">Затем можно выполнить операцию распаковки объекта `o`и присвоить его целочисленной переменной `i`:</span><span class="sxs-lookup"><span data-stu-id="124aa-109">The object `o` can then be unboxed and assigned to integer variable `i`:</span></span>

[!code-csharp[csProgGuideTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#15)]

<span data-ttu-id="124aa-110">Следующий пример иллюстрирует использование упаковки в C#.</span><span class="sxs-lookup"><span data-stu-id="124aa-110">The following examples illustrate how boxing is used in C#.</span></span>

[!code-csharp[csProgGuideTypes#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#47)]

## <a name="performance"></a><span data-ttu-id="124aa-111">Производительность</span><span class="sxs-lookup"><span data-stu-id="124aa-111">Performance</span></span>

<span data-ttu-id="124aa-112">По сравнению с простыми операциями присваивания операции упаковки и распаковки являются весьма затратными процессами с точки зрения вычислений.</span><span class="sxs-lookup"><span data-stu-id="124aa-112">In relation to simple assignments, boxing and unboxing are computationally expensive processes.</span></span> <span data-ttu-id="124aa-113">При выполнении упаковки типа значения необходимо создать и разместить новый объект.</span><span class="sxs-lookup"><span data-stu-id="124aa-113">When a value type is boxed, a new object must be allocated and constructed.</span></span> <span data-ttu-id="124aa-114">Объем вычислений при выполнении операции распаковки, хотя и в меньшей степени, но тоже весьма значителен.</span><span class="sxs-lookup"><span data-stu-id="124aa-114">To a lesser degree, the cast required for unboxing is also expensive computationally.</span></span> <span data-ttu-id="124aa-115">Дополнительные сведения см. в разделе [Производительность](../../../framework/performance/performance-tips.md).</span><span class="sxs-lookup"><span data-stu-id="124aa-115">For more information, see [Performance](../../../framework/performance/performance-tips.md).</span></span>

## <a name="boxing"></a><span data-ttu-id="124aa-116">Упаковка</span><span class="sxs-lookup"><span data-stu-id="124aa-116">Boxing</span></span>

<span data-ttu-id="124aa-117">Упаковка используется для хранения типов значений в куче со сбором мусора.</span><span class="sxs-lookup"><span data-stu-id="124aa-117">Boxing is used to store value types in the garbage-collected heap.</span></span> <span data-ttu-id="124aa-118">Упаковка представляет собой неявное преобразование [типа значения](../../language-reference/keywords/value-types.md) в тип `object` или в любой другой тип интерфейса, реализуемый этим типом значения.</span><span class="sxs-lookup"><span data-stu-id="124aa-118">Boxing is an implicit conversion of a [value type](../../language-reference/keywords/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="124aa-119">При упаковке типа значения в куче выделяется экземпляр объекта и выполняется копирование значения в этот новый объект.</span><span class="sxs-lookup"><span data-stu-id="124aa-119">Boxing a value type allocates an object instance on the heap and copies the value into the new object.</span></span>

<span data-ttu-id="124aa-120">Рассмотрим следующее объявление переменной типа значения.</span><span class="sxs-lookup"><span data-stu-id="124aa-120">Consider the following declaration of a value-type variable:</span></span>

[!code-csharp[csProgGuideTypes#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#17)]

<span data-ttu-id="124aa-121">Следующий оператор неявно применяет операцию упаковки к переменной `i`.</span><span class="sxs-lookup"><span data-stu-id="124aa-121">The following statement implicitly applies the boxing operation on the variable `i`:</span></span>

[!code-csharp[csProgGuideTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#18)]

<span data-ttu-id="124aa-122">Результат этого оператора создает ссылку на объект `o` в стеке, которая ссылается на значение типа `int` в куче.</span><span class="sxs-lookup"><span data-stu-id="124aa-122">The result of this statement is creating an object reference `o`, on the stack, that references a value of the type `int`, on the heap.</span></span> <span data-ttu-id="124aa-123">Это значение является копией значения типа значения, присвоенного переменной `i`.</span><span class="sxs-lookup"><span data-stu-id="124aa-123">This value is a copy of the value-type value assigned to the variable `i`.</span></span> <span data-ttu-id="124aa-124">Разница между этими двумя переменными, `i` и `o`, показана на рисунке упаковки-преобразования ниже:</span><span class="sxs-lookup"><span data-stu-id="124aa-124">The difference between the two variables, `i` and `o`, is illustrated in the following image of boxing conversion:</span></span>

![Рисунок, иллюстрирующий разницу между переменными "i" и "o".](./media/boxing-and-unboxing/boxing-operation-i-o-variables.gif)

<span data-ttu-id="124aa-126">Можно также выполнять упаковку явным образом, как в следующем примере, однако явная упаковка не является обязательной.</span><span class="sxs-lookup"><span data-stu-id="124aa-126">It is also possible to perform the boxing explicitly as in the following example, but explicit boxing is never required:</span></span>

[!code-csharp[csProgGuideTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#19)]

## <a name="description"></a><span data-ttu-id="124aa-127">Описание</span><span class="sxs-lookup"><span data-stu-id="124aa-127">Description</span></span>

<span data-ttu-id="124aa-128">В этом примере целочисленная переменная `i` преобразуется в объект `o` при помощи упаковки.</span><span class="sxs-lookup"><span data-stu-id="124aa-128">This example converts an integer variable `i` to an object `o` by using boxing.</span></span> <span data-ttu-id="124aa-129">Затем значение, хранимое переменной `i`, меняется с `123` на `456`.</span><span class="sxs-lookup"><span data-stu-id="124aa-129">Then, the value stored in the variable `i` is changed from `123` to `456`.</span></span> <span data-ttu-id="124aa-130">В примере показано, что исходный тип значения и упакованный объект используют отдельные ячейки памяти, а значит могут хранить разные значения.</span><span class="sxs-lookup"><span data-stu-id="124aa-130">The example shows that the original value type and the boxed object use separate memory locations, and therefore can store different values.</span></span>

## <a name="example"></a><span data-ttu-id="124aa-131">Пример</span><span class="sxs-lookup"><span data-stu-id="124aa-131">Example</span></span>

[!code-csharp[csProgGuideTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#16)]

## <a name="unboxing"></a><span data-ttu-id="124aa-132">Распаковка</span><span class="sxs-lookup"><span data-stu-id="124aa-132">Unboxing</span></span>

<span data-ttu-id="124aa-133">Распаковка является явным преобразованием из типа `object` в [тип значения](../../language-reference/keywords/value-types.md) или из типа интерфейса в тип значения, реализующего этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="124aa-133">Unboxing is an explicit conversion from the type `object` to a [value type](../../language-reference/keywords/value-types.md) or from an interface type to a value type that implements the interface.</span></span> <span data-ttu-id="124aa-134">Операция распаковки состоит из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="124aa-134">An unboxing operation consists of:</span></span>

- <span data-ttu-id="124aa-135">проверка экземпляра объекта на то, что он является упакованным значением заданного типа значения;</span><span class="sxs-lookup"><span data-stu-id="124aa-135">Checking the object instance to make sure that it is a boxed value of the given value type.</span></span>

- <span data-ttu-id="124aa-136">копирование значения из экземпляра в переменную типа значения.</span><span class="sxs-lookup"><span data-stu-id="124aa-136">Copying the value from the instance into the value-type variable.</span></span>

<span data-ttu-id="124aa-137">В следующем коде показаны операции по упаковке и распаковке.</span><span class="sxs-lookup"><span data-stu-id="124aa-137">The following statements demonstrate both boxing and unboxing operations:</span></span>

[!code-csharp[csProgGuideTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#21)]

<span data-ttu-id="124aa-138">На рисунке ниже представлен результат выполнения этого кода.</span><span class="sxs-lookup"><span data-stu-id="124aa-138">The following figure demonstrates the result of the previous statements:</span></span>

![Рисунок, иллюстрирующий распаковку-преобразование.](./media/boxing-and-unboxing/unboxing-conversion-operation.gif)

<span data-ttu-id="124aa-140">Для успешной распаковки типов значений во время выполнения необходимо, чтобы экземпляр, который распаковывается, был ссылкой на объект, предварительно созданный с помощью упаковки экземпляра этого типа значения.</span><span class="sxs-lookup"><span data-stu-id="124aa-140">For the unboxing of value types to succeed at run time, the item being unboxed must be a reference to an object that was previously created by boxing an instance of that value type.</span></span> <span data-ttu-id="124aa-141">Попытка распаковать `null` создает исключение <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="124aa-141">Attempting to unbox `null` causes a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="124aa-142">Попытка распаковать ссылку на несовместимый тип значения создает исключение <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="124aa-142">Attempting to unbox a reference to an incompatible value type causes an <xref:System.InvalidCastException>.</span></span>

## <a name="example"></a><span data-ttu-id="124aa-143">Пример</span><span class="sxs-lookup"><span data-stu-id="124aa-143">Example</span></span>

<span data-ttu-id="124aa-144">В следующем примере показан случай недопустимой распаковки, в результате чего создается исключение `InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="124aa-144">The following example demonstrates a case of invalid unboxing and the resulting `InvalidCastException`.</span></span> <span data-ttu-id="124aa-145">В случае использования `try` и `catch` при возникновении ошибки выводится сообщение.</span><span class="sxs-lookup"><span data-stu-id="124aa-145">Using `try` and `catch`, an error message is displayed when the error occurs.</span></span>

[!code-csharp[csProgGuideTypes#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#20)]

<span data-ttu-id="124aa-146">При выполнении этой программы выводится следующий результат:</span><span class="sxs-lookup"><span data-stu-id="124aa-146">This program outputs:</span></span>

`Specified cast is not valid. Error: Incorrect unboxing.`

<span data-ttu-id="124aa-147">При изменении оператора:</span><span class="sxs-lookup"><span data-stu-id="124aa-147">If you change the statement:</span></span>

```csharp
int j = (short) o;
```

<span data-ttu-id="124aa-148">на:</span><span class="sxs-lookup"><span data-stu-id="124aa-148">to:</span></span>

```csharp
int j = (int) o;
```

<span data-ttu-id="124aa-149">будет выполнено преобразование со следующим результатом:</span><span class="sxs-lookup"><span data-stu-id="124aa-149">the conversion will be performed, and you will get the output:</span></span>

`Unboxing OK.`

## <a name="c-language-specification"></a><span data-ttu-id="124aa-150">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="124aa-150">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="related-sections"></a><span data-ttu-id="124aa-151">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="124aa-151">Related sections</span></span>

<span data-ttu-id="124aa-152">Дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="124aa-152">For more information:</span></span>

- [<span data-ttu-id="124aa-153">Ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="124aa-153">Reference Types</span></span>](../../language-reference/keywords/reference-types.md)

- [<span data-ttu-id="124aa-154">Типы значений</span><span class="sxs-lookup"><span data-stu-id="124aa-154">Value Types</span></span>](../../language-reference/keywords/value-types.md)

## <a name="see-also"></a><span data-ttu-id="124aa-155">См. также</span><span class="sxs-lookup"><span data-stu-id="124aa-155">See also</span></span>

- [<span data-ttu-id="124aa-156">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="124aa-156">C# Programming Guide</span></span>](../index.md)
