---
ms.openlocfilehash: 7e76c32ddeb50eaf1ee93d7cf3cac7469187cc41
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937001"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a>Параметр совместимости AllowUpdateChildControlIndexForTabControls не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` поддерживается в Windows Forms в .NET Framework 4.6 и более поздних версиях, но не поддерживается в Windows Forms, начиная с версии .NET Core 3.0.

#### <a name="change-description"></a>Описание изменений

В .NET Framework 4.6 и более поздних версиях при выборе вкладки ее коллекция элементов управления переупорядочивается. Параметр совместимости `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` позволяет приложению отменить переупорядочивание, если оно не требуется.

В .NET Core параметр `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` не поддерживается.

#### <a name="version-introduced"></a>Представленная версия

3.0, предварительная версия 9

#### <a name="recommended-action"></a>Рекомендованное действие

Удалите параметр. Он не поддерживается, и альтернативного варианта нет.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- Отсутствуют

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
