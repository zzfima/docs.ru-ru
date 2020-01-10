---
title: Настройка маршалинга структур — .NET
description: Из этой статьи вы узнаете, как настроить способ, с помощью которого .NET маршалирует ваши структуры в собственное представление.
ms.date: 01/18/2019
dev_langs:
- csharp
- cpp
ms.openlocfilehash: e69746e03cefa2444d4c34b582730824ff357858
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706352"
---
# <a name="customizing-structure-marshaling"></a><span data-ttu-id="22acd-103">Настройка маршалинга структур</span><span class="sxs-lookup"><span data-stu-id="22acd-103">Customizing structure marshaling</span></span>

<span data-ttu-id="22acd-104">Иногда стандартные правила маршалинга структур не совсем подходят.</span><span class="sxs-lookup"><span data-stu-id="22acd-104">Sometimes the default marshaling rules for structures aren't exactly what you need.</span></span> <span data-ttu-id="22acd-105">В средах выполнения .NET предусмотрены точки расширения, которые позволяют настроить макет структуры и способ маршалинга полей.</span><span class="sxs-lookup"><span data-stu-id="22acd-105">The .NET runtimes provide a few extension points for you to customize your structure's layout and how fields are marshaled.</span></span>

## <a name="customizing-structure-layout"></a><span data-ttu-id="22acd-106">Настройка макета структуры</span><span class="sxs-lookup"><span data-stu-id="22acd-106">Customizing structure layout</span></span>

<span data-ttu-id="22acd-107">На платформе .NET предусмотрен атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType> и перечисление <xref:System.Runtime.InteropServices.LayoutKind?displayProperty=nameWithType>, которые позволяют настроить способ размещения полей в памяти.</span><span class="sxs-lookup"><span data-stu-id="22acd-107">.NET provides the <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType> attribute and the <xref:System.Runtime.InteropServices.LayoutKind?displayProperty=nameWithType> enumeration to allow you to customize how fields are placed in memory.</span></span> <span data-ttu-id="22acd-108">Следуйте указаниям ниже, чтобы избежать распространенных проблем.</span><span class="sxs-lookup"><span data-stu-id="22acd-108">The following guidance will help you avoid common issues.</span></span>

<span data-ttu-id="22acd-109">**✔️ ДОПУСТИМО** использовать `LayoutKind.Sequential` во всех возможных случаях.</span><span class="sxs-lookup"><span data-stu-id="22acd-109">**✔️ CONSIDER** using `LayoutKind.Sequential` whenever possible.</span></span>

<span data-ttu-id="22acd-110">**✔️ РЕКОМЕНДУЕТСЯ** использовать `LayoutKind.Explicit` для маршалинга только в тех случаях, когда ваша собственная структура также имеет явный макет, например объединение.</span><span class="sxs-lookup"><span data-stu-id="22acd-110">**✔️ DO** only use `LayoutKind.Explicit` in marshaling when your native struct is also has an explicit layout, such as a union.</span></span>

<span data-ttu-id="22acd-111">**❌ избегать** использования `LayoutKind.Explicit` при упаковке структур на платформах, отличных от Windows, если необходимо выполнять целевые среды выполнения до .net Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="22acd-111">**❌ AVOID** using `LayoutKind.Explicit` when marshaling structures on non-Windows platforms if you need to target runtimes before .NET Core 3.0.</span></span> <span data-ttu-id="22acd-112">Среда выполнения .NET Core до 3,0 не поддерживает передачу явных структур по значению в собственные функции в системах на основе Intel или AMD 64-разрядных систем, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="22acd-112">The .NET Core runtime before 3.0 doesn't support passing explicit structures by value to native functions on Intel or AMD 64-bit non-Windows systems.</span></span> <span data-ttu-id="22acd-113">Но она поддерживает передачу явных структур по ссылке на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="22acd-113">However, the runtime supports passing explicit structures by reference on all platforms.</span></span>

## <a name="customizing-boolean-field-marshaling"></a><span data-ttu-id="22acd-114">Настройка маршалинга логических полей</span><span class="sxs-lookup"><span data-stu-id="22acd-114">Customizing boolean field marshaling</span></span>

