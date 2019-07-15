---
ms.openlocfilehash: 2e974d277d6659aaada321b2a7e7a604df78a7bd
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858538"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a><span data-ttu-id="30c46-101">Окна WPF отображаются без обрезки, если изображение выходит за пределы одного монитора</span><span class="sxs-lookup"><span data-stu-id="30c46-101">WPF windows are rendered without clipping when extending outside a single monitor</span></span>

|   |   |
|---|---|
|<span data-ttu-id="30c46-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="30c46-102">Details</span></span>|<span data-ttu-id="30c46-103">В .NET Framework 4.6 на компьютере под управлением Windows 8 и более поздних версий все содержимое окна выводится без обрезки, если изображение выходит за пределы одного экрана при использовании нескольких мониторов.</span><span class="sxs-lookup"><span data-stu-id="30c46-103">In the .NET Framework 4.6 running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span> <span data-ttu-id="30c46-104">Это отличается от предыдущих версий .NET Framework, где окна WPF обрезались, если выходили за пределы одного экрана.</span><span class="sxs-lookup"><span data-stu-id="30c46-104">This is different from previous versions of the .NET Framework which would clip WPF windows that extended beyond a single display.</span></span>|
|<span data-ttu-id="30c46-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="30c46-105">Suggestion</span></span>|<span data-ttu-id="30c46-106">Это поведение (отсутствие или наличие обрезки) можно задать явным образом с помощью элемента <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> в <code>&lt;appSettings&gt;</code> в файле конфигурации приложения или задав свойство <code>EnableMultiMonitorDisplayClipping</code> при запуске приложения.</span><span class="sxs-lookup"><span data-stu-id="30c46-106">This behavior (whether to clip or not) can be explicitly set using the <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> element in <code>&lt;appSettings&gt;</code> in an application's configuration file, or by setting the <code>EnableMultiMonitorDisplayClipping</code> property at app startup.</span></span>|
|<span data-ttu-id="30c46-107">Область</span><span class="sxs-lookup"><span data-stu-id="30c46-107">Scope</span></span>|<span data-ttu-id="30c46-108">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="30c46-108">Minor</span></span>|
|<span data-ttu-id="30c46-109">Версия</span><span class="sxs-lookup"><span data-stu-id="30c46-109">Version</span></span>|<span data-ttu-id="30c46-110">4.6</span><span class="sxs-lookup"><span data-stu-id="30c46-110">4.6</span></span>|
|<span data-ttu-id="30c46-111">Тип</span><span class="sxs-lookup"><span data-stu-id="30c46-111">Type</span></span>|<span data-ttu-id="30c46-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="30c46-112">Runtime</span></span>|

