---
ms.openlocfilehash: 07527c247e6ccd53d2a77793946ffc796c3e1cbb
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643919"
---
### <a name="switchsystemwindowsformsuselegacyimages-compatibility-switch-not-supported"></a>Параметр совместимости Switch.System.Windows.Forms.UseLegacyImages не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.UseLegacyImages`, появившийся в .NET Framework 4.8, не поддерживается в Windows Forms в .NET Core 3.0.

#### <a name="change-description"></a>Описание изменений

Начиная с .NET Framework 4.8, параметр совместимости `Switch.System.Windows.Forms.UseLegacyImages` устраняет возможные проблемы с масштабированием изображений в сценариях ClickOnce в средах с высоким DPI. Если задано значение `true`, параметр позволяет пользователю восстановить прежний способ масштабирования изображений при высоком уровне DPI, когда масштаб составляет более 100 %. Дополнительные сведения см. в [заметках о выпуске .NET Framework 4.8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) в GitHub.

В .NET Core параметр `Switch.System.Windows.Forms.UseLegacyImages` не поддерживается.

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
