---
ms.openlocfilehash: e7a5a95a5d13f3396d396ad0d74a19a0efa3a967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235531"
---
### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a><span data-ttu-id="b19cd-101">В данных Sql_variant используется сортировка sql_variant, а не сортировка базы данных</span><span class="sxs-lookup"><span data-stu-id="b19cd-101">Sql_variant data uses sql_variant collation rather than database collation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b19cd-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="b19cd-102">Details</span></span>|<span data-ttu-id="b19cd-103">В данных <code>sql_variant</code> используется сортировка <code>sql_variant</code>, а не сортировка базы данных.</span><span class="sxs-lookup"><span data-stu-id="b19cd-103"><code>sql_variant</code> data uses <code>sql_variant</code> collation rather than database collation.</span></span>|
|<span data-ttu-id="b19cd-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="b19cd-104">Suggestion</span></span>|<span data-ttu-id="b19cd-105">Это изменение предотвращает возможное повреждение данных, если сортировка базы данных отличается от сортировки <code>sql_variant</code>.</span><span class="sxs-lookup"><span data-stu-id="b19cd-105">This change addresses possible data corruption if the database collation differs from the <code>sql_variant</code> collation.</span></span> <span data-ttu-id="b19cd-106">В приложениях, в которых предполагается, что данные будут повреждены, могут возникать сбои.</span><span class="sxs-lookup"><span data-stu-id="b19cd-106">Applications that rely on the corrupted data may experience failure.</span></span>|
|<span data-ttu-id="b19cd-107">Область</span><span class="sxs-lookup"><span data-stu-id="b19cd-107">Scope</span></span>|<span data-ttu-id="b19cd-108">Прозрачный</span><span class="sxs-lookup"><span data-stu-id="b19cd-108">Transparent</span></span>|
|<span data-ttu-id="b19cd-109">Версия</span><span class="sxs-lookup"><span data-stu-id="b19cd-109">Version</span></span>|<span data-ttu-id="b19cd-110">4.5</span><span class="sxs-lookup"><span data-stu-id="b19cd-110">4.5</span></span>|
|<span data-ttu-id="b19cd-111">Тип</span><span class="sxs-lookup"><span data-stu-id="b19cd-111">Type</span></span>|<span data-ttu-id="b19cd-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="b19cd-112">Runtime</span></span>|
