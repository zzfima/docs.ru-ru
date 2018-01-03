---
title: "Параметры (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4cbc13433b742cea1063cbd284690ce8cabbbfc4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="07664-102">Параметры (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="07664-102">Parameters (Entity SQL)</span></span>
<span data-ttu-id="07664-103">Параметры - это переменные, определенные вне [!INCLUDE[esql](../../../../../../includes/esql-md.md)] обычно через привязку API, используемую базовым языком.</span><span class="sxs-lookup"><span data-stu-id="07664-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="07664-104">Каждый параметр имеет имя и тип.</span><span class="sxs-lookup"><span data-stu-id="07664-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="07664-105">Имена параметров определены в выражениях запросов с символом (@) в качестве префикса.</span><span class="sxs-lookup"><span data-stu-id="07664-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="07664-106">Так они отличаются от имен свойств или других имен, определенных в запросе.</span><span class="sxs-lookup"><span data-stu-id="07664-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="07664-107">API-привязки базового языка предоставляет API для параметров привязки.</span><span class="sxs-lookup"><span data-stu-id="07664-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07664-108">Пример</span><span class="sxs-lookup"><span data-stu-id="07664-108">Example</span></span>  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="07664-109">См. также</span><span class="sxs-lookup"><span data-stu-id="07664-109">See Also</span></span>  
 [<span data-ttu-id="07664-110">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="07664-110">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="07664-111">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="07664-111">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
