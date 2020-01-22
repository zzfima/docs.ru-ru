---
title: Критические изменения, миграция с .NET Framework на .NET Core
description: Список критических изменений, миграция с .NET Framework на .NET Core.
ms.date: 12/18/2019
ms.openlocfilehash: 6959bffab62cabc524062231db989de45c8c1498
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116493"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a>Критические изменения для миграции с .NET Framework на .NET Core

Если вы переносите приложение с .NET Framework на .NET Core, критические изменения, перечисленные в этой статье, могут повлиять на работу приложения. Критические изменения сгруппированы по категориям, а в этих категориях — по версии .NET Core, в которых они были представлены.

> [!NOTE]
> Эта статья не является исчерпывающим списком критических изменений между .NET Framework и .NET Core. Здесь добавляются самые важные критические изменения, как только мы о них узнаем.

## <a name="corefx"></a>CoreFX

- [Изменено значение по умолчанию для UseShellExecute](#change-in-default-value-of-useshellexecute)

### <a name="net-core-21"></a>.NET Core 2.1

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

## <a name="windows-forms"></a>Windows Forms

Поддержка Windows Forms была добавлена в .NET Core в версии 3.0. Если вы переносите приложение Windows Forms с .NET Framework на .NET Core, критические изменения, перечисленные здесь, могут повлиять на работу приложения.

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

### <a name="net-core-31"></a>.NET Core 3.1

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

### <a name="net-core-30"></a>.NET Core 3.0

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9 pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

[!INCLUDE[Change of access for AccessibleObject.RuntimeIDFirstItem](~/includes/core-changes/windowsforms/3.0/changed-access-for-runtimeidfirstitem.md)]

***

[!INCLUDE[Duplicated APIs removed from Windows Forms](~/includes/core-changes/windowsforms/3.0/remove-duplicated-apis.md)]

***

## <a name="see-also"></a>См. также

- [API, которые всегда создают исключения в .NET Core](unsupported-apis.md)
- [Технологии .NET Framework, недоступные в .NET Core](../porting/net-framework-tech-unavailable.md)
