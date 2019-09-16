---
title: Маршалинг типов — .NET
description: Из этой статьи вы узнаете, как платформа .NET маршалирует ваши типы данных в собственное представление.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: bc44a2c63dfa3fde3e3c4197e5d1fe79857ea717
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929068"
---
# <a name="type-marshaling"></a><span data-ttu-id="8e341-103">Маршалинг типов</span><span class="sxs-lookup"><span data-stu-id="8e341-103">Type marshaling</span></span>

<span data-ttu-id="8e341-104">**Маршалинг** — это процесс преобразования типов при переходе от управляемого кода к машинному.</span><span class="sxs-lookup"><span data-stu-id="8e341-104">**Marshaling** is the process of transforming types when they need to cross between managed and native code.</span></span>

<span data-ttu-id="8e341-105">Необходимость в маршалинге вызвана различием типов в управляемом и неуправляемом коде.</span><span class="sxs-lookup"><span data-stu-id="8e341-105">Marshaling is needed because the types in the managed and unmanaged code are different.</span></span> <span data-ttu-id="8e341-106">Например, в управляемом коде имеется `String`, а в неуправляемом строки могут иметь различный формат: Юникод, отличный от Юникода, с конечным символом NULL, ASCII и т. д. По умолчанию подсистема P/Invoke пытается выбрать правильное решение в зависимости от реакции на событие по умолчанию, описанной в этой статье.</span><span class="sxs-lookup"><span data-stu-id="8e341-106">In managed code, for instance, you have a `String`, while in the unmanaged world strings can be Unicode ("wide"), non-Unicode, null-terminated, ASCII, etc. By default, the P/Invoke subsystem tries to do the right thing based on the default behavior, described on this article.</span></span> <span data-ttu-id="8e341-107">Однако в ситуациях, когда требуется дополнительный контроль, можно применить атрибут [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute), чтобы указать ожидаемый тип на стороне неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="8e341-107">However, for those situations where you need extra control, you can employ the [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) attribute to specify what is the expected type on the unmanaged side.</span></span> <span data-ttu-id="8e341-108">Например, если строку нужно передать в виде строки ANSI с конечным символом NULL, это можно сделать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8e341-108">For instance, if you want the string to be sent as a null-terminated ANSI string, you could do it like this:</span></span>

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

## <a name="default-rules-for-marshaling-common-types"></a><span data-ttu-id="8e341-109">Правила маршалинга общих типов</span><span class="sxs-lookup"><span data-stu-id="8e341-109">Default rules for marshaling common types</span></span>

<span data-ttu-id="8e341-110">Обычно среда выполнения пытается маршалировать типы "правильно", чтобы от пользователя не потребовалось никаких действий.</span><span class="sxs-lookup"><span data-stu-id="8e341-110">Generally, the runtime tries to do the "right thing" when marshaling to require the least amount of work from you.</span></span> <span data-ttu-id="8e341-111">В приведенных ниже таблицах показано, как при использовании в параметре или поле каждый тип данных маршалируется по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8e341-111">The following tables describe how each type is marshaled by default when used in a parameter or field.</span></span> <span data-ttu-id="8e341-112">Чтобы проверить правильность данных в приведенных ниже таблицах для всех платформ, используются символьные и целочисленные (фиксированной ширины) типы данных C99/C++11.</span><span class="sxs-lookup"><span data-stu-id="8e341-112">The C99/C++11 fixed-width integer and character types are used to ensure that the following table is correct for all platforms.</span></span> <span data-ttu-id="8e341-113">Используйте любой собственный тип, который имеет такое же выравнивание и требования к размеру, как эти типы данных.</span><span class="sxs-lookup"><span data-stu-id="8e341-113">You can use any native type that has the same alignment and size requirements as these types.</span></span>

<span data-ttu-id="8e341-114">В первой таблице представлены сопоставления различных типов, для которых маршалинг выполняется одинаково — как для P/Invoke, так и для поля.</span><span class="sxs-lookup"><span data-stu-id="8e341-114">This first table describes the mappings for various types for whom the marshaling is the same for both P/Invoke and field marshaling.</span></span>

