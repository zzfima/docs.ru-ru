---
title: Настройка маршалинга структур — .NET
description: Из этой статьи вы узнаете, как настроить способ, с помощью которого .NET маршалирует ваши структуры в собственное представление.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
dev_langs:
- csharp
- cpp
ms.openlocfilehash: f4b8402413f4d2f558d8e61ad4f10490dece9835
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423995"
---
# <a name="customizing-structure-marshaling"></a>Настройка маршалинга структур

Иногда стандартные правила маршалинга структур не совсем подходят. В средах выполнения .NET предусмотрены точки расширения, которые позволяют настроить макет структуры и способ маршалинга полей.

## <a name="customizing-structure-layout"></a>Настройка макета структуры

На платформе .NET предусмотрен атрибут <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType> и перечисление <xref:System.Runtime.InteropServices.LayoutKind?displayProperty=nameWithType>, которые позволяют настроить способ размещения полей в памяти. Следуйте указаниям ниже, чтобы избежать распространенных проблем.

**✔️ ДОПУСТИМО** использовать `LayoutKind.Sequential` во всех возможных случаях.

**✔️ РЕКОМЕНДУЕТСЯ** использовать `LayoutKind.Explicit` для маршалинга только в тех случаях, когда ваша собственная структура также имеет явный макет, например объединение.

**❌ избегать** использования `LayoutKind.Explicit` при упаковке структур на платформах, отличных от Windows, если необходимо выполнять целевые среды выполнения до .net Core 3,0. Среда выполнения .NET Core до 3,0 не поддерживает передачу явных структур по значению в собственные функции в системах на основе Intel или AMD 64-разрядных систем, отличных от Windows. Но она поддерживает передачу явных структур по ссылке на всех платформах.

## <a name="customizing-boolean-field-marshaling"></a>Настройка маршалинга логических полей

Машинный код имеет множество различных логических представлений. Только в системе Windows есть три способа представления логических значений. Среде выполнения не известно собственное определение вашей структуры, поэтому она пытается подобрать наиболее подходящий способ маршалинга ваших логических значений. В среде выполнения .NET можно указать, как маршалировать логические поля. В примере ниже показано, как маршалировать значение .NET `bool` в другие типы собственных логических значений.

