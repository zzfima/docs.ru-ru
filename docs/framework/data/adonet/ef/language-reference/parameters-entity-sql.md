---
title: Параметры (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: e1bb633f7f7c7908a5f424991f20a5cd89aee5aa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150018"
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="1eeb9-102">Параметры (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="1eeb9-102">Parameters (Entity SQL)</span></span>
<span data-ttu-id="1eeb9-103">Параметры - это переменные, определенные вне [!INCLUDE[esql](../../../../../../includes/esql-md.md)] обычно через привязку API, используемую базовым языком.</span><span class="sxs-lookup"><span data-stu-id="1eeb9-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="1eeb9-104">Каждый параметр имеет имя и тип.</span><span class="sxs-lookup"><span data-stu-id="1eeb9-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="1eeb9-105">Имена параметров определены в выражениях запросов с символом (@) в качестве префикса.</span><span class="sxs-lookup"><span data-stu-id="1eeb9-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="1eeb9-106">Так они отличаются от имен свойств или других имен, определенных в запросе.</span><span class="sxs-lookup"><span data-stu-id="1eeb9-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="1eeb9-107">API-привязки базового языка предоставляет API для параметров привязки.</span><span class="sxs-lookup"><span data-stu-id="1eeb9-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1eeb9-108">Пример</span><span class="sxs-lookup"><span data-stu-id="1eeb9-108">Example</span></span>  
  
```sql  
SELECT c
      FROM LOB.Customers AS c
      WHERE c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="1eeb9-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1eeb9-109">See also</span></span>

- [<span data-ttu-id="1eeb9-110">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1eeb9-110">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="1eeb9-111">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="1eeb9-111">Entity SQL Overview</span></span>](entity-sql-overview.md)
