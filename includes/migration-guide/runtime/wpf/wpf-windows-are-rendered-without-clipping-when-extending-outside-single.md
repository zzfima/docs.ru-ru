---
ms.openlocfilehash: 3b7309347c643d89a28331c6ef3cac36085a969a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858538"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="eabee-101">Окна WPF отображаются без обрезки, если изображение выходит за пределы одного монитора</span><span class="sxs-lookup"><span data-stu-id="eabee-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

|   |   |
|---|---|
|<span data-ttu-id="eabee-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="eabee-102">Details</span></span>|<span data-ttu-id="eabee-103">В .NET Framework 4.6 на компьютере под управлением Windows 8 и более поздних версий все содержимое окна выводится без обрезки, если изображение выходит за пределы одного экрана при использовании нескольких мониторов.</span><span class="sxs-lookup"><span data-stu-id="eabee-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="eabee-104">Это отличается от предыдущих версий .NET Framework, где окна WPF обрезались, если выходили за пределы одного экрана.</span><span class="sxs-lookup"><span data-stu-id="eabee-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>|
|<span data-ttu-id="eabee-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="eabee-105">Suggestion</span></span>|<span data-ttu-id="eabee-106">Это поведение (отсутствие или наличие обрезки) можно задать явным образом с помощью элемента <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> в <code>&lt;appSettings&gt;</code> в файле конфигурации приложения или задав свойство <code>EnableMultiMonitorDisplayClipping</code> при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="eabee-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>|
|<span data-ttu-id="eabee-107">Область</span><span class="sxs-lookup"><span data-stu-id="eabee-107">Scope</span></span>|<span data-ttu-id="eabee-108">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="eabee-108">Minor</span></span>|
|<span data-ttu-id="eabee-109">Version</span><span class="sxs-lookup"><span data-stu-id="eabee-109">Version</span></span>|<span data-ttu-id="eabee-110">4.6</span><span class="sxs-lookup"><span data-stu-id="eabee-110">4.6</span></span>|
|<span data-ttu-id="eabee-111">Type</span><span class="sxs-lookup"><span data-stu-id="eabee-111">Type</span></span>|<span data-ttu-id="eabee-112">Параметры выполнения</span><span class="sxs-lookup"><span data-stu-id="eabee-112">Runtime</span></span>|
