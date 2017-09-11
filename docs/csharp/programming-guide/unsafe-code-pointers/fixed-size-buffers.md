---
title: "Буферы фиксированного размера (Руководство по программированию на C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.assetid: 6220d454-947c-4977-ac9d-9308c6ed5051
caps.latest.revision: 31
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
ms.openlocfilehash: e1a3dcf953cb56fc3436fdd5e7ecb60478a12922
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="02b51-102">Буферы фиксированного размера (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="02b51-102">Fixed Size Buffers (C# Programming Guide)</span></span>
<span data-ttu-id="02b51-103">В языке C# для создания буфера с массивом фиксированного размера в структуре данных можно использовать оператор [fixed](../../../csharp/language-reference/keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="02b51-103">In C#, you can use the [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="02b51-104">Это полезно при работе с существующим кодом, например с кодом, написанным на других языках, ранее созданными библиотеками DLL или проектами COM.</span><span class="sxs-lookup"><span data-stu-id="02b51-104">This is useful when you are working with existing code, such as code written in other languages, pre-existing DLLs or COM projects.</span></span> <span data-ttu-id="02b51-105">Фиксированный массив может принимать любые атрибуты или модификаторы, допустимые для обычных членов структуры.</span><span class="sxs-lookup"><span data-stu-id="02b51-105">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="02b51-106">Единственным ограничением является то, что массив должен иметь тип `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` или `double`.</span><span class="sxs-lookup"><span data-stu-id="02b51-106">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>  
  
```  
private fixed char name[30];  
```  
  
## <a name="remarks"></a><span data-ttu-id="02b51-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="02b51-107">Remarks</span></span>  
 <span data-ttu-id="02b51-108">В предыдущих версиях языка C# объявление структуры фиксированного размера в стиле C++ было затруднительным, так как структура C# с массивом не содержит элементов массива.</span><span class="sxs-lookup"><span data-stu-id="02b51-108">In early versions of C#, declaring a C++ style fixed-size structure was difficult because a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="02b51-109">Вместо этого в ней присутствуют ссылки на элементы.</span><span class="sxs-lookup"><span data-stu-id="02b51-109">Instead, the struct contains a reference to the elements.</span></span>  
  
 <span data-ttu-id="02b51-110">В языке C# версии 2.0 появилась возможность внедрения массива фиксированного размера в [структуру](../../../csharp/language-reference/keywords/struct.md), если он используется в блоке [небезопасного](../../../csharp/language-reference/keywords/unsafe.md) кода.</span><span class="sxs-lookup"><span data-stu-id="02b51-110">C# 2.0 added the ability to embed an array of fixed size in a [struct](../../../csharp/language-reference/keywords/struct.md) when it is used in an [unsafe](../../../csharp/language-reference/keywords/unsafe.md) code block.</span></span>  
  
 <span data-ttu-id="02b51-111">Например, в версиях языка C# до версии 2.0 размер следующего ключевого слова `struct` будет равен 8 байтам.</span><span class="sxs-lookup"><span data-stu-id="02b51-111">For example, before C# 2.0, the following `struct` would be 8 bytes in size.</span></span> <span data-ttu-id="02b51-112">Массив `pathName` является ссылкой на массив с выделением в куче.</span><span class="sxs-lookup"><span data-stu-id="02b51-112">The `pathName` array is a reference to the heap-allocated array:</span></span>  
  
 <span data-ttu-id="02b51-113">[!code-cs[csProgGuidePointers#19](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="02b51-113">[!code-cs[csProgGuidePointers#19](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_1.cs)]</span></span>  
  
 <span data-ttu-id="02b51-114">Начиная с версии C# 2.0 `struct` может содержать внедренный массив.</span><span class="sxs-lookup"><span data-stu-id="02b51-114">Beginning with C# 2.0, a `struct` can contain an embedded array.</span></span> <span data-ttu-id="02b51-115">В приведенном ниже примере массив `fixedBuffer` имеет фиксированный размер.</span><span class="sxs-lookup"><span data-stu-id="02b51-115">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="02b51-116">Для доступа к элементам такого массива используется оператор `fixed`, устанавливающий указатель на первый элемент.</span><span class="sxs-lookup"><span data-stu-id="02b51-116">To access the elements of the array, you use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="02b51-117">Оператор `fixed` закрепляет экземпляр `fixedBuffer` в определенном месте в памяти.</span><span class="sxs-lookup"><span data-stu-id="02b51-117">The `fixed` statement pins an instance of `fixedBuffer` to a specific location in memory.</span></span>  
  
 <span data-ttu-id="02b51-118">[!code-cs[csProgGuidePointers#20](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="02b51-118">[!code-cs[csProgGuidePointers#20](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_2.cs)]</span></span>  
  
 <span data-ttu-id="02b51-119">Размер массива из 128 элементов `char` составляет 256 байт.</span><span class="sxs-lookup"><span data-stu-id="02b51-119">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="02b51-120">В буферах типа [char](../../../csharp/language-reference/keywords/char.md) фиксированного размера на один символ всегда приходится два байта независимо от кодировки.</span><span class="sxs-lookup"><span data-stu-id="02b51-120">Fixed size [char](../../../csharp/language-reference/keywords/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="02b51-121">Это справедливо даже в том случае, когда буферы char маршалируются в методы API или структуры с `CharSet = CharSet.Auto` или `CharSet = CharSet.Ansi`.</span><span class="sxs-lookup"><span data-stu-id="02b51-121">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="02b51-122">Для получения дополнительной информации см. <xref:System.Runtime.InteropServices.CharSet>.</span><span class="sxs-lookup"><span data-stu-id="02b51-122">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>  
  
 <span data-ttu-id="02b51-123">Еще одним распространенным массивом фиксированного размера является массив [bool](../../../csharp/language-reference/keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="02b51-123">Another common fixed-size array is the [bool](../../../csharp/language-reference/keywords/bool.md) array.</span></span> <span data-ttu-id="02b51-124">Элементы в массиве `bool` всегда имеют размер в один байт.</span><span class="sxs-lookup"><span data-stu-id="02b51-124">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="02b51-125">Массивы `bool` не подходят для создания битовых массивов или буферов.</span><span class="sxs-lookup"><span data-stu-id="02b51-125">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02b51-126">За исключением памяти, созданной с помощью [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md), компилятор C# и среда CLR не выполняют проверку переполнения буфера безопасности.</span><span class="sxs-lookup"><span data-stu-id="02b51-126">Except for memory created by using [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md), the C# compiler and the common language runtime (CLR) do not perform any security buffer overrun checks.</span></span> <span data-ttu-id="02b51-127">Как и при работе с любым небезопасным кодом, следует проявлять осторожность.</span><span class="sxs-lookup"><span data-stu-id="02b51-127">As with all unsafe code, use caution.</span></span>  
  
 <span data-ttu-id="02b51-128">Небезопасные буферы отличаются от обычных массивов указанными ниже особенностями.</span><span class="sxs-lookup"><span data-stu-id="02b51-128">Unsafe buffers differ from regular arrays in the following ways:</span></span>  
  
-   <span data-ttu-id="02b51-129">Небезопасные буферы можно использовать в небезопасном контексте.</span><span class="sxs-lookup"><span data-stu-id="02b51-129">You can only use unsafe buffers in an unsafe context.</span></span>  
  
-   <span data-ttu-id="02b51-130">Небезопасные буферы — это всегда векторы или одномерные массивы.</span><span class="sxs-lookup"><span data-stu-id="02b51-130">Unsafe buffers are always vectors, or one-dimensional arrays.</span></span>  
  
-   <span data-ttu-id="02b51-131">В объявлении массива всегда должен присутствовать счетчик, такой как `char id[8]`.</span><span class="sxs-lookup"><span data-stu-id="02b51-131">The declaration of the array should include a count, such as `char id[8]`.</span></span> <span data-ttu-id="02b51-132">При этом `char id[]` нельзя использовать.</span><span class="sxs-lookup"><span data-stu-id="02b51-132">You cannot use `char id[]` instead.</span></span>  
  
-   <span data-ttu-id="02b51-133">Небезопасные буферы могут быть только полями экземпляров структур в небезопасном контексте.</span><span class="sxs-lookup"><span data-stu-id="02b51-133">Unsafe buffers can only be instance fields of structs in an unsafe context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02b51-134">См. также</span><span class="sxs-lookup"><span data-stu-id="02b51-134">See Also</span></span>  
 <span data-ttu-id="02b51-135">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="02b51-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="02b51-136">[Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="02b51-136">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="02b51-137">[Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="02b51-137">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="02b51-138">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="02b51-138">Interoperability</span></span>](../../../csharp/programming-guide/interop/index.md)

