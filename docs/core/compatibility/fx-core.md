---
title: Критические изменения, миграция с .NET Framework на .NET Core
titleSuffix: ''
description: Список критических изменений, миграция с .NET Framework на .NET Core.
ms.date: 12/18/2019
ms.openlocfilehash: 407f99adf5d400fce659ef71cda32ceac1e54491
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093062"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a><span data-ttu-id="c736d-103">Критические изменения для миграции с .NET Framework на .NET Core</span><span class="sxs-lookup"><span data-stu-id="c736d-103">Breaking changes for migration from .NET Framework to .NET Core</span></span>

<span data-ttu-id="c736d-104">Если вы переносите приложение с .NET Framework на .NET Core, критические изменения, перечисленные в этой статье, могут повлиять на работу приложения.</span><span class="sxs-lookup"><span data-stu-id="c736d-104">If you're migrating an app from .NET Framework to .NET Core, the breaking changes listed in this article may affect you.</span></span> <span data-ttu-id="c736d-105">Критические изменения сгруппированы по категориям, а в этих категориях — по версии .NET Core, в которых они были представлены.</span><span class="sxs-lookup"><span data-stu-id="c736d-105">Breaking changes are grouped by category, and within those categories, by the version of .NET Core they were introduced in.</span></span>

> [!NOTE]
> <span data-ttu-id="c736d-106">Эта статья не является исчерпывающим списком критических изменений между .NET Framework и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c736d-106">This article is not a complete list of breaking changes between .NET Framework and .NET Core.</span></span> <span data-ttu-id="c736d-107">Здесь добавляются самые важные критические изменения, как только мы о них узнаем.</span><span class="sxs-lookup"><span data-stu-id="c736d-107">The most important breaking changes are added here as we become aware of them.</span></span>

## <a name="corefx"></a><span data-ttu-id="c736d-108">CoreFX</span><span class="sxs-lookup"><span data-stu-id="c736d-108">CoreFx</span></span>

- [<span data-ttu-id="c736d-109">Изменено значение по умолчанию для UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="c736d-109">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute)

### <a name="net-core-21"></a><span data-ttu-id="c736d-110">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c736d-110">.NET Core 2.1</span></span>

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

## <a name="windows-forms"></a><span data-ttu-id="c736d-111">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c736d-111">Windows Forms</span></span>

<span data-ttu-id="c736d-112">Поддержка Windows Forms была добавлена в .NET Core в версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="c736d-112">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="c736d-113">Если вы переносите приложение Windows Forms с .NET Framework на .NET Core, критические изменения, перечисленные здесь, могут повлиять на работу приложения.</span><span class="sxs-lookup"><span data-stu-id="c736d-113">If you're migrating a Windows Forms app from .NET Framework to .NET Core, the breaking changes listed here may affect your app.</span></span>

- [<span data-ttu-id="c736d-114">Удаленные элементы управления</span><span class="sxs-lookup"><span data-stu-id="c736d-114">Removed controls</span></span>](#removed-controls)
- [<span data-ttu-id="c736d-115">При отображении подсказки не возникает событие CellFormatting</span><span class="sxs-lookup"><span data-stu-id="c736d-115">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [<span data-ttu-id="c736d-116">Шрифт Control.DefaultFont изменен на Segoe UI 9 пт</span><span class="sxs-lookup"><span data-stu-id="c736d-116">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt)
- [<span data-ttu-id="c736d-117">Модернизация FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="c736d-117">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog)
- [<span data-ttu-id="c736d-118">Из некоторых типов Windows Forms удален атрибут SerializableAttribute</span><span class="sxs-lookup"><span data-stu-id="c736d-118">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types)
- [<span data-ttu-id="c736d-119">Параметр совместимости AllowUpdateChildControlIndexForTabControls не поддерживается</span><span class="sxs-lookup"><span data-stu-id="c736d-119">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [<span data-ttu-id="c736d-120">Параметр совместимости DomainUpDown.UseLegacyScrolling не поддерживается</span><span class="sxs-lookup"><span data-stu-id="c736d-120">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [<span data-ttu-id="c736d-121">Параметр совместимости DoNotLoadLatestRichEditControl не поддерживается</span><span class="sxs-lookup"><span data-stu-id="c736d-121">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [<span data-ttu-id="c736d-122">Параметр совместимости DoNotSupportSelectAllShortcutInMultilineTextBox не поддерживается</span><span class="sxs-lookup"><span data-stu-id="c736d-122">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [<span data-ttu-id="c736d-123">Параметр совместимости DontSupportReentrantFilterMessage не поддерживается</span><span class="sxs-lookup"><span data-stu-id="c736d-123">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [<span data-ttu-id="c736d-124">Параметр совместимости EnableVisualStyleValidation не поддерживается</span><span class="sxs-lookup"><span data-stu-id="c736d-124">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [<span data-ttu-id="c736d-125">Параметр совместимости UseLegacyContextMenuStripSourceControlValue не поддерживается</span><span class="sxs-lookup"><span data-stu-id="c736d-125">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [<span data-ttu-id="c736d-126">Параметр совместимости UseLegacyImages не поддерживается</span><span class="sxs-lookup"><span data-stu-id="c736d-126">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported)
- [<span data-ttu-id="c736d-127">Изменение доступа для AccessibleObject.RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="c736d-127">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem)
- [<span data-ttu-id="c736d-128">Из Windows Forms удалены дублирующиеся API</span><span class="sxs-lookup"><span data-stu-id="c736d-128">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms)

### <a name="net-core-31"></a><span data-ttu-id="c736d-129">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="c736d-129">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

### <a name="net-core-30"></a><span data-ttu-id="c736d-130">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c736d-130">.NET Core 3.0</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c736d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="c736d-131">See also</span></span>

- [<span data-ttu-id="c736d-132">API, которые всегда создают исключения в .NET Core</span><span class="sxs-lookup"><span data-stu-id="c736d-132">APIs that always throw exceptions on .NET Core</span></span>](unsupported-apis.md)
- [<span data-ttu-id="c736d-133">Технологии .NET Framework, недоступные в .NET Core</span><span class="sxs-lookup"><span data-stu-id="c736d-133">.NET Framework technologies unavailable on .NET Core</span></span>](../porting/net-framework-tech-unavailable.md)
