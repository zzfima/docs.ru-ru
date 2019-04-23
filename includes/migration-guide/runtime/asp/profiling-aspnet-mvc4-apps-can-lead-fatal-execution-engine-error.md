---
ms.openlocfilehash: 439a4976482639cd2e4e17315ec1a53ca54aa477
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804956"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="40390-101">Профилирование приложений ASP.Net MVC4 может привести к неустранимой ошибке подсистемы выполнения</span><span class="sxs-lookup"><span data-stu-id="40390-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

|   |   |
|---|---|
|<span data-ttu-id="40390-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="40390-102">Details</span></span>|<span data-ttu-id="40390-103">Профилирование с использованием сборок NGEN /Profile может привести к сбою при запуске профилируемых приложений ASP.NET MVC4 с неустранимой ошибкой подсистемы выполнения</span><span class="sxs-lookup"><span data-stu-id="40390-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>|
|<span data-ttu-id="40390-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="40390-104">Suggestion</span></span>|<span data-ttu-id="40390-105">Эта проблема решена в .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="40390-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="40390-106">Также можно избежать этой проблемы, указав <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> в маске события профилировщика.</span><span class="sxs-lookup"><span data-stu-id="40390-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>|
|<span data-ttu-id="40390-107">Область</span><span class="sxs-lookup"><span data-stu-id="40390-107">Scope</span></span>|<span data-ttu-id="40390-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="40390-108">Edge</span></span>|
|<span data-ttu-id="40390-109">Версия</span><span class="sxs-lookup"><span data-stu-id="40390-109">Version</span></span>|<span data-ttu-id="40390-110">4.5</span><span class="sxs-lookup"><span data-stu-id="40390-110">4.5</span></span>|
|<span data-ttu-id="40390-111">Тип</span><span class="sxs-lookup"><span data-stu-id="40390-111">Type</span></span>|<span data-ttu-id="40390-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="40390-112">Runtime</span></span>|
