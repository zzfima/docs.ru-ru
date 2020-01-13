---
title: Справочник по C#. Ключевое слово unsafe
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: ef98809eae0329c028dfb318c4a437aae4736db1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712992"
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="190dc-102">unsafe (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="190dc-102">unsafe (C# Reference)</span></span>

<span data-ttu-id="190dc-103">Ключевое слово `unsafe` обозначает небезопасный контекст, необходимый для выполнения любых операций с применением указателей.</span><span class="sxs-lookup"><span data-stu-id="190dc-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="190dc-104">Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="190dc-104">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="190dc-105">В объявлении типа или члена типа можно использовать модификатор `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="190dc-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="190dc-106">Все текстовое пространство типа или члена типа считается небезопасным контекстом.</span><span class="sxs-lookup"><span data-stu-id="190dc-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="190dc-107">Например, следующий метод объявлен с модификатором `unsafe`:</span><span class="sxs-lookup"><span data-stu-id="190dc-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>

```csharp
unsafe static void FastCopy(byte[] src, byte[] dst, int count)
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="190dc-108">Область небезопасного контекста простирается от списка параметров до конца метода, поэтому в списке параметров можно также использовать указатели:</span><span class="sxs-lookup"><span data-stu-id="190dc-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>

```csharp
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}
```

<span data-ttu-id="190dc-109">Кроме того, небезопасный блок позволяет добавлять небезопасный код в блок.</span><span class="sxs-lookup"><span data-stu-id="190dc-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="190dc-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="190dc-110">For example:</span></span>

```csharp
unsafe
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="190dc-111">Чтобы скомпилировать небезопасный код, необходимо указать параметр компилятора [`-unsafe`](../compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="190dc-111">To compile unsafe code, you must specify the [`-unsafe`](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="190dc-112">Небезопасный код не проверяется средой CLR.</span><span class="sxs-lookup"><span data-stu-id="190dc-112">Unsafe code is not verifiable by the common language runtime.</span></span>

## <a name="example"></a><span data-ttu-id="190dc-113">Пример</span><span class="sxs-lookup"><span data-stu-id="190dc-113">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="190dc-114">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="190dc-114">C# language specification</span></span>

<span data-ttu-id="190dc-115">Дополнительные сведения см. в разделе [Небезопасный код](~/_csharplang/spec/unsafe-code.md) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="190dc-115">For more information, see [Unsafe code](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="190dc-116">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="190dc-116">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="190dc-117">См. также</span><span class="sxs-lookup"><span data-stu-id="190dc-117">See also</span></span>

- [<span data-ttu-id="190dc-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="190dc-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="190dc-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="190dc-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="190dc-120">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="190dc-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="190dc-121">Оператор fixed</span><span class="sxs-lookup"><span data-stu-id="190dc-121">fixed Statement</span></span>](fixed-statement.md)
- [<span data-ttu-id="190dc-122">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="190dc-122">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="190dc-123">Буферы фиксированного размера</span><span class="sxs-lookup"><span data-stu-id="190dc-123">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
