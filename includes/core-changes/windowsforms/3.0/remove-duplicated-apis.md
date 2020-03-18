---
ms.openlocfilehash: e609b8006846cd202a6a7eeec2529cf1fbb09e7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937025"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a>Дублированные API удалены из Windows Forms

В .NET Core 3.0 RC1 были удалены некоторые API, которые случайно дублируются в пространстве имен <xref:System.Windows.Forms?displayProperty=fullName> начиная с версии .NET Core 3.0, предварительная версия 4.

#### <a name="change-description"></a>Описание изменений

В .NET Core 3.0, предварительная версия 4, случайно дублировались несколько типов в пространстве имен <xref:System.Windows.Forms?displayProperty=fullName>, которые уже существовали в пространстве имен <xref:System.ComponentModel.Design?displayProperty=fullName>. Начиная с .NET Core 3.0 RC1 эти дублирующиеся типы больше не доступны. В следующей таблице приводится список исходного типа и его повторяющегося типа:

> [!div class="mx-tdCol2BreakAll"]
> |Исходный тип|Повторяющийся тип|
> |---|---|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
> |<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
> |<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a>Представленная версия

3.0 RC1 (релиз-кандидат 1)

#### <a name="recommended-action"></a>Рекомендованное действие

Обновите код, чтобы он ссылался на исходный тип, как показано в столбце **Исходный тип**.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- Невозможно обнаружить с помощью анализа API.

<!--

### Affected APIs

- Not detectable via API analysis.

-->
