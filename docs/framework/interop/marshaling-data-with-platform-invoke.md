---
title: Маршалинг данных при вызове неуправляемого кода
ms.date: 03/20/2019
dev_langs:
- cpp
helpviewer_keywords:
- platform invoke, marshaling data
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: dc5c76cf-7b12-406f-b79c-d1a023ec245d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3cb310dc6d786c3c7711f4c194c6623324c777dd
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412400"
---
# <a name="marshaling-data-with-platform-invoke"></a><span data-ttu-id="d483f-102">Маршалинг данных при вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="d483f-102">Marshaling Data with Platform Invoke</span></span>

<span data-ttu-id="d483f-103">Для вызова функций, экспортированных из неуправляемой библиотеки, приложению .NET Framework требуется прототип функции в управляемом коде, представляющий неуправляемую функцию.</span><span class="sxs-lookup"><span data-stu-id="d483f-103">To call functions exported from an unmanaged library, a .NET Framework application requires a function prototype in managed code that represents the unmanaged function.</span></span> <span data-ttu-id="d483f-104">Чтобы создать прототип, который допускает вызов неуправляемого кода для правильного маршалинга данных, необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d483f-104">To create a prototype that enables platform invoke to marshal data correctly, you must do the following:</span></span>

- <span data-ttu-id="d483f-105">Примените атрибут <xref:System.Runtime.InteropServices.DllImportAttribute> к статической функции или методу в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="d483f-105">Apply the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to the static function or method in managed code.</span></span>

- <span data-ttu-id="d483f-106">Замените неуправляемые типы данных на управляемые.</span><span class="sxs-lookup"><span data-stu-id="d483f-106">Substitute managed data types for unmanaged data types.</span></span>

<span data-ttu-id="d483f-107">Чтобы создать эквивалентный управляемый прототип путем применения атрибута с необязательными полями и замены неуправляемых типов данных на управляемые, можно использовать документацию, предоставляемую с неуправляемой функцией.</span><span class="sxs-lookup"><span data-stu-id="d483f-107">You can use the documentation supplied with an unmanaged function to construct an equivalent managed prototype by applying the attribute with its optional fields and substituting managed data types for unmanaged types.</span></span> <span data-ttu-id="d483f-108">Инструкции по применению <xref:System.Runtime.InteropServices.DllImportAttribute> см. в разделе [Использование неуправляемых функций DLL](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md).</span><span class="sxs-lookup"><span data-stu-id="d483f-108">For instructions about how to apply the <xref:System.Runtime.InteropServices.DllImportAttribute>, see [Consuming Unmanaged DLL Functions](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md).</span></span>

<span data-ttu-id="d483f-109">В этом разделе содержатся примеры, демонстрирующие способы создания прототипов управляемых функций для передачи аргументов и получения значений от функций, экспортируемых из неуправляемых библиотек.</span><span class="sxs-lookup"><span data-stu-id="d483f-109">This section provides samples that demonstrate how to create managed function prototypes for passing arguments to and receiving return values from functions exported by unmanaged libraries.</span></span> <span data-ttu-id="d483f-110">В примерах также демонстрируется использование атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute> и класса <xref:System.Runtime.InteropServices.Marshal> для явного маршалинга данных.</span><span class="sxs-lookup"><span data-stu-id="d483f-110">The samples also demonstrate when to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute and the <xref:System.Runtime.InteropServices.Marshal> class to explicitly marshal data.</span></span>

## <a name="platform-invoke-data-types"></a><span data-ttu-id="d483f-111">Типы данных в вызове неуправляемого кода</span><span class="sxs-lookup"><span data-stu-id="d483f-111">Platform invoke data types</span></span>

<span data-ttu-id="d483f-112">Ниже перечислены типы данных, используемые в API Windows и в функциях в стиле C.</span><span class="sxs-lookup"><span data-stu-id="d483f-112">The following table lists data types used in the Windows APIs and C-style functions.</span></span> <span data-ttu-id="d483f-113">Многие неуправляемые библиотеки содержат функции, передающие эти типы данных в качестве параметров и возвращаемых значений.</span><span class="sxs-lookup"><span data-stu-id="d483f-113">Many unmanaged libraries contain functions that pass these data types as parameters and return values.</span></span> <span data-ttu-id="d483f-114">В третьем столбце представлены соответствующие встроенные типы значений .NET Framework или классы, используемые в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="d483f-114">The third column lists the corresponding .NET Framework built-in value type or class that you use in managed code.</span></span> <span data-ttu-id="d483f-115">В некоторых случаях типы, перечисленные в таблице, можно заменить на типы того же размера.</span><span class="sxs-lookup"><span data-stu-id="d483f-115">In some cases, you can substitute a type of the same size for the type listed in the table.</span></span>

