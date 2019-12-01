---
ms.openlocfilehash: 5c1dc42a451d2c6a82e2c2429115db023c610334
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643907"
---
### <a name="switchsystemwindowsformsuselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported"></a>Параметр совместимости Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue`, появившийся в .NET Framework 4.7.2, не поддерживается в Windows Forms в .NET Core 3.0.

#### <a name="change-description"></a>Описание изменений

Начиная с версии .NET Framework 4.7.2, параметр совместимости `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` позволяет разработчикам отказаться от нового поведения свойства <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>, которое теперь возвращает ссылку на систему управления версиями. Ранее это свойство возвращало `null`. Дополнительные сведения см. в статье [Элемент \<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

В .NET Core параметр `Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue` не поддерживается.

#### <a name="version-introduced"></a>Представленная версия

3.0, предварительная версия 9

#### <a name="recommended-action"></a>Рекомендуемое действие

Удалите параметр. Он не поддерживается, и альтернативного варианта нет.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Forms.ContextMenuStrip.SourceControl?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `P:System.Windows.Forms.ContextMenuStrip.SourceControl`

-->
