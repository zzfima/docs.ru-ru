---
title: Кодировки и маршалинг — .NET
description: Узнайте, как различные значения кодировок влияют на то, как .NET маршалирует данные в машинный код.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 2ff6c485906db481cb5236f83e885ba9fd46450b
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "56411410"
---
# <a name="charsets-and-marshalling"></a>Кодировки и маршалинг

Способ маршалирования значений `char`, объектов `string` и объектов `System.Text.StringBuilder` зависит от значения, заданного в поле `CharSet` P/Invoke или структуры. Для P/Invoke можно указать `CharSet`, задав в поле <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> при объявлении P/Invoke. Чтобы указать `CharSet` для структуры, задайте <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> в поле объявления структуры. Если эти поля атрибута не заданы, используемое значение `CharSet` определяется компилятором языка. В C# по умолчанию используется кодировка <xref:System.Runtime.InteropServices.CharSet.Ansi>.

В следующей таблице показаны кодировки и способ представления символа или строки при маршалировании в этой кодировке.

| CharSet | Windows | Unix | Mono в Unix |
|---------|---------|-------|-------|
| Ansi    | `char` (ANSI)  | `char` (ANSI в macOS, UTF-8 в Linux) | `char` (UTF-8) |
| Юникод | `wchar_t` (UTF-16) | `char16_t` (UTF-16) | `char16_t` (UTF-16) |
| Авто | `wchar_t` (UTF-16) | `char16_t` (UTF-16) | `char` (UTF-8) |

Вы должны понимать, какое представление ожидает ваше собственное представление при выборе кодировки.
