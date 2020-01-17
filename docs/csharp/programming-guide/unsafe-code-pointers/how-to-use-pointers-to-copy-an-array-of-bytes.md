---
title: Руководство по программированию на C#. Использование указателей для копирования массива байтов
ms.date: 04/20/2018
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.openlocfilehash: 4929699c2d1e07b16d4694cff79f9b1394b1de38
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75698460"
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes-c-programming-guide"></a><span data-ttu-id="22ad4-102">Руководство по программированию на C#. Использование указателей для копирования массива байтов</span><span class="sxs-lookup"><span data-stu-id="22ad4-102">How to use pointers to copy an array of bytes (C# Programming Guide)</span></span>

<span data-ttu-id="22ad4-103">В следующем примере указатели используются для копирования байт из одного массива в другой.</span><span class="sxs-lookup"><span data-stu-id="22ad4-103">The following example uses pointers to copy bytes from one array to another.</span></span>

<span data-ttu-id="22ad4-104">В этом примере применяется ключевое слово [unsafe](../../language-reference/keywords/unsafe.md), которое позволяет использовать указатели в методе `Copy`.</span><span class="sxs-lookup"><span data-stu-id="22ad4-104">This example uses the [unsafe](../../language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="22ad4-105">Оператор [fixed](../../language-reference/keywords/fixed-statement.md) используется для объявления указателей исходного и конечного массивов.</span><span class="sxs-lookup"><span data-stu-id="22ad4-105">The [fixed](../../language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="22ad4-106">Оператор `fixed`*закрепляет* расположение исходного и конечного массивов в памяти, чтобы они не перемещались при сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="22ad4-106">The `fixed` statement *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="22ad4-107">Закрепление этих блоков памяти отменяется, когда завершается обработка блока `fixed`.</span><span class="sxs-lookup"><span data-stu-id="22ad4-107">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="22ad4-108">Поскольку метод `Copy` в этом примере использует ключевое слово `unsafe`, он должен быть скомпилирован с параметром компилятора [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="22ad4-108">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>

<span data-ttu-id="22ad4-109">В этом примере доступ к элементам обоих массивов выполняется с помощью индексов, а не второго неуправляемого указателя.</span><span class="sxs-lookup"><span data-stu-id="22ad4-109">This example accesses the elements of both arrays using indices rather than a second unmanaged pointer.</span></span> <span data-ttu-id="22ad4-110">Объявление указателей `pSource` и `pTarget` закрепляет массивы.</span><span class="sxs-lookup"><span data-stu-id="22ad4-110">The declaration of the `pSource` and `pTarget` pointers pins the arrays.</span></span> <span data-ttu-id="22ad4-111">Эта возможность доступна начиная с C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="22ad4-111">This feature is available starting with C# 7.3.</span></span>

## <a name="example"></a><span data-ttu-id="22ad4-112">Пример</span><span class="sxs-lookup"><span data-stu-id="22ad4-112">Example</span></span>

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a><span data-ttu-id="22ad4-113">См. также</span><span class="sxs-lookup"><span data-stu-id="22ad4-113">See also</span></span>

- [<span data-ttu-id="22ad4-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="22ad4-114">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="22ad4-115">Небезопасный код и указатели</span><span class="sxs-lookup"><span data-stu-id="22ad4-115">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="22ad4-116">-unsafe (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="22ad4-116">-unsafe (C# Compiler Options)</span></span>](../../language-reference/compiler-options/unsafe-compiler-option.md)
- [<span data-ttu-id="22ad4-117">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="22ad4-117">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
