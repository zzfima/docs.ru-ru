---
title: Настройка маршалинга параметров — .NET
description: Из этой статьи вы узнаете, как настроить способ, с помощью которого .NET маршалирует ваши параметры в собственное представление.
ms.date: 01/18/2019
ms.openlocfilehash: ff646ad942cf051ce90cd75b24c8562e536182d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401163"
---
# <a name="customizing-parameter-marshaling"></a>Настройка маршалинга параметров

Если маршалинг параметров по умолчанию в среде выполнения .NET не отвечает вашим требованиям, можно настроить маршалинг параметров с помощью атрибута <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType>.

## <a name="customizing-string-parameters"></a>Настройка параметров строки

Среда выполнения .NET предусматривает различные форматы для маршалинга строк. Эти методы разбиты на две группы: строки в стиле C и форматы строк, ориентированные на Windows.

### <a name="c-style-strings"></a>Строки в стиле C

Каждый из этих форматов передает строку, которая оканчивается значением NULL, в машинный код. Они различаются кодировкой собственной строки.

| Значение `System.Runtime.InteropServices.UnmanagedType` | Кодирование |
|------------------------------------------------------|----------|
| LPStr | ANSI |
| LPUTF8Str | UTF-8 |
| LPWSTR | UTF-16 |
| LPTStr | UTF-16 |

Формат <xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=nameWithType> немного отличается. Как и `LPWStr`, он маршалирует строку в собственную строку в стиле C с кодировкой UTF-16. Но управляемая сигнатура требует передавать строку по ссылке, а соответствующая собственная сигнатура принимает строку по значению. Это различие позволяет использовать собственный API, который принимает строку по значению и меняет ее на месте без необходимости использования `StringBuilder`. Мы не рекомендуем использовать этот формат вручную, так как он может вызывать путаницу из-за несоответствия собственных и управляемых сигнатур.

### <a name="windows-centric-string-formats"></a>Форматы строк, ориентированные на Windows

Взаимодействуя с интерфейсами COM или OLE, вы, скорее всего, заметите, что собственные функции принимают строки как аргументы `BSTR`. Вы можете использовать неуправляемый тип <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType>, чтобы маршалировать строку как `BSTR`.

Если вы взаимодействуете с API WinRT, вы можете использовать формат <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType>, чтобы маршалировать строку как `HSTRING`.

## <a name="customizing-array-parameters"></a>Настройка параметров массива

В среде выполнения .NET можно маршалировать параметры массива несколькими способами. При вызове API, который принимает массив в стиле C, используйте неуправляемый тип <xref:System.Runtime.InteropServices.UnmanagedType.LPArray?displayProperty=nameWithType>. Если для значений в массиве необходимо настроить маршалинг, используйте для этого поле <xref:System.Runtime.InteropServices.MarshalAsAttribute.ArraySubType> в атрибуте `[MarshalAs]`.

Если вы используете API COM, вам, скорее всего, придется маршалировать свои параметры массивов как `SAFEARRAY*`. Для этого можно использовать неуправляемый тип <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>. Тип по умолчанию для элементов `SAFEARRAY` можно посмотреть в таблице с информацией по [настройке полей `object`](./customize-struct-marshaling.md#marshaling-systemobjects). Чтобы настроить точный тип элемента для `SAFEARRAY`, используйте поля <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> и <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType>.

## <a name="customizing-boolean-or-decimal-parameters"></a>Настройка параметров логических значений или десятичных чисел

Сведения о маршалинге параметров логических значений или десятичных чисел см. в статье [Customizing structure marshalling](customize-struct-marshaling.md) (Настройка маршалинга структуры).

## <a name="customizing-object-parameters-windows-only"></a>Настройка параметров объекта (только для Windows)

В системе Windows среда выполнения .NET предусматривает несколько способов маршалинга параметров объекта в машинный код.

### <a name="marshaling-as-specific-com-interfaces"></a>Маршалинг в виде конкретных интерфейсов COM

Если ваш API принимает указатель на COM-объект, вы можете использовать любой из следующих форматов `UnmanagedType` с параметром типа `object`, чтобы среда выполнения .NET выполняла маршалинг в виде этих конкретных интерфейсов:

- `IUnknown`
- `IDispatch`
- `IInspectable`

Кроме того, если тип обозначен как `[ComVisible(true)]` или маршалируется тип `object`, можно использовать формат <xref:System.Runtime.InteropServices.UnmanagedType.Interface?displayProperty=nameWithType>, чтобы маршалировать объект как вызываемую оболочку COM для просмотра типа из COM.

### <a name="marshaling-to-a-variant"></a>Маршалинг в `VARIANT`

Если ваш собственный API принимает `VARIANT` Win32, можно использовать формат <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> с параметром `object` для маршалинга объектов в виде `VARIANT`. Дополнительные сведения о сопоставлении типов NET и `VARIANT` см. в документации по [настройке полей `object`](customize-struct-marshaling.md#marshaling-systemobjects).

### <a name="custom-marshalers"></a>Пользовательские маршалеры

Если необходимо проецировать машинный интерфейс COM в другой управляемый тип, используйте формат `UnmanagedType.CustomMarshaler` и реализацию <xref:System.Runtime.InteropServices.ICustomMarshaler>, чтобы указать свой пользовательский код маршалинга.
