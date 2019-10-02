---
ms.openlocfilehash: 5ef785f476b795a9c53e511d51b2683b99e6da05
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181967"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft.VisualBasic.Constants.vbNewLine устарела

Начиная с .NET Core 3.0 (предварительная версия 8), константа <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> помечена как [Obsolete](xref:System.ObsoleteAttribute).

#### <a name="version-introduced"></a>Представленная версия

.NET Core 3.0 (предварительная версия 8)

#### <a name="details"></a>Сведения

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

-- >

