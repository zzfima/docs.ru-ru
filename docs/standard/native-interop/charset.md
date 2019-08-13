---
title: Кодировки и маршалинг — .NET
description: Узнайте, как различные значения кодировок влияют на то, как .NET маршалирует данные в машинный код.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: cac71c5d09514dfe1244d16224944e05826edfa9
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817850"
---
# <a name="charsets-and-marshaling"></a>Кодировки и маршалинг

Способ маршалирования значений `char`, объектов `string` и объектов `System.Text.StringBuilder` зависит от значения, заданного в поле `CharSet` P/Invoke или структуры. Для P/Invoke можно указать `CharSet`, задав в поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> при объявлении P/Invoke. Чтобы указать `CharSet` для структуры, задайте <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> в поле объявления структуры. Если эти поля атрибута не заданы, используемое значение `CharSet` определяется компилятором языка. В C# и Visual Basic по умолчанию используется кодировка <xref:System.Runtime.InteropServices.CharSet.Ansi>.

В следующей таблице показаны кодировки и способ представления символа или строки при маршалировании в этой кодировке.

| Значение`CharSet` | Windows            | .NET Core 2.2 и более ранние версии в Unix | .NET Core 3.0 и более поздние версии, Mono в Unix |
|-----------------|--------------------|-----------------------------------|------------------------------------------|
| Ansi            | `char` (системная [кодовая страница Windows (ANSI)](/windows/win32/intl/code-pages) по умолчанию)      | `char` (UTF-8)                    | `char` (UTF-8)                           |
| Юникод         | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char16_t` (UTF-16)                      |
| Авто            | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char` (UTF-8)                           |

Вы должны понимать, какое представление ожидает ваше собственное представление при выборе кодировки.
