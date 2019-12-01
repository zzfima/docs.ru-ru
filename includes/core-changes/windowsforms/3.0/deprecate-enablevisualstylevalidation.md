---
ms.openlocfilehash: 84b6bfc32f5a73597b227098e5aee1e3450cf85b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643901"
---
### <a name="switchsystemwindowsformsenablevisualstylevalidation-compatibility-switch-not-supported"></a>Параметр совместимости Switch.System.Windows.Forms.EnableVisualStyleValidation не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.EnableVisualStyleValidation` не поддерживается в Windows Forms в .NET Core 3.0.

#### <a name="change-description"></a>Описание изменений

В .NET Framework параметр совместимости `Switch.System.Windows.Forms.EnableVisualStyleValidation` позволял приложению отказаться от проверки визуальных стилей, предоставленных в числовой форме.

В .NET Core параметр `Switch.System.Windows.Forms.EnableVisualStyleValidation` не поддерживается.

#### <a name="version-introduced"></a>Представленная версия

3.0, предварительная версия 9

#### <a name="recommended-action"></a>Рекомендуемое действие

Удалите параметр. Он не поддерживается, и альтернативного варианта нет.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- Нет

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