<span data-ttu-id="22acd-115">Машинный код имеет множество различных логических представлений.</span><span class="sxs-lookup"><span data-stu-id="22acd-115">Native code has many different boolean representations.</span></span> <span data-ttu-id="22acd-116">Только в системе Windows есть три способа представления логических значений.</span><span class="sxs-lookup"><span data-stu-id="22acd-116">On Windows alone, there are three ways to represent boolean values.</span></span> <span data-ttu-id="22acd-117">Среде выполнения не известно собственное определение вашей структуры, поэтому она пытается подобрать наиболее подходящий способ маршалинга ваших логических значений.</span><span class="sxs-lookup"><span data-stu-id="22acd-117">The runtime doesn't know the native definition of your structure, so the best it can do is make a guess on how to marshal your boolean values.</span></span> <span data-ttu-id="22acd-118">В среде выполнения .NET можно указать, как маршалировать логические поля.</span><span class="sxs-lookup"><span data-stu-id="22acd-118">The .NET runtime provides a way to indicate how to marshal your boolean field.</span></span> <span data-ttu-id="22acd-119">В примере ниже показано, как маршалировать значение .NET `bool` в другие типы собственных логических значений.</span><span class="sxs-lookup"><span data-stu-id="22acd-119">The following examples show how to marshal .NET `bool` to different native boolean types.</span></span>

