---
title: Маршалинг типов в .NET
description: Из этой статьи вы узнаете, как платформа .NET маршалирует ваши типы данных в собственное представление.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: b4846f2e6cd945a25ec6a747c9038d48fe115559
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185419"
---
# <a name="type-marshalling"></a><span data-ttu-id="dfa20-103">Маршалинг типов</span><span class="sxs-lookup"><span data-stu-id="dfa20-103">Type marshalling</span></span>

<span data-ttu-id="dfa20-104">**Маршалинг** — это процесс преобразования типов при переходе от управляемого кода к машинному.</span><span class="sxs-lookup"><span data-stu-id="dfa20-104">**Marshalling** is the process of transforming types when they need to cross between managed and native code.</span></span>

<span data-ttu-id="dfa20-105">Необходимость в маршалинге вызвана различием типов в управляемом и неуправляемом коде.</span><span class="sxs-lookup"><span data-stu-id="dfa20-105">Marshalling is needed because the types in the managed and unmanaged code are different.</span></span> <span data-ttu-id="dfa20-106">Например, в управляемом коде имеется `String`, а в неуправляемом строки могут иметь различный формат: Юникод, отличный от Юникода, с конечным символом NULL, ASCII и т. д. По умолчанию подсистема P/Invoke пытается выбрать правильное решение в зависимости от реакции на событие по умолчанию, описанной в этой статье.</span><span class="sxs-lookup"><span data-stu-id="dfa20-106">In managed code, for instance, you have a `String`, while in the unmanaged world strings can be Unicode ("wide"), non-Unicode, null-terminated, ASCII, etc. By default, the P/Invoke subsystem tries to do the right thing based on the default behavior, described on this article.</span></span> <span data-ttu-id="dfa20-107">Однако в ситуациях, когда требуется дополнительный контроль, можно применить атрибут [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute), чтобы указать ожидаемый тип на стороне неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="dfa20-107">However, for those situations where you need extra control, you can employ the [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) attribute to specify what is the expected type on the unmanaged side.</span></span> <span data-ttu-id="dfa20-108">Например, если строку нужно передать в виде строки ANSI с конечным символом NULL, это можно сделать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="dfa20-108">For instance, if you want the string to be sent as a null-terminated ANSI string, you could do it like this:</span></span>

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

## <a name="default-rules-for-marshalling-common-types"></a><span data-ttu-id="dfa20-109">Правила маршалинга общих типов</span><span class="sxs-lookup"><span data-stu-id="dfa20-109">Default rules for marshalling common types</span></span>

<span data-ttu-id="dfa20-110">Обычно среда выполнения пытается маршалировать типы "правильно", чтобы от пользователя не потребовалось каких-либо действий.</span><span class="sxs-lookup"><span data-stu-id="dfa20-110">Generally, the runtime tries to do the "right thing" when marshalling to require the least amount of work from you.</span></span> <span data-ttu-id="dfa20-111">В приведенных ниже таблицах показано, как при использовании в параметре или поле каждый тип данных маршалируется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dfa20-111">The following tables describe how each type is marshalled by default when used in a parameter or field.</span></span> <span data-ttu-id="dfa20-112">Чтобы проверить правильность данных в приведенных ниже таблицах для всех платформ, используются символьные и целочисленные (фиксированной ширины) типы данных C99/C++11.</span><span class="sxs-lookup"><span data-stu-id="dfa20-112">The C99/C++11 fixed-width integer and character types are used to ensure that the following table is correct for all platforms.</span></span> <span data-ttu-id="dfa20-113">Используйте любой собственный тип, который имеет такое же выравнивание и требования к размеру, как эти типы данных.</span><span class="sxs-lookup"><span data-stu-id="dfa20-113">You can use any native type that has the same alignment and size requirements as these types.</span></span>

<span data-ttu-id="dfa20-114">В первой таблице представлены сопоставления различных типов, для которых маршалинг выполняется одинаково — как для P/Invoke, так и для поля.</span><span class="sxs-lookup"><span data-stu-id="dfa20-114">This first table describes the mappings for various types for whom the marshalling is the same for both P/Invoke and field marshalling.</span></span>

