---
title: Кодировки и маршалинг — .NET
description: Узнайте, как различные значения кодировок влияют на то, как .NET маршалирует данные в машинный код.
ms.date: 01/18/2019
ms.openlocfilehash: 4be4bd5a968eb5c0d6959a0f378ee1223ed906ed
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706391"
---
# <a name="charsets-and-marshaling"></a>Кодировки и маршалинг

Способ маршалирования значений `char`, объектов `string` и объектов `System.Text.StringBuilder` зависит от значения, заданного в поле `CharSet` P/Invoke или структуры. Для P/Invoke можно указать `CharSet`, задав в поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> при объявлении P/Invoke. Чтобы задать `CharSet` для типа, установите поле <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> в объявлении класса или структуры. Если эти поля атрибута не заданы, используемое значение `CharSet` определяется компилятором языка. C#и Visual Basic по умолчанию использовать <xref:System.Runtime.InteropServices.CharSet.Ansi> charset.

В следующей таблице показаны кодировки и способ представления символа или строки при маршалировании в этой кодировке.

| Значение`CharSet` | Портал            | .NET Core 2.2 и более ранние версии в Unix | .NET Core 3.0 и более поздние версии, Mono в Unix |
|-----------------|--------------------|-----------------------------------|------------------------------------------|
| Ansi            | `char` (системная [кодовая страница Windows (ANSI)](/windows/win32/intl/code-pages) по умолчанию)      | `char` (UTF-8)                    | `char` (UTF-8)                           |
| Unicode         | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char16_t` (UTF-16)                      |
| Авто            | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char` (UTF-8)                           |

Вы должны понимать, какое представление ожидает ваше собственное представление при выборе кодировки.