<span data-ttu-id="22acd-120">По умолчанию логические значения маршалируются как собственное 4-байтное значение Win32 [`BOOL`](/windows/desktop/winprog/windows-data-types#BOOL), как показано в примере ниже:</span><span class="sxs-lookup"><span data-stu-id="22acd-120">Boolean values default to marshaling as a native 4-byte Win32 [`BOOL`](/windows/desktop/winprog/windows-data-types#BOOL) value as shown in the following example:</span></span>

```csharp
public struct WinBool
{
    public bool b;
}
```

```cpp
struct WinBool
{
    public BOOL b;
};
```

<span data-ttu-id="22acd-121">Если необходимо передать явную структуру, можно использовать значение <xref:System.Runtime.InteropServices.UnmanagedType.Bool?displayProperty=nameWithType>, чтобы получить описанное выше поведение:</span><span class="sxs-lookup"><span data-stu-id="22acd-121">If you want to be explicit, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.Bool?displayProperty=nameWithType> value to get the same behavior as above:</span></span>

```csharp
public struct WinBool
{
    [MarshalAs(UnmanagedType.Bool)]
    public bool b;
}
```

```cpp
struct WinBool
{
    public BOOL b;
};
```

<span data-ttu-id="22acd-122">Если использовать значение `UnmanagedType.U1` или `UnmanagedType.I1` ниже, среда выполнения сможет маршалировать поле `b` как 1-байтный собственный тип `bool`.</span><span class="sxs-lookup"><span data-stu-id="22acd-122">Using the `UnmanagedType.U1` or `UnmanagedType.I1` values below, you can tell the runtime to marshal the `b` field as a 1-byte native `bool` type.</span></span>

```csharp
public struct CBool
{
    [MarshalAs(UnmanagedType.U1)]
    public bool b;
}
```

```cpp
struct CBool
{
    public bool b;
};
```

<span data-ttu-id="22acd-123">В системе Windows можно выбрать значение <xref:System.Runtime.InteropServices.UnmanagedType.VariantBool?displayProperty=nameWithType>, чтобы среда выполнения маршалировала ваше логическое значение в 2-байтное значение `VARIANT_BOOL`:</span><span class="sxs-lookup"><span data-stu-id="22acd-123">On Windows, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.VariantBool?displayProperty=nameWithType> value to tell the runtime to marshal your boolean value to a 2-byte `VARIANT_BOOL` value:</span></span>

```csharp
public struct VariantBool
{
    [MarshalAs(UnmanagedType.VariantBool)]
    public bool b;
}
```

```cpp
struct VariantBool
{
    public VARIANT_BOOL b;
};
```

> [!NOTE]
> <span data-ttu-id="22acd-124">Значение `VARIANT_BOOL` отличается от большинства типов логических значений в `VARIANT_TRUE = -1` и `VARIANT_FALSE = 0`.</span><span class="sxs-lookup"><span data-stu-id="22acd-124">`VARIANT_BOOL` is different than most bool types in that `VARIANT_TRUE = -1` and `VARIANT_FALSE = 0`.</span></span> <span data-ttu-id="22acd-125">Кроме того, все значения, которые не равны `VARIANT_TRUE`, считаются ложными.</span><span class="sxs-lookup"><span data-stu-id="22acd-125">Additionally, all values that aren't equal to `VARIANT_TRUE` are considered false.</span></span>

## <a name="customizing-array-field-marshaling"></a><span data-ttu-id="22acd-126">Настройка маршалинга полей массивов</span><span class="sxs-lookup"><span data-stu-id="22acd-126">Customizing array field marshaling</span></span>

<span data-ttu-id="22acd-127">На платформе .NET также предусмотрено несколько способов настройки маршалинга массивов.</span><span class="sxs-lookup"><span data-stu-id="22acd-127">.NET also includes a few ways to customize array marshaling.</span></span>

<span data-ttu-id="22acd-128">По умолчанию .NET маршалирует массивы как указатель на непрерывный список элементов:</span><span class="sxs-lookup"><span data-stu-id="22acd-128">By default, .NET marshals arrays as a pointer to a contiguous list of the elements:</span></span>

```csharp
public struct DefaultArray
{
    public int[] values;
}
```

```cpp
struct DefaultArray
{
    int* values;
};
```

<span data-ttu-id="22acd-129">Если вы взаимодействуете с API COM, возможно, понадобится маршалировать массивы как объекты `SAFEARRAY*`.</span><span class="sxs-lookup"><span data-stu-id="22acd-129">If you're interfacing with COM APIs, you may have to marshal arrays as `SAFEARRAY*` objects.</span></span> <span data-ttu-id="22acd-130">Можно использовать значения <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> и <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>, чтобы среда выполнения маршалировала массив как `SAFEARRAY*`:</span><span class="sxs-lookup"><span data-stu-id="22acd-130">You can use the <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> and the <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType> value to tell the runtime to marshal an array as a `SAFEARRAY*`:</span></span>

```csharp
public struct SafeArrayExample
{
    [MarshalAs(UnmanagedType.SafeArray)]
    public int[] values;
}
```

```cpp
struct SafeArrayExample
{
    SAFEARRAY* values;
};
```

<span data-ttu-id="22acd-131">Если нужно настроить тип элемента для `SAFEARRAY`, можно использовать поля <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> и <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> для настройки точного типа элемента `SAFEARRAY`.</span><span class="sxs-lookup"><span data-stu-id="22acd-131">If you need to customize what type of element is in the `SAFEARRAY`, then you can use the <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> fields to customize the exact element type of the `SAFEARRAY`.</span></span>

<span data-ttu-id="22acd-132">Если необходимо маршалировать объект на месте, можно использовать для этого значение <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="22acd-132">If you need to marshal the array in-place, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType> value to tell the marshaler to marshal the array in-place.</span></span> <span data-ttu-id="22acd-133">При применении такого маршалинга также необходимо указать в поле <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> количество элементов в массиве, чтобы среда выполнения могла правильно выделить место для структуры.</span><span class="sxs-lookup"><span data-stu-id="22acd-133">When you're using this marshaling, you also must supply a value to the <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> field  for the number of elements in the array so the runtime can correctly allocate space for the structure.</span></span>

```csharp
public struct InPlaceArray
{
    [MarshalAs(UnmanagedType.ByValArray, SizeConst = 4)]
    public int[] values;
}
```

```cpp
struct InPlaceArray
{
    int values[4];
};
```

> [!NOTE]
> <span data-ttu-id="22acd-134">.NET не поддерживает маршалинг поля массива переменной длины как элемента гибкого массива C99.</span><span class="sxs-lookup"><span data-stu-id="22acd-134">.NET doesn't support marshaling a variable length array field as a C99 Flexible Array Member.</span></span>

## <a name="customizing-string-field-marshaling"></a><span data-ttu-id="22acd-135">Настройка маршалинга полей строки</span><span class="sxs-lookup"><span data-stu-id="22acd-135">Customizing string field marshaling</span></span>

<span data-ttu-id="22acd-136">В .NET также предусмотрены разнообразные варианты настроек для маршалинга полей строки.</span><span class="sxs-lookup"><span data-stu-id="22acd-136">.NET also provides a wide variety of customizations for marshaling string fields.</span></span>

<span data-ttu-id="22acd-137">По умолчанию .NET маршалирует строку как указатель на строку, которая оканчивается значением NULL.</span><span class="sxs-lookup"><span data-stu-id="22acd-137">By default, .NET marshals a string as a pointer to a null-terminated string.</span></span> <span data-ttu-id="22acd-138">Кодирование зависит от значения поля <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> в атрибуте <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="22acd-138">The encoding depends on the value of the <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> field in the <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="22acd-139">Если атрибут не указан, по умолчанию используется кодирование ANSI.</span><span class="sxs-lookup"><span data-stu-id="22acd-139">If no attribute is specified, the encoding defaults to an ANSI encoding.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
public struct DefaultString
{
    public string str;
}
```

```cpp
struct DefaultString
{
    char* str;
};
```

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct DefaultString
{
    public string str;
}
```

```cpp
struct DefaultString
{
    char16_t* str; // Could also be wchar_t* on Windows.
};
```

<span data-ttu-id="22acd-140">Если нужно использовать разные кодировки для разных полей или более явное определение структуры, можно указать значение <xref:System.Runtime.InteropServices.UnmanagedType.LPStr?displayProperty=nameWithType> или <xref:System.Runtime.InteropServices.UnmanagedType.LPWStr?displayProperty=nameWithType> в атрибуте <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="22acd-140">If you need to use different encodings for different fields or just prefer to be more explicit in your struct definition, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.LPStr?displayProperty=nameWithType> or <xref:System.Runtime.InteropServices.UnmanagedType.LPWStr?displayProperty=nameWithType> values on a <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> attribute.</span></span>

```csharp
public struct AnsiString
{
    [MarshalAs(UnmanagedType.LPStr)]
    public string str;
}
```

```cpp
struct AnsiString
{
    char* str;
};
```

```csharp
public struct UnicodeString
{
    [MarshalAs(UnmanagedType.LPWStr)]
    public string str;
}
```

```cpp
struct UnicodeString
{
    char16_t* str; // Could also be wchar_t* on Windows.
};
```

<span data-ttu-id="22acd-141">Чтобы маршалировать строки с кодированием UTF-8, можно использовать значение <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> в атрибуте <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span><span class="sxs-lookup"><span data-stu-id="22acd-141">If you want to marshal your strings using the UTF-8 encoding, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> value in your <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>

```csharp
public struct UTF8String
{
    [MarshalAs(UnmanagedType.LPUTF8Str)]
    public string str;
}
```

```cpp
struct UTF8String
{
    char* str;
};
```

> [!NOTE]
> <span data-ttu-id="22acd-142">Значение <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> доступно только на платформе .NET Framework 4.7 (или более поздних версий) или .NET Core 1.1 (или более поздних версий).</span><span class="sxs-lookup"><span data-stu-id="22acd-142">Using <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> requires either .NET Framework 4.7 (or later versions) or .NET Core 1.1 (or later versions).</span></span> <span data-ttu-id="22acd-143">Оно недоступно на платформе .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="22acd-143">It isn't available in .NET Standard 2.0.</span></span>

<span data-ttu-id="22acd-144">Если вы работаете с API COM, возможно, вам потребуется маршалировать строку как `BSTR`.</span><span class="sxs-lookup"><span data-stu-id="22acd-144">If you're working with COM APIs, you may need to marshal a string as a `BSTR`.</span></span> <span data-ttu-id="22acd-145">Вы можете маршалировать строку как `BSTR`, используя значение <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="22acd-145">Using the <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType> value, you can marshal a string as a `BSTR`.</span></span>

```csharp
public struct BString
{
    [MarshalAs(UnmanagedType.BStr)]
    public string str;
}
```

```cpp
struct BString
{
    BSTR str;
};
```

<span data-ttu-id="22acd-146">Если используется API на базе WinRT, возможно, потребуется маршалировать строку как `HSTRING`.</span><span class="sxs-lookup"><span data-stu-id="22acd-146">When using a WinRT-based API, you may need to marshal a string as an `HSTRING`.</span></span>  <span data-ttu-id="22acd-147">Вы можете маршалировать строку как `HSTRING`, используя значение <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="22acd-147">Using the <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType> value, you can marshal a string as a `HSTRING`.</span></span>

```csharp
public struct HString
{
    [MarshalAs(UnmanagedType.HString)]
    public string str;
}
```

```cpp
struct BString
{
    HSTRING str;
};
```

<span data-ttu-id="22acd-148">Если API требует передавать строку на месте в структуре, можно использовать значение <xref:System.Runtime.InteropServices.UnmanagedType.ByValTStr?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="22acd-148">If your API requires you to pass the string in-place in the structure, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.ByValTStr?displayProperty=nameWithType> value.</span></span> <span data-ttu-id="22acd-149">Обратите внимание, что кодирование для строки, которую маршалирует значение `ByValTStr`, определяется атрибутом `CharSet`.</span><span class="sxs-lookup"><span data-stu-id="22acd-149">Do note that the encoding for a string marshaled by `ByValTStr` is determined from the `CharSet` attribute.</span></span> <span data-ttu-id="22acd-150">Кроме того, поле <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> должно передавать значение длины строки.</span><span class="sxs-lookup"><span data-stu-id="22acd-150">Additionally, it requires that a string length is passed by the <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> field.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
public struct DefaultString
{
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 4)]
    public string str;
}
```

```cpp
struct DefaultString
{
    char str[4];
};
```

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct DefaultString
{
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 4)]
    public string str;
}
```