| <span data-ttu-id="dfa20-115">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="dfa20-115">.NET Type</span></span> | <span data-ttu-id="dfa20-116">Собственный тип</span><span class="sxs-lookup"><span data-stu-id="dfa20-116">Native Type</span></span>  |
|-----------|-------------------------|
| `byte`    | `uint8_t`               |
| `sbyte`   | `int8_t`                |
| `short`   | `int16_t`               |
| `ushort`  | `uint16_t`              |
| `int`     | `int32_t`               |
| `uint`    | `uint32_t`              |
| `long`    | `int64_t`               |
| `ulong`   | `uint64_t`              |
| `char`    | <span data-ttu-id="dfa20-117">Тип `char` или `char16_t` в зависимости от кодировки `CharSet` P/Invoke или структуры.</span><span class="sxs-lookup"><span data-stu-id="dfa20-117">Either `char` or `char16_t` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="dfa20-118">См. дополнительные сведения в [документации по кодировке](charset.md).</span><span class="sxs-lookup"><span data-stu-id="dfa20-118">See the [charset documentation](charset.md).</span></span> |
| `string`  | <span data-ttu-id="dfa20-119">Тип `char*` или `char16_t*` в зависимости от кодировки `CharSet` P/Invoke или структуры.</span><span class="sxs-lookup"><span data-stu-id="dfa20-119">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="dfa20-120">См. дополнительные сведения в [документации по кодировке](charset.md).</span><span class="sxs-lookup"><span data-stu-id="dfa20-120">See the [charset documentation](charset.md).</span></span> |
| `System.IntPtr` | `intptr_t`        |
| `System.UIntPtr` | `uintptr_t`      |
| <span data-ttu-id="dfa20-121">Типы указателей .NET (за исключением</span><span class="sxs-lookup"><span data-stu-id="dfa20-121">.NET Pointer types (ex.</span></span> <span data-ttu-id="dfa20-122">`void*`)</span><span class="sxs-lookup"><span data-stu-id="dfa20-122">`void*`)</span></span>  | `void*` |
| <span data-ttu-id="dfa20-123">Тип, производный от `System.Runtime.InteropServices.SafeHandle`</span><span class="sxs-lookup"><span data-stu-id="dfa20-123">Type derived from `System.Runtime.InteropServices.SafeHandle`</span></span> | `void*` |
| <span data-ttu-id="dfa20-124">Тип, производный от `System.Runtime.InteropServices.CriticalHandle`</span><span class="sxs-lookup"><span data-stu-id="dfa20-124">Type derived from `System.Runtime.InteropServices.CriticalHandle`</span></span> | `void*`          |
| `bool`    | <span data-ttu-id="dfa20-125">Тип Win32 `BOOL`</span><span class="sxs-lookup"><span data-stu-id="dfa20-125">Win32 `BOOL` type</span></span>       |
| `decimal` | <span data-ttu-id="dfa20-126">Структура COM `DECIMAL`</span><span class="sxs-lookup"><span data-stu-id="dfa20-126">COM `DECIMAL` struct</span></span> |
| <span data-ttu-id="dfa20-127">Делегат .NET</span><span class="sxs-lookup"><span data-stu-id="dfa20-127">.NET Delegate</span></span> | <span data-ttu-id="dfa20-128">Собственный указатель функции</span><span class="sxs-lookup"><span data-stu-id="dfa20-128">Native function pointer</span></span> |
| `System.DateTime` | <span data-ttu-id="dfa20-129">Тип Win32 `DATE`</span><span class="sxs-lookup"><span data-stu-id="dfa20-129">Win32 `DATE` type</span></span> |
| `System.Guid` | <span data-ttu-id="dfa20-130">Тип Win32 `GUID`</span><span class="sxs-lookup"><span data-stu-id="dfa20-130">Win32 `GUID` type</span></span> |

<span data-ttu-id="dfa20-131">Если вы маршалируете тип как параметр или структуру, несколько категорий маршалинга будут иметь разные значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dfa20-131">A few categories of marshalling have different defaults if you're marshalling as a parameter or structure.</span></span>

| <span data-ttu-id="dfa20-132">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="dfa20-132">.NET Type</span></span> | <span data-ttu-id="dfa20-133">Собственный тип (параметр)</span><span class="sxs-lookup"><span data-stu-id="dfa20-133">Native Type (Parameter)</span></span> | <span data-ttu-id="dfa20-134">Собственный тип (поле)</span><span class="sxs-lookup"><span data-stu-id="dfa20-134">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| <span data-ttu-id="dfa20-135">Массив .NET</span><span class="sxs-lookup"><span data-stu-id="dfa20-135">.NET array</span></span> | <span data-ttu-id="dfa20-136">Указатель на начало массива в собственном представлении элементов массива.</span><span class="sxs-lookup"><span data-stu-id="dfa20-136">A pointer to the start of an array of native representations of the array elements.</span></span> | <span data-ttu-id="dfa20-137">Нельзя использовать без атрибута `[MarshalAs]`</span><span class="sxs-lookup"><span data-stu-id="dfa20-137">Not allowed without a `[MarshalAs]` attribute</span></span>|
| <span data-ttu-id="dfa20-138">Класс, где для `LayoutKind` задано значение `Sequential` или `Explicit`</span><span class="sxs-lookup"><span data-stu-id="dfa20-138">A class with a `LayoutKind` of `Sequential` or `Explicit`</span></span> | <span data-ttu-id="dfa20-139">Указатель на собственное представление класса</span><span class="sxs-lookup"><span data-stu-id="dfa20-139">A pointer to the native representation of the class</span></span> | <span data-ttu-id="dfa20-140">Собственное представление класса</span><span class="sxs-lookup"><span data-stu-id="dfa20-140">The native representation of the class</span></span> |

