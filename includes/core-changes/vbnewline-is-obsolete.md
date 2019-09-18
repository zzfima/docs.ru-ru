---
ms.openlocfilehash: 2a0ebcf61fd96df6d2235962c1f1e9cac3fb22e6
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988502"
---
### <a name="microsoftvisualbasicconstantsvbnewline-is-obsolete"></a>Microsoft.VisualBasic.Constants.vbNewLine устарела

Константа <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> помечена как [Obsolete](xref:System.ObsoleteAttribute) (Устаревшая) в .NET Framework, но ранее соответствующий атрибут отсутствовал в библиотеке .NET Core 3.0.

#### <a name="version-introduced"></a>Представленная версия

.NET Core 3.0 (предварительная версия 8)

#### <a name="details"></a>Подробные сведения

Начиная с .NET Core 3.0 (предварительная версия 8) атрибут [Obsolete](xref:System.ObsoleteAttribute) был применен к константе <xref:Microsoft.VisualBasic.Constants.vbNewLine?displayProperty=fullName> для обеспечения соответствия `vbNewLine` в .NET Framework. При использовании константы `vbNewLine` выдается предупреждение компилятора. 

В предыдущих версиях .NET Core `vbNewLine` не вызывает предупреждение компилятора.

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

