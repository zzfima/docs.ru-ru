---
ms.openlocfilehash: 265fc5bea97bf85bcb9cc8111f915e14297d9957
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643877"
---
### <a name="switchsystemwindowsformsdonotloadlatestricheditcontrol-compatibility-switch-not-supported"></a>Параметр совместимости Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl не поддерживается

Параметр совместимости `Switch.System.Windows.Forms.UseLegacyImages`, появившийся в .NET Framework 4.7.1, не поддерживается в Windows Forms в .NET Core 3.0.

#### <a name="change-description"></a>Описание изменений

В .NET Framework 4.6.2 и предыдущих версиях элемент управления <xref:System.Windows.Forms.RichTextBox> создавал экземпляр элемента управления Win32 RichEdit версии 3.0, а для приложений, предназначенных для .NET Framework 4.7.1, элемент управления <xref:System.Windows.Forms.RichTextBox> создавал экземпляр элемента управления RichEdit версии 4.1 (в *msftedit.dll*). Параметр совместимости `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` был введен для того, чтобы в приложениях, предназначенных для .NET Framework 4.7.1 и более поздних версий, можно было отказаться от использования нового элемента управления RichEdit версии 4.1 и использовать вместо него прежнюю версию 3.

В .NET Core параметр `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` не поддерживается. Поддерживаются только новые версии элемента управления <xref:System.Windows.Forms.RichTextBox>.

#### <a name="version-introduced"></a>Представленная версия

3.0, предварительная версия 9

#### <a name="recommended-action"></a>Рекомендуемое действие

Удалите параметр. Он не поддерживается, и альтернативного варианта нет.

#### <a name="category"></a>Категория

Windows Forms

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
