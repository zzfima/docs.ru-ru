---
title: Оператор fixed (Справочник по C#)
ms.date: 04/20/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5dd117461f792ec7a10b740fbad277de52d05623
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="a8cee-102">Оператор fixed (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a8cee-102">fixed Statement (C# Reference)</span></span>

<span data-ttu-id="a8cee-103">Оператор `fixed` не позволяет сборщику мусора переносить перемещаемую переменную.</span><span class="sxs-lookup"><span data-stu-id="a8cee-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="a8cee-104">Оператор `fixed` допускается только в [небезопасном](unsafe.md) контексте.</span><span class="sxs-lookup"><span data-stu-id="a8cee-104">The `fixed` statement is only permitted in an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="a8cee-105">`Fixed` также можно использовать для создания [буферов фиксированного размера](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="a8cee-105">`Fixed` can also be used to create [fixed size buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

<span data-ttu-id="a8cee-106">Оператор `fixed` задает указатель на управляемую переменную и "закрепляет" эту переменную во время выполнения оператора.</span><span class="sxs-lookup"><span data-stu-id="a8cee-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="a8cee-107">Указатели на перемещаемые управляемые переменные полезны только в контексте `fixed`.</span><span class="sxs-lookup"><span data-stu-id="a8cee-107">Pointers to movable managed variables are useful only in a `fixed` context.</span></span> <span data-ttu-id="a8cee-108">Без контекста `fixed` при сборке мусора эти переменные могут переноситься непредсказуемым образом.</span><span class="sxs-lookup"><span data-stu-id="a8cee-108">Without a `fixed` context, garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="a8cee-109">Компилятор C# позволяет присвоить указатель только управляемой переменной в операторе `fixed`.</span><span class="sxs-lookup"><span data-stu-id="a8cee-109">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

<span data-ttu-id="a8cee-110">Вы можете инициализировать указатель, используя массив, строку, буфер фиксированного размера или адрес переменной.</span><span class="sxs-lookup"><span data-stu-id="a8cee-110">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="a8cee-111">В приведенном ниже примере демонстрируется использование переменных адресов, массивов и строк.</span><span class="sxs-lookup"><span data-stu-id="a8cee-111">The following example illustrates the use of variable addresses, arrays, and strings.</span></span> <span data-ttu-id="a8cee-112">Дополнительные сведения о буферах фиксированного размера см. в разделе [Буферы фиксированного размера](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="a8cee-112">For more information about fixed-size buffers, see [Fixed Size Buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

<span data-ttu-id="a8cee-113">В одном операторе можно инициализировать несколько указателей одного типа.</span><span class="sxs-lookup"><span data-stu-id="a8cee-113">Multiple pointers can be initialized in one statement if they are all the same type:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

<span data-ttu-id="a8cee-114">Чтобы инициализировать указатели разных типов, просто вложите операторы `fixed`, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="a8cee-114">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

<span data-ttu-id="a8cee-115">После выполнения кода в операторе закрепление всех переменных отменяется, и они могут пройти сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="a8cee-115">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="a8cee-116">Таким образом, не следует использовать указатели на эти переменные за пределами оператора `fixed`.</span><span class="sxs-lookup"><span data-stu-id="a8cee-116">Therefore, do not point to those variables outside the `fixed` statement.</span></span> <span data-ttu-id="a8cee-117">Переменные, объявленные в операторе `fixed`, относятся к этому оператору, что упрощает выполнение следующего выражения.</span><span class="sxs-lookup"><span data-stu-id="a8cee-117">The variables declared in the `fixed` statement are scoped to that statement, making this easier:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

<span data-ttu-id="a8cee-118">Указатели, инициализированные в операторах `fixed`, являются переменными только для чтения.</span><span class="sxs-lookup"><span data-stu-id="a8cee-118">Pointers initialized in `fixed` statements are readonly variables.</span></span> <span data-ttu-id="a8cee-119">Чтобы изменить значение указателя, необходимо объявить переменную второго указателя и изменить ее.</span><span class="sxs-lookup"><span data-stu-id="a8cee-119">If you want to modify the pointer value, you must declare a second pointer variable, and modify that.</span></span> <span data-ttu-id="a8cee-120">Переменную, объявленную в операторе `fixed`, изменить невозможно.</span><span class="sxs-lookup"><span data-stu-id="a8cee-120">The variable declared in the `fixed` statement cannot be modified:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```


<span data-ttu-id="a8cee-121">В небезопасном режиме вы можете выделить память в стеке, где сборка мусора не производится и, соответственно, закрепление не требуется.</span><span class="sxs-lookup"><span data-stu-id="a8cee-121">In unsafe mode, you can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="a8cee-122">Дополнительные сведения см. в разделе [stackalloc](stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="a8cee-122">For more information, see [stackalloc](stackalloc.md).</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="a8cee-123">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a8cee-123">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a8cee-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a8cee-124">See Also</span></span>

 [<span data-ttu-id="a8cee-125">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a8cee-125">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="a8cee-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a8cee-126">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="a8cee-127">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="a8cee-127">C# Keywords</span></span>](index.md)  
 [<span data-ttu-id="a8cee-128">unsafe</span><span class="sxs-lookup"><span data-stu-id="a8cee-128">unsafe</span></span>](unsafe.md)  
 [<span data-ttu-id="a8cee-129">Буферы фиксированного размера</span><span class="sxs-lookup"><span data-stu-id="a8cee-129">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