|<span data-ttu-id="d483f-116">Неуправляемый тип в API Windows</span><span class="sxs-lookup"><span data-stu-id="d483f-116">Unmanaged type in Windows APIs</span></span>|<span data-ttu-id="d483f-117">Неуправляемый тип языка C</span><span class="sxs-lookup"><span data-stu-id="d483f-117">Unmanaged C language type</span></span>|<span data-ttu-id="d483f-118">Управляемый тип</span><span class="sxs-lookup"><span data-stu-id="d483f-118">Managed type</span></span>|<span data-ttu-id="d483f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d483f-119">Description</span></span>|
|--------------------------------|-------------------------------|------------------------|-----------------|
|`VOID`|`void`|<xref:System.Void?displayProperty=nameWithType>|<span data-ttu-id="d483f-120">Применяется к функции, которая не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="d483f-120">Applied to a function that does not return a value.</span></span>|
|`HANDLE`|`void *`|<span data-ttu-id="d483f-121"><xref:System.IntPtr?displayProperty=nameWithType> или <xref:System.UIntPtr?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d483f-121"><xref:System.IntPtr?displayProperty=nameWithType> or <xref:System.UIntPtr?displayProperty=nameWithType></span></span>|<span data-ttu-id="d483f-122">32 бита в 32-разрядных операционных системах Windows, 64 бита в 64-разрядных операционных системах Windows.</span><span class="sxs-lookup"><span data-stu-id="d483f-122">32 bits on 32-bit Windows operating systems, 64 bits on 64-bit Windows operating systems.</span></span>|
|`BYTE`|`unsigned char`|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="d483f-123">8 бит</span><span class="sxs-lookup"><span data-stu-id="d483f-123">8 bits</span></span>|
|`SHORT`|`short`|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="d483f-124">16 бит</span><span class="sxs-lookup"><span data-stu-id="d483f-124">16 bits</span></span>|
|`WORD`|`unsigned short`|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="d483f-125">16 бит</span><span class="sxs-lookup"><span data-stu-id="d483f-125">16 bits</span></span>|
|`INT`|`int`|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="d483f-126">32 бита</span><span class="sxs-lookup"><span data-stu-id="d483f-126">32 bits</span></span>|
|`UINT`|`unsigned int`|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="d483f-127">32 бита</span><span class="sxs-lookup"><span data-stu-id="d483f-127">32 bits</span></span>|
|`LONG`|`long`|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="d483f-128">32 бита</span><span class="sxs-lookup"><span data-stu-id="d483f-128">32 bits</span></span>|
|`BOOL`|`long`|<span data-ttu-id="d483f-129"><xref:System.Boolean?displayProperty=nameWithType> или <xref:System.Int32?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d483f-129"><xref:System.Boolean?displayProperty=nameWithType> or <xref:System.Int32?displayProperty=nameWithType></span></span>|<span data-ttu-id="d483f-130">32 бита</span><span class="sxs-lookup"><span data-stu-id="d483f-130">32 bits</span></span>|
|`DWORD`|`unsigned long`|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="d483f-131">32 бита</span><span class="sxs-lookup"><span data-stu-id="d483f-131">32 bits</span></span>|
|`ULONG`|`unsigned long`|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="d483f-132">32 бита</span><span class="sxs-lookup"><span data-stu-id="d483f-132">32 bits</span></span>|
|`CHAR`|`char`|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="d483f-133">В кодировке ANSI.</span><span class="sxs-lookup"><span data-stu-id="d483f-133">Decorate with ANSI.</span></span>|
|`WCHAR`|`wchar_t`|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="d483f-134">В кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="d483f-134">Decorate with Unicode.</span></span>|
|`LPSTR`|`char *`|<span data-ttu-id="d483f-135"><xref:System.String?displayProperty=nameWithType> или <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d483f-135"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="d483f-136">В кодировке ANSI.</span><span class="sxs-lookup"><span data-stu-id="d483f-136">Decorate with ANSI.</span></span>|
|`LPCSTR`|`const char *`|<span data-ttu-id="d483f-137"><xref:System.String?displayProperty=nameWithType> или <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d483f-137"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="d483f-138">В кодировке ANSI.</span><span class="sxs-lookup"><span data-stu-id="d483f-138">Decorate with ANSI.</span></span>|
|`LPWSTR`|`wchar_t *`|<span data-ttu-id="d483f-139"><xref:System.String?displayProperty=nameWithType> или <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d483f-139"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="d483f-140">В кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="d483f-140">Decorate with Unicode.</span></span>|
|`LPCWSTR`|`const wchar_t *`|<span data-ttu-id="d483f-141"><xref:System.String?displayProperty=nameWithType> или <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d483f-141"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="d483f-142">В кодировке Юникод.</span><span class="sxs-lookup"><span data-stu-id="d483f-142">Decorate with Unicode.</span></span>|
|`FLOAT`|`float`|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="d483f-143">32 бита</span><span class="sxs-lookup"><span data-stu-id="d483f-143">32 bits</span></span>|
|`DOUBLE`|`double`|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="d483f-144">64 бита</span><span class="sxs-lookup"><span data-stu-id="d483f-144">64 bits</span></span>|

<span data-ttu-id="d483f-145">Соответствующие типы в Visual Basic, C# и C++ см. в разделе [Общие сведения о библиотеке классов .NET Framework](../../standard/class-library-overview.md#system-namespace).</span><span class="sxs-lookup"><span data-stu-id="d483f-145">For corresponding types in Visual Basic, C#, and C++, see the [Introduction to the .NET Framework Class Library](../../standard/class-library-overview.md#system-namespace).</span></span>

## <a name="pinvokelibdll"></a><span data-ttu-id="d483f-146">PinvokeLib.dll</span><span class="sxs-lookup"><span data-stu-id="d483f-146">PinvokeLib.dll</span></span>

<span data-ttu-id="d483f-147">В примере кода ниже определяются функции библиотеки, предоставляемые Pinvoke.dll.</span><span class="sxs-lookup"><span data-stu-id="d483f-147">The following code defines the library functions provided by Pinvoke.dll.</span></span> <span data-ttu-id="d483f-148">Многие из примеров, описанных в этом разделе, вызывают эту библиотеку.</span><span class="sxs-lookup"><span data-stu-id="d483f-148">Many samples described in this section call this library.</span></span>

### <a name="example"></a><span data-ttu-id="d483f-149">Пример</span><span class="sxs-lookup"><span data-stu-id="d483f-149">Example</span></span>

[!code-cpp[PInvokeLib#1](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.cpp#1)]

[!code-cpp[PInvokeLib#2](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.h#2)]