| <span data-ttu-id="8e341-115">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="8e341-115">.NET Type</span></span> | <span data-ttu-id="8e341-116">Собственный тип</span><span class="sxs-lookup"><span data-stu-id="8e341-116">Native Type</span></span>  |
|-----------|-------------------------|
| `byte`    | `uint8_t`               |
| `sbyte`   | `int8_t`                |
| `short`   | `int16_t`               |
| `ushort`  | `uint16_t`              |
| `int`     | `int32_t`               |
| `uint`    | `uint32_t`              |
| `long`    | `int64_t`               |
| `ulong`   | `uint64_t`              |
| `char`    | <span data-ttu-id="8e341-117">Тип `char` или `char16_t` в зависимости от кодировки `CharSet` P/Invoke или структуры.</span><span class="sxs-lookup"><span data-stu-id="8e341-117">Either `char` or `char16_t` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="8e341-118">См. дополнительные сведения в [документации по кодировке](charset.md).</span><span class="sxs-lookup"><span data-stu-id="8e341-118">See the [charset documentation](charset.md).</span></span> |
| `string`  | <span data-ttu-id="8e341-119">Тип `char*` или `char16_t*` в зависимости от кодировки `CharSet` P/Invoke или структуры.</span><span class="sxs-lookup"><span data-stu-id="8e341-119">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="8e341-120">См. дополнительные сведения в [документации по кодировке](charset.md).</span><span class="sxs-lookup"><span data-stu-id="8e341-120">See the [charset documentation](charset.md).</span></span> |
| `System.IntPtr` | `intptr_t`        |
| `System.UIntPtr` | `uintptr_t`      |
| <span data-ttu-id="8e341-121">Типы указателей .NET (за исключением</span><span class="sxs-lookup"><span data-stu-id="8e341-121">.NET Pointer types (ex.</span></span> <span data-ttu-id="8e341-122">`void*`)</span><span class="sxs-lookup"><span data-stu-id="8e341-122">`void*`)</span></span>  | `void*` |
| <span data-ttu-id="8e341-123">Тип, производный от `System.Runtime.InteropServices.SafeHandle`</span><span class="sxs-lookup"><span data-stu-id="8e341-123">Type derived from `System.Runtime.InteropServices.SafeHandle`</span></span> | `void*` |
| <span data-ttu-id="8e341-124">Тип, производный от `System.Runtime.InteropServices.CriticalHandle`</span><span class="sxs-lookup"><span data-stu-id="8e341-124">Type derived from `System.Runtime.InteropServices.CriticalHandle`</span></span> | `void*`          |
| `bool`    | <span data-ttu-id="8e341-125">Тип Win32 `BOOL`</span><span class="sxs-lookup"><span data-stu-id="8e341-125">Win32 `BOOL` type</span></span>       |
| `decimal` | <span data-ttu-id="8e341-126">Структура COM `DECIMAL`</span><span class="sxs-lookup"><span data-stu-id="8e341-126">COM `DECIMAL` struct</span></span> |
| <span data-ttu-id="8e341-127">Делегат .NET</span><span class="sxs-lookup"><span data-stu-id="8e341-127">.NET Delegate</span></span> | <span data-ttu-id="8e341-128">Собственный указатель функции</span><span class="sxs-lookup"><span data-stu-id="8e341-128">Native function pointer</span></span> |
| `System.DateTime` | <span data-ttu-id="8e341-129">Тип Win32 `DATE`</span><span class="sxs-lookup"><span data-stu-id="8e341-129">Win32 `DATE` type</span></span> |
| `System.Guid` | <span data-ttu-id="8e341-130">Тип Win32 `GUID`</span><span class="sxs-lookup"><span data-stu-id="8e341-130">Win32 `GUID` type</span></span> |

<span data-ttu-id="8e341-131">Если вы маршалируете тип как параметр или структуру, несколько категорий маршалинга будут иметь разные значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8e341-131">A few categories of marshaling have different defaults if you're marshaling as a parameter or structure.</span></span>

