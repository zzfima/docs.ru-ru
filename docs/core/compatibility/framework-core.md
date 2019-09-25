---
title: Критические изменения, миграция с .NET Framework на .NET Core 3.0 — .NET Core
description: Список критических изменений для миграции с .NET Framework на .NET Core 3.0 для Windows Forms и Windows Presentation Foundation.
ms.date: 09/10/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c658c5bce7a2554bba83f2779a73d9d6af01a342
ms.sourcegitcommit: 3ac05b2c386c8cc5e73f4c7665f6c0a7ed3da1bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "71151534"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core-30"></a>Критические изменения для миграции с .NET Framework на .NET Core 3.0

> [!IMPORTANT]
> Эта статья находится на стадии разработки. Это не полный список критических изменений .NET Core. Дополнительные сведения о критических изменениях .NET Core см. в отдельных [вопросах](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) в репозитории dotnet/docs на GitHub. 

Если вы переносите приложение Windows Forms или Windows Presentation Foundation с .NET Framework на .NET Core 3.0, ознакомьтесь со следующими статьями о критических изменениях, которые могут повлиять на работу приложения.

## <a name="windows-forms"></a>Windows Forms

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacyimages.md)]
