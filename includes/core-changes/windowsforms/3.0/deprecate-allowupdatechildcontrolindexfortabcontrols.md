---
ms.openlocfilehash: 1d01de4b978309e05a6036953f2a6909628a2480
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643889"
---
### <a name="switchsystemwindowsformsallowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a>Параметр совместимости Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` поддерживается в Windows Forms в .NET Framework 4.6 и более поздних версиях, но не поддерживается в Windows Forms, начиная с версии .NET Core 3.0.

#### <a name="change-description"></a>Описание изменений

В .NET Framework 4.6 и более поздних версиях при выборе вкладки ее коллекция элементов управления переупорядочивается. Параметр совместимости `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` позволяет приложению отменить переупорядочивание, если оно не требуется.

В .NET Core параметр `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` не поддерживается.

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
