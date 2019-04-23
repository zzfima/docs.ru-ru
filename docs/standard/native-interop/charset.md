---
title: Кодировки и маршалинг — .NET
description: Узнайте, как различные значения кодировок влияют на то, как .NET маршалирует данные в машинный код.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: f436bbbf435df07d242f9bf295b0264c4cfd5b3b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59480850"
---
# <a name="charsets-and-marshalling"></a>Кодировки и маршалинг

Способ маршалирования значений `char`, объектов `string` и объектов `System.Text.StringBuilder` зависит от значения, заданного в поле `CharSet` P/Invoke или структуры. Для P/Invoke можно указать `CharSet`, задав в поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> при объявлении P/Invoke. Чтобы указать `CharSet` для структуры, задайте <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> в поле объявления структуры. Если эти поля атрибута не заданы, используемое значение `CharSet` определяется компилятором языка. В C# и Visual Basic по умолчанию используется кодировка <xref:System.Runtime.InteropServices.CharSet.Ansi>.

В следующей таблице показаны кодировки и способ представления символа или строки при маршалировании в этой кодировке.

| CharSet | Windows            | UNIX на .NET Core 2.2 и более ранних версий | Mono и Unix на .NET Core 3.0 и более поздних версий |
|---------|--------------------|-----------------------------|------------------------------------------|
| Ansi    | `char` (ANSI)      | `char` (UTF-8)              | `char` (UTF-8)                           |
| Юникод | `wchar_t` (UTF-16) | `char16_t` (UTF-16)         | `char16_t` (UTF-16)                      |
| Авто    | `wchar_t` (UTF-16) | `char16_t` (UTF-16)         | `char` (UTF-8)                           |

Вы должны понимать, какое представление ожидает ваше собственное представление при выборе кодировки.
