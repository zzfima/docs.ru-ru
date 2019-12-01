---
ms.openlocfilehash: 86cdb845c436f424bbcc70e0736568031143b204
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567406"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft.VisualBasic.Constants.vbNewLine устарела

Начиная с .NET Core 3.0 (предварительная версия 8), константа <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> помечена как [Obsolete](xref:System.ObsoleteAttribute).

#### <a name="version-introduced"></a>Представленная версия

3.0 (предварительная версия 8)

#### <a name="change-description"></a>Описание изменений

Начиная с .NET Core 3.0 (предварительная версия 8), к константе <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> применяется атрибут [Obsolete](xref:System.ObsoleteAttribute). При использовании константы выдается предупреждение компилятора. В предыдущих версиях .NET Core и .NET Framework она не была помечена как нерекомендуемая.

Это изменение было внесено для поддержки Visual Basic в качестве языка для разработки на нескольких платформах. Константа `vbNewLine` эквивалентна `\r\n`, последовательности символов новой строки в Windows. В системах на основе Unix символ новой строки — `\n`.

#### <a name="recommended-action"></a>Рекомендуемое действие

Сообщение атрибута [Obsolete](xref:System.ObsoleteAttribute) для `vbNewLine` включает следующие рекомендации:

> Для возврата каретки и перевода строки используйте [vbCrLf](xref:Microsoft.VisualBasic.Constants.vbCrLf). Для новой строки на текущей платформе используйте <xref:System.Environment.NewLine?displayProperty=nameWithType>.

#### <a name="category"></a>Категория

Visual Basic

#### <a name="affected-apis"></a>Затронутые API

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
