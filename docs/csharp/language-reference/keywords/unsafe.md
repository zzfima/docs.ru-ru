---
title: Справочник по C#. Ключевое слово unsafe
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: 81a293a6922a71f7428167c50aed064d7387a099
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236626"
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="a92aa-102">unsafe (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a92aa-102">unsafe (C# Reference)</span></span>

<span data-ttu-id="a92aa-103">Ключевое слово `unsafe` обозначает небезопасный контекст, необходимый для выполнения любых операций с применением указателей.</span><span class="sxs-lookup"><span data-stu-id="a92aa-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="a92aa-104">Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="a92aa-104">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="a92aa-105">В объявлении типа или члена типа можно использовать модификатор `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="a92aa-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="a92aa-106">Все текстовое пространство типа или члена типа считается небезопасным контекстом.</span><span class="sxs-lookup"><span data-stu-id="a92aa-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="a92aa-107">Например, следующий метод объявлен с модификатором `unsafe`:</span><span class="sxs-lookup"><span data-stu-id="a92aa-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>

```csharp
unsafe static void FastCopy(byte[] src, byte[] dst, int count)
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="a92aa-108">Область небезопасного контекста простирается от списка параметров до конца метода, поэтому в списке параметров можно также использовать указатели:</span><span class="sxs-lookup"><span data-stu-id="a92aa-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>

```csharp
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}
```

<span data-ttu-id="a92aa-109">Кроме того, небезопасный блок позволяет добавлять небезопасный код в блок.</span><span class="sxs-lookup"><span data-stu-id="a92aa-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="a92aa-110">Например:</span><span class="sxs-lookup"><span data-stu-id="a92aa-110">For example:</span></span>

```csharp
unsafe
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="a92aa-111">Для компиляции небезопасного кода необходимо задать параметр компилятора [/unsafe](../compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a92aa-111">To compile unsafe code, you must specify the [/unsafe](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="a92aa-112">Небезопасный код не проверяется средой CLR.</span><span class="sxs-lookup"><span data-stu-id="a92aa-112">Unsafe code is not verifiable by the common language runtime.</span></span>

## <a name="example"></a><span data-ttu-id="a92aa-113">Пример</span><span class="sxs-lookup"><span data-stu-id="a92aa-113">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="a92aa-114">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a92aa-114">C# language specification</span></span>

<span data-ttu-id="a92aa-115">Дополнительные сведения см. в разделе [Небезопасный код](~/_csharplang/spec/unsafe-code.md) в [Спецификации языка C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="a92aa-115">For more information, see [Unsafe code](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="a92aa-116">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="a92aa-116">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="a92aa-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a92aa-117">See also</span></span>

- [<span data-ttu-id="a92aa-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a92aa-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a92aa-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a92aa-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a92aa-120">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="a92aa-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a92aa-121">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="a92aa-121">fixed Statement</span></span>](fixed-statement.md)
- [<span data-ttu-id="a92aa-122">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="a92aa-122">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="a92aa-123">Буферы фиксированного размера</span><span class="sxs-lookup"><span data-stu-id="a92aa-123">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)