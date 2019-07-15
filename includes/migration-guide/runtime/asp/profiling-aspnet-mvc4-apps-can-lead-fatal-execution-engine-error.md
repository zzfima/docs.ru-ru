---
ms.openlocfilehash: 107b34c7bd26e1396e8a6638d6929c15de92b8e4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803180"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="e3c03-101">Профилирование приложений ASP.Net MVC4 может привести к неустранимой ошибке подсистемы выполнения</span><span class="sxs-lookup"><span data-stu-id="e3c03-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e3c03-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e3c03-102">Details</span></span>|<span data-ttu-id="e3c03-103">Профилирование с использованием сборок NGEN /Profile может привести к сбою при запуске профилируемых приложений ASP.NET MVC4 с неустранимой ошибкой подсистемы выполнения</span><span class="sxs-lookup"><span data-stu-id="e3c03-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>|
|<span data-ttu-id="e3c03-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="e3c03-104">Suggestion</span></span>|<span data-ttu-id="e3c03-105">Эта проблема решена в .NET Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="e3c03-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="e3c03-106">Также можно избежать этой проблемы, указав <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> в маске события профилировщика.</span><span class="sxs-lookup"><span data-stu-id="e3c03-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>|
|<span data-ttu-id="e3c03-107">Область</span><span class="sxs-lookup"><span data-stu-id="e3c03-107">Scope</span></span>|<span data-ttu-id="e3c03-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="e3c03-108">Edge</span></span>|
|<span data-ttu-id="e3c03-109">Версия</span><span class="sxs-lookup"><span data-stu-id="e3c03-109">Version</span></span>|<span data-ttu-id="e3c03-110">4.5</span><span class="sxs-lookup"><span data-stu-id="e3c03-110">4.5</span></span>|
|<span data-ttu-id="e3c03-111">Тип</span><span class="sxs-lookup"><span data-stu-id="e3c03-111">Type</span></span>|<span data-ttu-id="e3c03-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="e3c03-112">Runtime</span></span>|

