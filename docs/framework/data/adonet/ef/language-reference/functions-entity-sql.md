---
title: Функции (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: f31f829b53160da5a043617b9aa999b398859f17
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080609"
---
# <a name="functions-entity-sql"></a><span data-ttu-id="f97a4-102">Функции (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="f97a4-102">Functions (Entity SQL)</span></span>
<span data-ttu-id="f97a4-103">Язык Entity SQL поддерживает определяемые пользователем функции и функции поставщиков.</span><span class="sxs-lookup"><span data-stu-id="f97a4-103">Entity SQL supports user-defined functions, canonical functions, and provider-specific functions.</span></span> <span data-ttu-id="f97a4-104">Определяемые пользователем функции определяются в концептуальной модели либо внутри запроса.</span><span class="sxs-lookup"><span data-stu-id="f97a4-104">User-defined functions are specified in the conceptual model or inline in the query.</span></span> <span data-ttu-id="f97a4-105">Дополнительные сведения см. в разделе [определяемые пользователем функции](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f97a4-105">For more information, see [User-Defined Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="f97a4-106">Канонические функции встроены в платформу Entity Framework и должны поддерживаться поставщиками данных.</span><span class="sxs-lookup"><span data-stu-id="f97a4-106">Canonical functions are predefined in the Entity Framework and should be supported by data providers.</span></span> <span data-ttu-id="f97a4-107">Команды Entity SQL завершатся ошибкой, если пользователь вызывает функции, которые не поддерживаются поставщиком данных.</span><span class="sxs-lookup"><span data-stu-id="f97a4-107">Entity SQL commands will fail if a user calls a function that is not supported by a provider.</span></span> <span data-ttu-id="f97a4-108">Поэтому, как правило, рекомендуется использовать канонические функции, а не функции, зависящие от хранилища и находящиеся в пространстве имен поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="f97a4-108">Therefore, canonical functions are generally recommended over store-specific functions, which are in a provider-specific namespace.</span></span> <span data-ttu-id="f97a4-109">Дополнительные сведения см. в разделе [канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span><span class="sxs-lookup"><span data-stu-id="f97a4-109">For more information, see [Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span></span>  
  
 <span data-ttu-id="f97a4-110">Управляемый поставщик клиента Microsoft SQL предоставляет набор функций для поставщика.</span><span class="sxs-lookup"><span data-stu-id="f97a4-110">The Microsoft SQL Client Managed Provider provides a set of provider-specific functions.</span></span> <span data-ttu-id="f97a4-111">Дополнительные сведения см. в разделе [функции SqlClient для Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="f97a4-111">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f97a4-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f97a4-112">In This Section</span></span>  
 [<span data-ttu-id="f97a4-113">Определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="f97a4-113">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)  
  
 [<span data-ttu-id="f97a4-114">Разрешение перегрузки функций</span><span class="sxs-lookup"><span data-stu-id="f97a4-114">Function Overload Resolution</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)  
  
 [<span data-ttu-id="f97a4-115">Статистические функции</span><span class="sxs-lookup"><span data-stu-id="f97a4-115">Aggregate Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="f97a4-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f97a4-116">See also</span></span>

- [<span data-ttu-id="f97a4-117">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="f97a4-117">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