| <span data-ttu-id="8e341-132">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="8e341-132">.NET Type</span></span> | <span data-ttu-id="8e341-133">Собственный тип (параметр)</span><span class="sxs-lookup"><span data-stu-id="8e341-133">Native Type (Parameter)</span></span> | <span data-ttu-id="8e341-134">Собственный тип (поле)</span><span class="sxs-lookup"><span data-stu-id="8e341-134">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| <span data-ttu-id="8e341-135">Массив .NET</span><span class="sxs-lookup"><span data-stu-id="8e341-135">.NET array</span></span> | <span data-ttu-id="8e341-136">Указатель на начало массива в собственном представлении элементов массива.</span><span class="sxs-lookup"><span data-stu-id="8e341-136">A pointer to the start of an array of native representations of the array elements.</span></span> | <span data-ttu-id="8e341-137">Нельзя использовать без атрибута `[MarshalAs]`</span><span class="sxs-lookup"><span data-stu-id="8e341-137">Not allowed without a `[MarshalAs]` attribute</span></span>|
| <span data-ttu-id="8e341-138">Класс, где для `LayoutKind` задано значение `Sequential` или `Explicit`</span><span class="sxs-lookup"><span data-stu-id="8e341-138">A class with a `LayoutKind` of `Sequential` or `Explicit`</span></span> | <span data-ttu-id="8e341-139">Указатель на собственное представление класса</span><span class="sxs-lookup"><span data-stu-id="8e341-139">A pointer to the native representation of the class</span></span> | <span data-ttu-id="8e341-140">Собственное представление класса</span><span class="sxs-lookup"><span data-stu-id="8e341-140">The native representation of the class</span></span> |

<span data-ttu-id="8e341-141">В приведенной ниже таблице содержатся правила маршалинга, применяемые по умолчанию только для Windows.</span><span class="sxs-lookup"><span data-stu-id="8e341-141">The following table includes the default marshaling rules that are Windows-only.</span></span> <span data-ttu-id="8e341-142">На других платформах (не Windows) эти типы нельзя маршалировать.</span><span class="sxs-lookup"><span data-stu-id="8e341-142">On non-Windows platforms, you cannot marshal these types.</span></span>

| <span data-ttu-id="8e341-143">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="8e341-143">.NET Type</span></span> | <span data-ttu-id="8e341-144">Собственный тип (параметр)</span><span class="sxs-lookup"><span data-stu-id="8e341-144">Native Type (Parameter)</span></span> | <span data-ttu-id="8e341-145">Собственный тип (поле)</span><span class="sxs-lookup"><span data-stu-id="8e341-145">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| `object`  | `VARIANT`               | `IUnknown*`         |
| `System.Array` | <span data-ttu-id="8e341-146">Интерфейс COM</span><span class="sxs-lookup"><span data-stu-id="8e341-146">COM interface</span></span> | <span data-ttu-id="8e341-147">Нельзя использовать без атрибута `[MarshalAs]`</span><span class="sxs-lookup"><span data-stu-id="8e341-147">Not allowed without a `[MarshalAs]` attribute</span></span> |
| `System.ArgIterator` | `va_list` | <span data-ttu-id="8e341-148">Нельзя использовать</span><span class="sxs-lookup"><span data-stu-id="8e341-148">Not allowed</span></span> |
| `System.Collections.IEnumerator` | `IEnumVARIANT*` | <span data-ttu-id="8e341-149">Нельзя использовать</span><span class="sxs-lookup"><span data-stu-id="8e341-149">Not allowed</span></span> |
| `System.Collections.IEnumerable` | `IDispatch*` | <span data-ttu-id="8e341-150">Нельзя использовать</span><span class="sxs-lookup"><span data-stu-id="8e341-150">Not allowed</span></span> |
| `System.DateTimeOffset` | <span data-ttu-id="8e341-151">`int64_t` — число тактов начиная с полуночи 1 января 1601 года.</span><span class="sxs-lookup"><span data-stu-id="8e341-151">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> || <span data-ttu-id="8e341-152">`int64_t` — число тактов начиная с полуночи 1 января 1601 года.</span><span class="sxs-lookup"><span data-stu-id="8e341-152">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> |