```cpp
struct DefaultString
{
    char16_t str[4]; // Could also be wchar_t[4] on Windows.
};
```

## <a name="customizing-decimal-field-marshaling"></a><span data-ttu-id="22acd-151">Настройка маршалинга полей десятичных чисел</span><span class="sxs-lookup"><span data-stu-id="22acd-151">Customizing decimal field marshaling</span></span>

<span data-ttu-id="22acd-152">Если вы работаете в системе Windows, то некоторые API могут использовать собственную структуру [`CY` или `CURRENCY`](/windows/win32/api/wtypes/ns-wtypes-cy~r1).</span><span class="sxs-lookup"><span data-stu-id="22acd-152">If you're working on Windows, you might encounter some APIs that use the native [`CY` or `CURRENCY`](/windows/win32/api/wtypes/ns-wtypes-cy~r1) structure.</span></span> <span data-ttu-id="22acd-153">По умолчанию тип .NET `decimal` маршалируется в собственную структуру [`DECIMAL`](/windows/win32/api/wtypes/ns-wtypes-decimal~r1).</span><span class="sxs-lookup"><span data-stu-id="22acd-153">By default, the .NET `decimal` type marshals to the native [`DECIMAL`](/windows/win32/api/wtypes/ns-wtypes-decimal~r1) structure.</span></span> <span data-ttu-id="22acd-154">Но можно использовать атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> со значением <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=nameWithType>, чтобы маршалер преобразовывал значение `decimal` в собственное значение `CY`.</span><span class="sxs-lookup"><span data-stu-id="22acd-154">However, you can use a <xref:System.Runtime.InteropServices.MarshalAsAttribute> with the <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=nameWithType> value to instruct the marshaler to convert a `decimal` value to a native `CY` value.</span></span>

