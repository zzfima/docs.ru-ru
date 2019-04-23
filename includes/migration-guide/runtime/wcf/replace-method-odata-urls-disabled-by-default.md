---
ms.openlocfilehash: 6dc3669433804a4524c18d5a932f9879343ab508
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804883"
---
### <a name="the-replace-method-in-odata-urls-is-disabled-by-default"></a><span data-ttu-id="692eb-101">Метод Replace в URL-адресах OData по умолчанию отключен</span><span class="sxs-lookup"><span data-stu-id="692eb-101">The Replace method in OData URLs is disabled by default</span></span>

|   |   |
|---|---|
|<span data-ttu-id="692eb-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="692eb-102">Details</span></span>|<span data-ttu-id="692eb-103">Начиная с .NET Framework 4.5, метод Replace в URL-адресах OData по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="692eb-103">Beginning in the .NET Framework 4.5, the Replace method in OData URLs is disabled by default.</span></span> <span data-ttu-id="692eb-104">Если метод Replace OData отключен (теперь по умолчанию), все запросы пользователя, включая функции Replace (которые используются редко), завершатся ошибкой.</span><span class="sxs-lookup"><span data-stu-id="692eb-104">When OData Replace is disabled (now by default), any user requests including replace functions (which are uncommon) will fail.</span></span>|
|<span data-ttu-id="692eb-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="692eb-105">Suggestion</span></span>|<span data-ttu-id="692eb-106">Если необходим метод Replace (который используется редко), его можно включить в параметрах конфигурации (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>).</span><span class="sxs-lookup"><span data-stu-id="692eb-106">If the replace method is required (which is uncommon), it can be re-enabled through a config settings (<xref:System.Data.Services.Configuration.DataServicesFeaturesSection.ReplaceFunction?displayProperty=name>).</span></span> <span data-ttu-id="692eb-107">Однако включенный метод Replace может открывать уязвимости системы безопасности, поэтому он должен использоваться только после тщательной проверки.</span><span class="sxs-lookup"><span data-stu-id="692eb-107">However, an enabled replace method can open security vulnerabilities and should only be used after careful review.</span></span>|
|<span data-ttu-id="692eb-108">Область</span><span class="sxs-lookup"><span data-stu-id="692eb-108">Scope</span></span>|<span data-ttu-id="692eb-109">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="692eb-109">Edge</span></span>|
|<span data-ttu-id="692eb-110">Версия</span><span class="sxs-lookup"><span data-stu-id="692eb-110">Version</span></span>|<span data-ttu-id="692eb-111">4.5</span><span class="sxs-lookup"><span data-stu-id="692eb-111">4.5</span></span>|
|<span data-ttu-id="692eb-112">Тип</span><span class="sxs-lookup"><span data-stu-id="692eb-112">Type</span></span>|<span data-ttu-id="692eb-113">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="692eb-113">Runtime</span></span>|
|<span data-ttu-id="692eb-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="692eb-114">Affected APIs</span></span>|<ul><li><xref:System.Data.Services.DataService%601?displayProperty=nameWithType></li></ul>|