<span data-ttu-id="8e341-153">Некоторые типы можно маршалировать только как параметры и нельзя — как поля.</span><span class="sxs-lookup"><span data-stu-id="8e341-153">Some types can only be marshaled as parameters and not as fields.</span></span> <span data-ttu-id="8e341-154">Эти типы перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="8e341-154">These types are listed in the following table:</span></span>

| <span data-ttu-id="8e341-155">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="8e341-155">.NET Type</span></span> | <span data-ttu-id="8e341-156">Собственный тип (только параметр)</span><span class="sxs-lookup"><span data-stu-id="8e341-156">Native Type (Parameter Only)</span></span> |
|-----------|------------------------------|
| `System.Text.StringBuilder` | <span data-ttu-id="8e341-157">Тип `char*` или `char16_t*` в зависимости от кодировки `CharSet` P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="8e341-157">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke.</span></span>  <span data-ttu-id="8e341-158">См. дополнительные сведения в [документации по кодировке](charset.md).</span><span class="sxs-lookup"><span data-stu-id="8e341-158">See the [charset documentation](charset.md).</span></span> |
| `System.ArgIterator` | <span data-ttu-id="8e341-159">`va_list` (только в Windows x86/x64/arm64)</span><span class="sxs-lookup"><span data-stu-id="8e341-159">`va_list` (on Windows x86/x64/arm64 only)</span></span> |
| `System.Runtime.InteropServices.ArrayWithOffset` | `void*` |
| `System.Runtime.InteropServices.HandleRef` | `void*` |

<span data-ttu-id="8e341-160">Если эти значения по умолчанию вам не подходят, вы можете настроить маршалинг параметров.</span><span class="sxs-lookup"><span data-stu-id="8e341-160">If these defaults don't do exactly what you want, you can customize how parameters are marshaled.</span></span> <span data-ttu-id="8e341-161">В статье о [маршалинге параметров](customize-parameter-marshaling.md) описана настройка маршалинга различных типов параметров.</span><span class="sxs-lookup"><span data-stu-id="8e341-161">The [parameter marshaling](customize-parameter-marshaling.md) article walks you through how to customize how different parameter types are marshaled.</span></span>

## <a name="default-marshaling-in-com-scenarios"></a><span data-ttu-id="8e341-162">Маршалинг в сценариях COM по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8e341-162">Default marshaling in COM scenarios</span></span>

<span data-ttu-id="8e341-163">При вызове методов в объектах COM в .NET среда выполнения .NET изменяет правила маршалинга по умолчанию в соответствии с общей семантикой COM.</span><span class="sxs-lookup"><span data-stu-id="8e341-163">When you are calling methods on COM objects in .NET, the .NET runtime changes the default marshaling rules to match common COM semantics.</span></span> <span data-ttu-id="8e341-164">В следующей таблице перечислены правила, которые среда выполнения .NET использует в сценариях COM:</span><span class="sxs-lookup"><span data-stu-id="8e341-164">The following table lists the rules that .NET runtimes uses in COM scenarios:</span></span>

| <span data-ttu-id="8e341-165">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="8e341-165">.NET Type</span></span> | <span data-ttu-id="8e341-166">Собственный тип (вызовы метода COM)</span><span class="sxs-lookup"><span data-stu-id="8e341-166">Native Type (COM method calls)</span></span> |
|-----------|--------------------------------|
| `bool`    | `VARIANT_BOOL`                 |
| `StringBuilder` | `LPWSTR`                 |
| `string`  | `BSTR`                         |
| <span data-ttu-id="8e341-167">Тип делегатов</span><span class="sxs-lookup"><span data-stu-id="8e341-167">Delegate types</span></span> | <span data-ttu-id="8e341-168">`_Delegate*` в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8e341-168">`_Delegate*` in .NET Framework.</span></span> <span data-ttu-id="8e341-169">Не разрешены в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8e341-169">Disallowed in .NET Core.</span></span> |
| `System.Drawing.Color` | `OLECOLOR`        |
| <span data-ttu-id="8e341-170">Массив .NET</span><span class="sxs-lookup"><span data-stu-id="8e341-170">.NET array</span></span> | `SAFEARRAY`                   |
| `string[]` | <span data-ttu-id="8e341-171">`SAFEARRAY` `BSTR`</span><span class="sxs-lookup"><span data-stu-id="8e341-171">`SAFEARRAY` of `BSTR`s</span></span>        |

