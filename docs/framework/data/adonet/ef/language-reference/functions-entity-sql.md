---
title: Функции (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 52b3d776-5acc-4f69-b614-5a43ce56ef9f
ms.openlocfilehash: 88029f22cc22594d26a05ad66051378a75a6e753
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715599"
---
# <a name="functions-entity-sql"></a><span data-ttu-id="66447-102">Функции (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="66447-102">Functions (Entity SQL)</span></span>
<span data-ttu-id="66447-103">Язык Entity SQL поддерживает определяемые пользователем функции и функции поставщиков.</span><span class="sxs-lookup"><span data-stu-id="66447-103">Entity SQL supports user-defined functions, canonical functions, and provider-specific functions.</span></span> <span data-ttu-id="66447-104">Определяемые пользователем функции определяются в концептуальной модели либо внутри запроса.</span><span class="sxs-lookup"><span data-stu-id="66447-104">User-defined functions are specified in the conceptual model or inline in the query.</span></span> <span data-ttu-id="66447-105">Дополнительные сведения см. в разделе [определяемые пользователем функции](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="66447-105">For more information, see [User-Defined Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="66447-106">Канонические функции встроены в платформу Entity Framework и должны поддерживаться поставщиками данных.</span><span class="sxs-lookup"><span data-stu-id="66447-106">Canonical functions are predefined in the Entity Framework and should be supported by data providers.</span></span> <span data-ttu-id="66447-107">Команды Entity SQL завершатся ошибкой, если пользователь вызывает функции, которые не поддерживаются поставщиком данных.</span><span class="sxs-lookup"><span data-stu-id="66447-107">Entity SQL commands will fail if a user calls a function that is not supported by a provider.</span></span> <span data-ttu-id="66447-108">Поэтому, как правило, рекомендуется использовать канонические функции, а не функции, зависящие от хранилища и находящиеся в пространстве имен поставщика данных.</span><span class="sxs-lookup"><span data-stu-id="66447-108">Therefore, canonical functions are generally recommended over store-specific functions, which are in a provider-specific namespace.</span></span> <span data-ttu-id="66447-109">Дополнительные сведения см. в разделе [канонические функции](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span><span class="sxs-lookup"><span data-stu-id="66447-109">For more information, see [Canonical Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md).</span></span>  
  
 <span data-ttu-id="66447-110">Управляемый поставщик клиента Microsoft SQL предоставляет набор функций для поставщика.</span><span class="sxs-lookup"><span data-stu-id="66447-110">The Microsoft SQL Client Managed Provider provides a set of provider-specific functions.</span></span> <span data-ttu-id="66447-111">Дополнительные сведения см. в разделе [функции SqlClient для Entity Framework](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span><span class="sxs-lookup"><span data-stu-id="66447-111">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66447-112">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="66447-112">In This Section</span></span>  
 [<span data-ttu-id="66447-113">Определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="66447-113">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)  
  
 [<span data-ttu-id="66447-114">Разрешение перегрузки функций</span><span class="sxs-lookup"><span data-stu-id="66447-114">Function Overload Resolution</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)  
  
 [<span data-ttu-id="66447-115">Статистические функции</span><span class="sxs-lookup"><span data-stu-id="66447-115">Aggregate Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/aggregate-functions-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="66447-116">См. также</span><span class="sxs-lookup"><span data-stu-id="66447-116">See also</span></span>
- [<span data-ttu-id="66447-117">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="66447-117">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