```csharp
public struct Currency
{
    [MarshalAs(UnmanagedType.Currency)]
    public decimal dec;
}
```

```cpp
struct Currency
{
    CY dec;
};
```

## <a name="marshaling-systemobjects"></a><span data-ttu-id="22acd-155">Маршалинг `System.Object`</span><span class="sxs-lookup"><span data-stu-id="22acd-155">Marshaling `System.Object`s</span></span>

<span data-ttu-id="22acd-156">В системе Windows можно маршалировать поля типа `object` в машинный код.</span><span class="sxs-lookup"><span data-stu-id="22acd-156">On Windows, you can marshal `object`-typed fields to native code.</span></span> <span data-ttu-id="22acd-157">Эти поля можно маршалировать в один из трех типов:</span><span class="sxs-lookup"><span data-stu-id="22acd-157">You can marshal these fields to one of three types:</span></span>

- [`VARIANT`](/windows/win32/api/oaidl/ns-oaidl-variant)
- [`IUnknown*`](/windows/desktop/api/unknwn/nn-unknwn-iunknown)
- [`IDispatch*`](/windows/desktop/api/oaidl/nn-oaidl-idispatch)

<span data-ttu-id="22acd-158">По умолчанию поля типа `object` маршалируются в тип `IUnknown*`, который создает оболочку объекта.</span><span class="sxs-lookup"><span data-stu-id="22acd-158">By default, an `object`-typed field will be marshaled to an `IUnknown*` that wraps the object.</span></span>

