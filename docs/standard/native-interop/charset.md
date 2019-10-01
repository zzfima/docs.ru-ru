---
title: Кодировки и маршалинг — .NET
description: Узнайте, как различные значения кодировок влияют на то, как .NET маршалирует данные в машинный код.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 301fa3d8bd379e76a0e751c3a20d0d8be37d9ac0
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700927"
---
# <a name="charsets-and-marshaling"></a>Кодировки и маршалинг

Способ маршалирования значений `char`, объектов `string` и объектов `System.Text.StringBuilder` зависит от значения, заданного в поле `CharSet` P/Invoke или структуры. Для P/Invoke можно указать `CharSet`, задав в поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> при объявлении P/Invoke. Чтобы задать `CharSet` для типа, установите поле <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> в объявлении класса или структуры. Если эти поля атрибута не заданы, используемое значение `CharSet` определяется компилятором языка. В C# и Visual Basic по умолчанию используется кодировка <xref:System.Runtime.InteropServices.CharSet.Ansi>.

В следующей таблице показаны кодировки и способ представления символа или строки при маршалировании в этой кодировке.

| Значение`CharSet` | Windows            | .NET Core 2.2 и более ранние версии в Unix | .NET Core 3.0 и более поздние версии, Mono в Unix |
|-----------------|--------------------|-----------------------------------|------------------------------------------|
| Ansi            | `char` (системная [кодовая страница Windows (ANSI)](/windows/win32/intl/code-pages) по умолчанию)      | `char` (UTF-8)                    | `char` (UTF-8)                           |
| Юникод         | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char16_t` (UTF-16)                      |
| Авто            | `wchar_t` (UTF-16) | `char16_t` (UTF-16)               | `char` (UTF-8)                           |

Вы должны понимать, какое представление ожидает ваше собственное представление при выборе кодировки.
