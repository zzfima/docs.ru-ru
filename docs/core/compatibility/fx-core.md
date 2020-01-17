---
title: Критические изменения, миграция с .NET Framework на .NET Core
description: Список критических изменений, миграция с .NET Framework на .NET Core.
ms.date: 12/18/2019
ms.openlocfilehash: 5c29636664632e80e4235e922a3296c34fdbef36
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900124"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a><span data-ttu-id="d31f7-103">Критические изменения для миграции с .NET Framework на .NET Core</span><span class="sxs-lookup"><span data-stu-id="d31f7-103">Breaking changes for migration from .NET Framework to .NET Core</span></span>

<span data-ttu-id="d31f7-104">Если вы переносите приложение с .NET Framework на .NET Core, критические изменения, перечисленные в этой статье, могут повлиять на работу приложения.</span><span class="sxs-lookup"><span data-stu-id="d31f7-104">If you're migrating an app from .NET Framework to .NET Core, the breaking changes listed in this article may affect you.</span></span> <span data-ttu-id="d31f7-105">Критические изменения группируются по категориям.</span><span class="sxs-lookup"><span data-stu-id="d31f7-105">Breaking changes are grouped by category.</span></span>

> [!NOTE]
> <span data-ttu-id="d31f7-106">Эта статья не является исчерпывающим списком критических изменений между .NET Framework и .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d31f7-106">This article is not a complete list of breaking changes between .NET Framework and .NET Core.</span></span> <span data-ttu-id="d31f7-107">Здесь добавляются самые важные критические изменения, как только мы о них узнаем.</span><span class="sxs-lookup"><span data-stu-id="d31f7-107">The most important breaking changes are added here as we become aware of them.</span></span>

## <a name="corefx"></a><span data-ttu-id="d31f7-108">CoreFX</span><span class="sxs-lookup"><span data-stu-id="d31f7-108">CoreFx</span></span>

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

## <a name="windows-forms"></a><span data-ttu-id="d31f7-109">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d31f7-109">Windows Forms</span></span>

<span data-ttu-id="d31f7-110">Сведения о критических изменениях при переносе приложения Windows Forms из .NET Framework в .NET Core 3.0 или более поздней версии см. в разделе [Breaking changes in Windows Forms (.NET Framework to .NET Core)](../porting/winforms-breaking-changes.md) (Критические изменения в Windows Forms (из .NET Framework в .NET Core)).</span><span class="sxs-lookup"><span data-stu-id="d31f7-110">For information about breaking changes when you migrate a Windows Forms app from .NET Framework to .NET Core 3.0 or later, see [Breaking changes in Windows Forms (.NET Framework to .NET Core)](../porting/winforms-breaking-changes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d31f7-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d31f7-111">See also</span></span>

- [<span data-ttu-id="d31f7-112">API, которые всегда создают исключения в .NET Core</span><span class="sxs-lookup"><span data-stu-id="d31f7-112">APIs that always throw exceptions on .NET Core</span></span>](unsupported-apis.md)
- [<span data-ttu-id="d31f7-113">Технологии .NET Framework, недоступные в .NET Core</span><span class="sxs-lookup"><span data-stu-id="d31f7-113">.NET Framework technologies unavailable on .NET Core</span></span>](../porting/net-framework-tech-unavailable.md)
