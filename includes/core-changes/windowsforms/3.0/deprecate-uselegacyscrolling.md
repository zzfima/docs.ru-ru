---
ms.openlocfilehash: 459e7e1f0b5543f069682dadf60668e94b472377
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643865"
---
### <a name="switchsystemwindowsformsdomainupdownuselegacyscrolling-compatibility-switch-not-supported"></a>Параметр совместимости Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling`, появившийся в .NET Framework 4.7.1, не поддерживается в Windows Forms в .NET Core 3.0.

#### <a name="change-description"></a>Описание изменений

Начиная с версии .NET Framework 4.7.1, параметр совместимости `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` позволял разработчикам отказаться от независимых действий <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> и <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>. Параметр восстанавливал прежнее поведение, при котором действие <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> игнорируется, если присутствует текст контекста, и разработчику необходимо использовать действие <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> для элемента управления перед использованием действия <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>. Дополнительные сведения см. в статье [Элемент \<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

В .NET Core параметр `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` не поддерживается.

#### <a name="version-introduced"></a>Представленная версия

3.0, предварительная версия 9

#### <a name="recommended-action"></a>Рекомендуемое действие

Удалите параметр. Он не поддерживается, и альтернативного варианта нет.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.DomainUpDown.DownButton`
- `M:System.Windows.Forms.DomainUpDown.UpButton`

-->
