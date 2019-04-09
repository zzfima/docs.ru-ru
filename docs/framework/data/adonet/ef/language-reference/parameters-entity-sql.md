---
title: Параметры (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 47a1514933904daa623adc151d50525f011e07a7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187680"
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="fd9b9-102">Параметры (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="fd9b9-102">Parameters (Entity SQL)</span></span>
<span data-ttu-id="fd9b9-103">Параметры - это переменные, определенные вне [!INCLUDE[esql](../../../../../../includes/esql-md.md)] обычно через привязку API, используемую базовым языком.</span><span class="sxs-lookup"><span data-stu-id="fd9b9-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="fd9b9-104">Каждый параметр имеет имя и тип.</span><span class="sxs-lookup"><span data-stu-id="fd9b9-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="fd9b9-105">Имена параметров определены в выражениях запросов с символом (@) в качестве префикса.</span><span class="sxs-lookup"><span data-stu-id="fd9b9-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="fd9b9-106">Так они отличаются от имен свойств или других имен, определенных в запросе.</span><span class="sxs-lookup"><span data-stu-id="fd9b9-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="fd9b9-107">API-привязки базового языка предоставляет API для параметров привязки.</span><span class="sxs-lookup"><span data-stu-id="fd9b9-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd9b9-108">Пример</span><span class="sxs-lookup"><span data-stu-id="fd9b9-108">Example</span></span>  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="fd9b9-109">См. также</span><span class="sxs-lookup"><span data-stu-id="fd9b9-109">See also</span></span>

- [<span data-ttu-id="fd9b9-110">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fd9b9-110">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="fd9b9-111">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="fd9b9-111">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