По умолчанию логические значения маршалируются как собственное 4-байтное значение Win32 [`BOOL`](/windows/desktop/winprog/windows-data-types#BOOL), как показано в примере ниже:

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

Если необходимо передать явную структуру, можно использовать значение <xref:System.Runtime.InteropServices.UnmanagedType.Bool?displayProperty=nameWithType>, чтобы получить описанное выше поведение:

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

Если использовать значение `UnmanagedType.U1` или `UnmanagedType.I1` ниже, среда выполнения сможет маршалировать поле `b` как 1-байтный собственный тип `bool`.

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

В системе Windows можно выбрать значение <xref:System.Runtime.InteropServices.UnmanagedType.VariantBool?displayProperty=nameWithType>, чтобы среда выполнения маршалировала ваше логическое значение в 2-байтное значение `VARIANT_BOOL`:

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
> Значение `VARIANT_BOOL` отличается от большинства типов логических значений в `VARIANT_TRUE = -1` и `VARIANT_FALSE = 0`. Кроме того, все значения, которые не равны `VARIANT_TRUE`, считаются ложными.

## <a name="customizing-array-field-marshaling"></a>Настройка маршалинга полей массивов

На платформе .NET также предусмотрено несколько способов настройки маршалинга массивов.

По умолчанию .NET маршалирует массивы как указатель на непрерывный список элементов:

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

Если вы взаимодействуете с API COM, возможно, понадобится маршалировать массивы как объекты `SAFEARRAY*`. Можно использовать значения <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> и <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>, чтобы среда выполнения маршалировала массив как `SAFEARRAY*`:

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

Если нужно настроить тип элемента для `SAFEARRAY`, можно использовать поля <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> и <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> для настройки точного типа элемента `SAFEARRAY`.

Если необходимо маршалировать объект на месте, можно использовать для этого значение <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>. При применении такого маршалинга также необходимо указать в поле <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> количество элементов в массиве, чтобы среда выполнения могла правильно выделить место для структуры.

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
> .NET не поддерживает маршалинг поля массива переменной длины как элемента гибкого массива C99.

## <a name="customizing-string-field-marshaling"></a>Настройка маршалинга полей строки

В .NET также предусмотрены разнообразные варианты настроек для маршалинга полей строки.

По умолчанию .NET маршалирует строку как указатель на строку, которая оканчивается значением NULL. Кодирование зависит от значения поля <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> в атрибуте <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType>. Если атрибут не указан, по умолчанию используется кодирование ANSI.

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

Если нужно использовать разные кодировки для разных полей или более явное определение структуры, можно указать значение <xref:System.Runtime.InteropServices.UnmanagedType.LPStr?displayProperty=nameWithType> или <xref:System.Runtime.InteropServices.UnmanagedType.LPWStr?displayProperty=nameWithType> в атрибуте <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType>.

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

Чтобы маршалировать строки с кодированием UTF-8, можно использовать значение <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> в атрибуте <xref:System.Runtime.InteropServices.MarshalAsAttribute>.

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
> Значение <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> доступно только на платформе .NET Framework 4.7 (или более поздних версий) или .NET Core 1.1 (или более поздних версий). Оно недоступно на платформе .NET Standard 2.0.

Если вы работаете с API COM, возможно, вам потребуется маршалировать строку как `BSTR`. Вы можете маршалировать строку как `BSTR`, используя значение <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType>.

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

Если используется API на базе WinRT, возможно, потребуется маршалировать строку как `HSTRING`.  Вы можете маршалировать строку как `HSTRING`, используя значение <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType>.

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

Если API требует передавать строку на месте в структуре, можно использовать значение <xref:System.Runtime.InteropServices.UnmanagedType.ByValTStr?displayProperty=nameWithType>. Обратите внимание, что кодирование для строки, которую маршалирует значение `ByValTStr`, определяется атрибутом `CharSet`. Кроме того, поле <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> должно передавать значение длины строки.

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

## <a name="customizing-decimal-field-marshaling"></a>Настройка маршалинга полей десятичных чисел

Если вы работаете в системе Windows, то некоторые API могут использовать собственную структуру [`CY` или `CURRENCY`](/windows/win32/api/wtypes/ns-wtypes-cy~r1). По умолчанию тип .NET `decimal` маршалируется в собственную структуру [`DECIMAL`](/windows/win32/api/wtypes/ns-wtypes-decimal~r1). Но можно использовать атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> со значением <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=nameWithType>, чтобы маршалер преобразовывал значение `decimal` в собственное значение `CY`.

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

## <a name="marshaling-systemobjects"></a>Маршалинг `System.Object`

В системе Windows можно маршалировать поля типа `object` в машинный код. Эти поля можно маршалировать в один из трех типов:

- [`VARIANT`](/windows/win32/api/oaidl/ns-oaidl-variant)
- [`IUnknown*`](/windows/desktop/api/unknwn/nn-unknwn-iunknown)
- [`IDispatch*`](/windows/desktop/api/oaidl/nn-oaidl-idispatch)

По умолчанию поля типа `object` маршалируются в тип `IUnknown*`, который создает оболочку объекта.

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

Чтобы маршалировать поле объекта в тип `IDispatch*`, добавьте атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> со значением <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>.

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

Чтобы маршалировать его как `VARIANT`, добавьте атрибут <xref:System.Runtime.InteropServices.MarshalAsAttribute> со значением <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType>.

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

В приведенной ниже таблице показано, как разные типы среды выполнения поля `obj` соотносятся с разными типами, которые сохраняются в `VARIANT`:

| Тип .NET | Тип VARIANT | | Тип .NET | Тип VARIANT |
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
