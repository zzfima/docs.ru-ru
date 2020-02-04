---
title: Критические изменения Windows Forms — .NET Core
description: Список критических изменений в Windows Forms для .NET Core.
ms.date: 01/08/2020
ms.openlocfilehash: 44bcde60f9e08d2e06a69c55e4ebe904bf5c449b
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116455"
---
# <a name="breaking-changes-in-windows-forms"></a>Критические изменения в Windows Forms

Поддержка Windows Forms была добавлена в .NET Core в версии 3.0. В этой статье перечислены критические изменения для Windows Forms, сгруппированные по версии .NET Core, в которой они появились. Если вы обновляете приложение Windows Forms с .NET Framework или с предыдущей версии .NET Core (3.0 или более поздней), эта статья для вас актуальна.

На этой странице описаны следующие критические изменения:

- [Удаленные элементы управления](#removed-controls)
- [При отображении подсказки не возникает событие CellFormatting](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [Шрифт Control.DefaultFont изменен на Segoe UI 9 пт](#default-control-font-changed-to-segoe-ui-9-pt)
- [Модернизация FolderBrowserDialog](#modernization-of-the-folderbrowserdialog)
- [Из некоторых типов Windows Forms удален атрибут SerializableAttribute](#serializableattribute-removed-from-some-windows-forms-types)
- [Параметр совместимости AllowUpdateChildControlIndexForTabControls не поддерживается](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [Параметр совместимости DomainUpDown.UseLegacyScrolling не поддерживается](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [Параметр совместимости DoNotLoadLatestRichEditControl не поддерживается](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [Параметр совместимости DoNotSupportSelectAllShortcutInMultilineTextBox не поддерживается](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [Параметр совместимости DontSupportReentrantFilterMessage не поддерживается](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [Параметр совместимости EnableVisualStyleValidation не поддерживается](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [Параметр совместимости UseLegacyContextMenuStripSourceControlValue не поддерживается](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [Параметр совместимости UseLegacyImages не поддерживается](#uselegacyimages-compatibility-switch-not-supported)
- [Изменение доступа для AccessibleObject.RuntimeIDFirstItem](#change-of-access-for-accessibleobjectruntimeidfirstitem)
- [Из Windows Forms удалены дублирующиеся API](#duplicated-apis-removed-from-windows-forms)

## <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

## <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

[!INCLUDE[Change of access for AccessibleObject.RuntimeIDFirstItem](~/includes/core-changes/windowsforms/3.0/changed-access-for-runtimeidfirstitem.md)]

***

[!INCLUDE[Duplicated APIs removed from Windows Forms](~/includes/core-changes/windowsforms/3.0/remove-duplicated-apis.md)]

***

## <a name="see-also"></a>См. также

- [Перенос приложения Windows Forms в .NET Core](../porting/winforms.md)