## <a name="marshaling-classes-and-structs"></a><span data-ttu-id="8e341-172">Маршалинг классов и структур</span><span class="sxs-lookup"><span data-stu-id="8e341-172">Marshaling classes and structs</span></span>

<span data-ttu-id="8e341-173">Другим аспектом маршалинга типов является способ передачи структуры в неуправляемый метод.</span><span class="sxs-lookup"><span data-stu-id="8e341-173">Another aspect of type marshaling is how to pass in a struct to an unmanaged method.</span></span> <span data-ttu-id="8e341-174">Например, некоторые неуправляемые методы требуют указания структуры в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="8e341-174">For instance, some of the unmanaged methods require a struct as a parameter.</span></span> <span data-ttu-id="8e341-175">В таких случаях необходимо создать соответствующую структуру или соответствующий класс в управляемом коде и использовать в качестве параметра.</span><span class="sxs-lookup"><span data-stu-id="8e341-175">In these cases, you need to create a corresponding struct or a class in managed part of the world to use it as a parameter.</span></span> <span data-ttu-id="8e341-176">Но определить класс недостаточно. Нужно также указать маршалеру, как сопоставлять поля класса с неуправляемой структурой.</span><span class="sxs-lookup"><span data-stu-id="8e341-176">However, just defining the class isn't enough, you also need to instruct the marshaler how to map fields in the class to the unmanaged struct.</span></span> <span data-ttu-id="8e341-177">Здесь пригодится атрибут `StructLayout`.</span><span class="sxs-lookup"><span data-stu-id="8e341-177">Here the `StructLayout` attribute becomes useful.</span></span>

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

<span data-ttu-id="8e341-178">В приведенном выше примере представлен код вызова функции `GetSystemTime()`.</span><span class="sxs-lookup"><span data-stu-id="8e341-178">The previous code shows a simple example of calling into `GetSystemTime()` function.</span></span> <span data-ttu-id="8e341-179">Интерес представляет строка 4.</span><span class="sxs-lookup"><span data-stu-id="8e341-179">The interesting bit is on line 4.</span></span> <span data-ttu-id="8e341-180">Атрибут указывает, что поля класса должны последовательно сопоставляться со структурой на другой (неуправляемой) стороне.</span><span class="sxs-lookup"><span data-stu-id="8e341-180">The attribute specifies that the fields of the class should be mapped sequentially to the struct on the other (unmanaged) side.</span></span> <span data-ttu-id="8e341-181">Это означает, что имена полей не важны, важен только их порядок, так как он должен соответствовать неуправляемой структуре, которая показана в приведенном ниже примере:</span><span class="sxs-lookup"><span data-stu-id="8e341-181">This means that the naming of the fields isn't important, only their order is important, as it needs to correspond to the unmanaged struct, shown in the following example:</span></span>

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
} SYSTEMTIME, *PSYSTEMTIME;
```

<span data-ttu-id="8e341-182">Иногда маршалинг по умолчанию не решает задачу для вашей структуры.</span><span class="sxs-lookup"><span data-stu-id="8e341-182">Sometimes the default marshaling for your structure doesn't do what you need.</span></span> <span data-ttu-id="8e341-183">Дополнительные сведения см. в статье о [настройке маршалинга структур](./customize-struct-marshaling.md).</span><span class="sxs-lookup"><span data-stu-id="8e341-183">The [Customizing structure marshaling](./customize-struct-marshaling.md) article teaches you how to customize how your structure is marshaled.</span></span>