<span data-ttu-id="dfa20-141">В приведенной ниже таблице содержатся правила маршалинга, применяемые по умолчанию только для Windows.</span><span class="sxs-lookup"><span data-stu-id="dfa20-141">The following table includes the default marshalling rules that are Windows-only.</span></span> <span data-ttu-id="dfa20-142">На других платформах (не Windows) эти типы нельзя маршалировать.</span><span class="sxs-lookup"><span data-stu-id="dfa20-142">On non-Windows platforms, you cannot marshal these types.</span></span>

| <span data-ttu-id="dfa20-143">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="dfa20-143">.NET Type</span></span> | <span data-ttu-id="dfa20-144">Собственный тип (параметр)</span><span class="sxs-lookup"><span data-stu-id="dfa20-144">Native Type (Parameter)</span></span> | <span data-ttu-id="dfa20-145">Собственный тип (поле)</span><span class="sxs-lookup"><span data-stu-id="dfa20-145">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| `object`  | `VARIANT`               | `IUnknown*`         |
| `System.Array` | <span data-ttu-id="dfa20-146">Интерфейс COM</span><span class="sxs-lookup"><span data-stu-id="dfa20-146">COM interface</span></span> | <span data-ttu-id="dfa20-147">Нельзя использовать без атрибута `[MarshalAs]`</span><span class="sxs-lookup"><span data-stu-id="dfa20-147">Not allowed without a `[MarshalAs]` attribute</span></span> |
| `System.ArgIterator` | `va_list` | <span data-ttu-id="dfa20-148">Нельзя использовать</span><span class="sxs-lookup"><span data-stu-id="dfa20-148">Not allowed</span></span> |
| `System.Collections.IEnumerator` | `IEnumVARIANT*` | <span data-ttu-id="dfa20-149">Нельзя использовать</span><span class="sxs-lookup"><span data-stu-id="dfa20-149">Not allowed</span></span> |
| `System.Collections.IEnumerable` | `IDispatch*` | <span data-ttu-id="dfa20-150">Нельзя использовать</span><span class="sxs-lookup"><span data-stu-id="dfa20-150">Not allowed</span></span> |
| `System.DateTimeOffset` | <span data-ttu-id="dfa20-151">`int64_t` — число тактов начиная с полуночи 1 января 1601 года.</span><span class="sxs-lookup"><span data-stu-id="dfa20-151">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> || <span data-ttu-id="dfa20-152">`int64_t` — число тактов начиная с полуночи 1 января 1601 года.</span><span class="sxs-lookup"><span data-stu-id="dfa20-152">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> |

<span data-ttu-id="dfa20-153">Некоторые типы можно маршалировать только как параметры и нельзя — как поля.</span><span class="sxs-lookup"><span data-stu-id="dfa20-153">Some types can only be marshalled as parameters and not as fields.</span></span> <span data-ttu-id="dfa20-154">Эти типы перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="dfa20-154">These types are listed in the following table:</span></span>

| <span data-ttu-id="dfa20-155">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="dfa20-155">.NET Type</span></span> | <span data-ttu-id="dfa20-156">Собственный тип (только параметр)</span><span class="sxs-lookup"><span data-stu-id="dfa20-156">Native Type (Parameter Only)</span></span> |
|-----------|------------------------------|
| `System.Text.StringBuilder` | <span data-ttu-id="dfa20-157">Тип `char*` или `char16_t*` в зависимости от кодировки `CharSet` P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="dfa20-157">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke.</span></span>  <span data-ttu-id="dfa20-158">См. дополнительные сведения в [документации по кодировке](charset.md).</span><span class="sxs-lookup"><span data-stu-id="dfa20-158">See the [charset documentation](charset.md).</span></span> |
| `System.ArgIterator` | <span data-ttu-id="dfa20-159">`va_list` (только в Windows x86/x64/arm64)</span><span class="sxs-lookup"><span data-stu-id="dfa20-159">`va_list` (on Windows x86/x64/arm64 only)</span></span> |
| `System.Runtime.InteropServices.ArrayWithOffset` | `void*` |
| `System.Runtime.InteropServices.HandleRef` | `void*` |