```csharp
public struct ObjectDefault
{
    public object obj;
}
```

```cpp
struct ObjectDefault
{
    IUnknown* obj;
};
```

<span data-ttu-id="22acd-159">Чтобы маршалировать поле объекта в тип `IDispatch*`, добавьте атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> со значением <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="22acd-159">If you want to marshal an object field to an `IDispatch*`, add a <xref:System.Runtime.InteropServices.MarshalAsAttribute> with the <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType> value.</span></span>

```csharp
public struct ObjectDispatch
{
    [MarshalAs(UnmanagedType.IDispatch)]
    public object obj;
}
```

```cpp
struct ObjectDispatch
{
    IDispatch* obj;
};
```

<span data-ttu-id="22acd-160">Чтобы маршалировать его как `VARIANT`, добавьте атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> со значением <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="22acd-160">If you want to marshal it as a `VARIANT`, add a <xref:System.Runtime.InteropServices.MarshalAsAttribute> with the <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> value.</span></span>

```csharp
public struct ObjectVariant
{
    [MarshalAs(UnmanagedType.Struct)]
    public object obj;
}
```

```cpp
struct ObjectVariant
{
    VARIANT obj;
};
```

<span data-ttu-id="22acd-161">В приведенной ниже таблице показано, как разные типы среды выполнения поля `obj` соотносятся с разными типами, которые сохраняются в `VARIANT`:</span><span class="sxs-lookup"><span data-stu-id="22acd-161">The following table describes how different runtime types of the `obj` field map to the various types stored in a `VARIANT`:</span></span>

| <span data-ttu-id="22acd-162">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="22acd-162">.NET Type</span></span> | <span data-ttu-id="22acd-163">Тип VARIANT</span><span class="sxs-lookup"><span data-stu-id="22acd-163">VARIANT Type</span></span> | | <span data-ttu-id="22acd-164">Тип .NET</span><span class="sxs-lookup"><span data-stu-id="22acd-164">.NET Type</span></span> | <span data-ttu-id="22acd-165">Тип VARIANT</span><span class="sxs-lookup"><span data-stu-id="22acd-165">VARIANT Type</span></span> |
|------------|--------------|-|----------|--------------|
|  `byte`  | `VT_UI1` |     | `System.Runtime.InteropServices.BStrWrapper` | `VT_BSTR` |
| `sbyte`  | `VT_I1`  |     | `object`  | `VT_DISPATCH` |
| `short`  | `VT_I2`  |     | `System.Runtime.InteropServices.UnknownWrapper` | `VT_UNKNOWN` |
| `ushort` | `VT_UI2` |     | `System.Runtime.InteropServices.DispatchWrapper` | `VT_DISPATCH` |
| `int`    | `VT_I4`  |     | `System.Reflection.Missing` | `VT_ERROR` |
| `uint`   | `VT_UI4` |     | `(object)null` | `VT_EMPTY` |
| `long`   | `VT_I8`  |     | `bool` | `VT_BOOL` |
| `ulong`  | `VT_UI8` |     | `System.DateTime` | `VT_DATE` |
| `float`  | `VT_R4`  |     | `decimal` | `VT_DECIMAL` |
| `double` | `VT_R8`  |     | `System.Runtime.InteropServices.CurrencyWrapper` | `VT_CURRENCY` |
| `char`   | `VT_UI2` |     | `System.DBNull` | `VT_NULL` |
| `string` | `VT_BSTR`|
