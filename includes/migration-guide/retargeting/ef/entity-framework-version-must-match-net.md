---
ms.openlocfilehash: 4c6a89f9753989a5ad061e847dff70d2af0b3cf4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774425"
---
### <a name="entity-framework-version-must-match-the-net-framework-version"></a><span data-ttu-id="ce586-101">Версия Entity Framework должна соответствовать версии .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ce586-101">Entity Framework version must match the .NET Framework version</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ce586-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="ce586-102">Details</span></span>|<span data-ttu-id="ce586-103">Версия Entity Framework должна соответствовать версии платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ce586-103">The entity framework version should be matched with the .NET framework version.</span></span> <span data-ttu-id="ce586-104">Для .NET Framework 4.5 рекомендуется Entity Framework 5.</span><span class="sxs-lookup"><span data-stu-id="ce586-104">Entity Framework 5 is recommended for .NET Framework 4.5.</span></span> <span data-ttu-id="ce586-105">Существуют некоторые известные проблемы с EF 4.x в проекте .NET Framework 4.5, связанные с <xref:System.ComponentModel.DataAnnotations>.</span><span class="sxs-lookup"><span data-stu-id="ce586-105">There are some known issues with EF 4.x in a .NET Framework 4.5 project around <xref:System.ComponentModel.DataAnnotations>.</span></span> <span data-ttu-id="ce586-106">В .NET 4.5 они были перемещены в другую сборку, поэтому существуют проблемы с выбором заметок для использования.</span><span class="sxs-lookup"><span data-stu-id="ce586-106">In .NET 4.5, these were moved to a different assembly, so there are issues determining which annotations to use.</span></span>|
|<span data-ttu-id="ce586-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="ce586-107">Suggestion</span></span>|<span data-ttu-id="ce586-108">Обновление до версии Entity Framework 5 для .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="ce586-108">Upgrade to Entity Framework 5 for .NET Framework 4.5</span></span>|
|<span data-ttu-id="ce586-109">Область</span><span class="sxs-lookup"><span data-stu-id="ce586-109">Scope</span></span>|<span data-ttu-id="ce586-110">Значительно</span><span class="sxs-lookup"><span data-stu-id="ce586-110">Major</span></span>|
|<span data-ttu-id="ce586-111">Версия</span><span class="sxs-lookup"><span data-stu-id="ce586-111">Version</span></span>|<span data-ttu-id="ce586-112">4.5</span><span class="sxs-lookup"><span data-stu-id="ce586-112">4.5</span></span>|
|<span data-ttu-id="ce586-113">Тип</span><span class="sxs-lookup"><span data-stu-id="ce586-113">Type</span></span>|<span data-ttu-id="ce586-114">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="ce586-114">Retargeting</span></span>|