<span data-ttu-id="dfa20-160">Если эти значения по умолчанию вам не подходят, вы можете настроить маршалинг параметров.</span><span class="sxs-lookup"><span data-stu-id="dfa20-160">If these defaults don't do exactly what you want, you can customize how parameters are marshalled.</span></span> <span data-ttu-id="dfa20-161">В статье о [маршалинге параметров](customize-parameter-marshalling.md) описана настройка маршалинга различных типов параметров.</span><span class="sxs-lookup"><span data-stu-id="dfa20-161">The [parameter marshalling](customize-parameter-marshalling.md) article walks you through how to customize how different parameter types are marshalled.</span></span>

## <a name="marshalling-classes-and-structs"></a><span data-ttu-id="dfa20-162">Маршалинг классов и структур</span><span class="sxs-lookup"><span data-stu-id="dfa20-162">Marshalling classes and structs</span></span>

<span data-ttu-id="dfa20-163">Другим аспектом маршалинга типов является способ передачи структуры в неуправляемый метод.</span><span class="sxs-lookup"><span data-stu-id="dfa20-163">Another aspect of type marshalling is how to pass in a struct to an unmanaged method.</span></span> <span data-ttu-id="dfa20-164">Например, некоторые неуправляемые методы требуют указания структуры в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="dfa20-164">For instance, some of the unmanaged methods require a struct as a parameter.</span></span> <span data-ttu-id="dfa20-165">В таких случаях необходимо создать соответствующую структуру или соответствующий класс в управляемом коде и использовать в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="dfa20-165">In these cases, you need to create a corresponding struct or a class in managed part of the world to use it as a parameter.</span></span> <span data-ttu-id="dfa20-166">Но определить класс недостаточно. Нужно также указать маршалеру, как сопоставлять поля класса с неуправляемой структурой.</span><span class="sxs-lookup"><span data-stu-id="dfa20-166">However, just defining the class isn't enough, you also need to instruct the marshaler how to map fields in the class to the unmanaged struct.</span></span> <span data-ttu-id="dfa20-167">Здесь пригодится атрибут `StructLayout`.</span><span class="sxs-lookup"><span data-stu-id="dfa20-167">Here the `StructLayout` attribute becomes useful.</span></span>

```csharp
[DllImport("kernel32.dll")]
static extern void GetSystemTime(SystemTime systemTime);

[StructLayout(LayoutKind.Sequential)]
class SystemTime {
    public ushort Year;
    public ushort Month;
    public ushort DayOfWeek;
    public ushort Day;
    public ushort Hour;
    public ushort Minute;
    public ushort Second;
    public ushort Milsecond;
}

public static void Main(string[] args) {
    SystemTime st = new SystemTime();
    GetSystemTime(st);
    Console.WriteLine(st.Year);
}
```

<span data-ttu-id="dfa20-168">В приведенном выше примере представлен код вызова функции `GetSystemTime()`.</span><span class="sxs-lookup"><span data-stu-id="dfa20-168">The previous code shows a simple example of calling into `GetSystemTime()` function.</span></span> <span data-ttu-id="dfa20-169">Интерес представляет строка 4.</span><span class="sxs-lookup"><span data-stu-id="dfa20-169">The interesting bit is on line 4.</span></span> <span data-ttu-id="dfa20-170">Атрибут указывает, что поля класса должны последовательно сопоставляться со структурой на другой (неуправляемой) стороне.</span><span class="sxs-lookup"><span data-stu-id="dfa20-170">The attribute specifies that the fields of the class should be mapped sequentially to the struct on the other (unmanaged) side.</span></span> <span data-ttu-id="dfa20-171">Это означает, что имена полей не важны, важен только их порядок, так как он должен соответствовать неуправляемой структуре, которая показана в приведенном ниже примере:</span><span class="sxs-lookup"><span data-stu-id="dfa20-171">This means that the naming of the fields isn't important, only their order is important, as it needs to correspond to the unmanaged struct, shown in the following example:</span></span>

```c
typedef struct _SYSTEMTIME {
  WORD wYear;
  WORD wMonth;
  WORD wDayOfWeek;
  WORD wDay;
  WORD wHour;
  WORD wMinute;
  WORD wSecond;
  WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME*;
```

<span data-ttu-id="dfa20-172">Иногда маршалинг по умолчанию не решает задачу для вашей структуры.</span><span class="sxs-lookup"><span data-stu-id="dfa20-172">Sometimes the default marshalling for your structure doesn't do what you need.</span></span> <span data-ttu-id="dfa20-173">Дополнительные сведения см. в статье о [настройке маршалинга структуры](./customize-struct-marshalling.md).</span><span class="sxs-lookup"><span data-stu-id="dfa20-173">The [Customizing structure marshalling](./customize-struct-marshalling.md) article teaches you how to customize how your structure is marshaled.</span></span>
