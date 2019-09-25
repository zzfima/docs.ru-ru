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
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core-30"></a><span data-ttu-id="a867c-103">Критические изменения для миграции с .NET Framework на .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a867c-103">Breaking changes for migration from .NET Framework to .NET Core 3.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a867c-104">Эта статья находится на стадии разработки.</span><span class="sxs-lookup"><span data-stu-id="a867c-104">This article is under construction.</span></span> <span data-ttu-id="a867c-105">Это не полный список критических изменений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a867c-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="a867c-106">Дополнительные сведения о критических изменениях .NET Core см. в отдельных [вопросах](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) в репозитории dotnet/docs на GitHub.</span><span class="sxs-lookup"><span data-stu-id="a867c-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span> 

<span data-ttu-id="a867c-107">Если вы переносите приложение Windows Forms или Windows Presentation Foundation с .NET Framework на .NET Core 3.0, ознакомьтесь со следующими статьями о критических изменениях, которые могут повлиять на работу приложения.</span><span class="sxs-lookup"><span data-stu-id="a867c-107">If you are migrating a Windows Forms or Windows Presentation Foundation application from .NET Framework to .NET Core 3.0, review the following topics for breaking changes that may affect your app:</span></span>

## <a name="windows-forms"></a><span data-ttu-id="a867c-108">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a867c-108">Windows Forms</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9pt](~/includes/core-changes/windowsforms/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/deprecate-uselegacyimages.md)]
