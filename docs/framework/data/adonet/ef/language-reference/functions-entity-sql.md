---
title: Функции (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: ec94a0f16fb3b836297f6675cc938a711816555b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250910"
---
# <a name="functions-entity-sql"></a><span data-ttu-id="56af3-102">Функции (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="56af3-102">Functions (Entity SQL)</span></span>
<span data-ttu-id="56af3-103">Язык Entity SQL поддерживает определяемые пользователем функции и функции поставщиков.</span><span class="sxs-lookup"><span data-stu-id="56af3-103">Entity SQL supports user-defined functions, canonical functions, and provider-specific functions.</span></span> <span data-ttu-id="56af3-104">Определяемые пользователем функции определяются в концептуальной модели либо внутри запроса.</span><span class="sxs-lookup"><span data-stu-id="56af3-104">User-defined functions are specified in the conceptual model or inline in the query.</span></span> <span data-ttu-id="56af3-105">Дополнительные сведения см. в разделе [определяемые пользователем функции](user-defined-functions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="56af3-105">For more information, see [User-Defined Functions](user-defined-functions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="56af3-106">Канонические функции встроены в платформу Entity Framework и должны поддерживаться поставщиками данных.</span><span class="sxs-lookup"><span data-stu-id="56af3-106">Canonical functions are predefined in the Entity Framework and should be supported by data providers.</span></span> <span data-ttu-id="56af3-107">Команды Entity SQL завершатся ошибкой, если пользователь вызывает функции, которые не поддерживаются поставщиком данных.</span><span class="sxs-lookup"><span data-stu-id="56af3-107">Entity SQL commands will fail if a user calls a function that is not supported by a provider.</span></span> <span data-ttu-id="56af3-108">Поэтому, как правило, рекомендуется использовать канонические функции, а не функции, зависящие от хранилища и находящиеся в пространстве имен поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="56af3-108">Therefore, canonical functions are generally recommended over store-specific functions, which are in a provider-specific namespace.</span></span> <span data-ttu-id="56af3-109">Дополнительные сведения см. в разделе [канонические функции](canonical-functions.md).</span><span class="sxs-lookup"><span data-stu-id="56af3-109">For more information, see [Canonical Functions](canonical-functions.md).</span></span>  
  
 <span data-ttu-id="56af3-110">Управляемый поставщик клиента Microsoft SQL предоставляет набор функций для поставщика.</span><span class="sxs-lookup"><span data-stu-id="56af3-110">The Microsoft SQL Client Managed Provider provides a set of provider-specific functions.</span></span> <span data-ttu-id="56af3-111">Дополнительные сведения см. в разделе [SqlClient для функций Entity Framework](../sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="56af3-111">For more information, see [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="56af3-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="56af3-112">In This Section</span></span>  
 [<span data-ttu-id="56af3-113">Определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="56af3-113">User-Defined Functions</span></span>](user-defined-functions-entity-sql.md)  
  
 [<span data-ttu-id="56af3-114">Разрешение перегрузки функций</span><span class="sxs-lookup"><span data-stu-id="56af3-114">Function Overload Resolution</span></span>](function-overload-resolution-entity-sql.md)  
  
 [<span data-ttu-id="56af3-115">Статистические функции</span><span class="sxs-lookup"><span data-stu-id="56af3-115">Aggregate Functions</span></span>](../aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="56af3-116">См. также</span><span class="sxs-lookup"><span data-stu-id="56af3-116">See also</span></span>

- [<span data-ttu-id="56af3-117">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="56af3-117">Entity SQL Overview</span></span>](entity-sql-overview.md)
