---
ms.openlocfilehash: 95a4c807f5c1077cf52f54b196e904ebc98c32f8
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116366"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft.VisualBasic.Constants.vbNewLine устарела

Начиная с .NET Core 3.0 (предварительная версия 8) константа <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> помечена как [\[устаревшая\]](xref:System.ObsoleteAttribute).

#### <a name="version-introduced"></a>Представленная версия

3.0 (предварительная версия 8)

#### <a name="change-description"></a>Описание изменений

Начиная с .NET Core 3.0 (предварительная версия 8), к константе <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> применяется атрибут [Obsolete](xref:System.ObsoleteAttribute). При использовании константы выдается предупреждение компилятора. В .NET Framework и предыдущих версиях .NET Core она не была помечена как устаревшая.

Это изменение было внесено для поддержки Visual Basic в качестве языка для разработки на нескольких платформах. Константа <xref:Microsoft.VisualBasic.Constants.vbNewLine> эквивалентна `\r\n`, последовательности символов новой строки в Windows. В системах на основе Unix символ новой строки — `\n`.

#### <a name="recommended-action"></a>Рекомендованное действие

Сообщение атрибута [Obsolete](xref:System.ObsoleteAttribute) для <xref:Microsoft.VisualBasic.Constants.vbNewLine> включает следующие рекомендации:

Для возврата каретки и перевода строки используйте <xref:Microsoft.VisualBasic.Constants.vbCrLf>. Для новой строки на текущей платформе используйте <xref:System.Environment.NewLine?displayProperty=nameWithType>.

#### <a name="category"></a>Категория

Visual Basic

#### <a name="affected-apis"></a>Затронутые API

- <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName>

<!--

### Affected APIs

- `F:Microsoft.VisualBasic.Constants.vbNewLine`

-->
