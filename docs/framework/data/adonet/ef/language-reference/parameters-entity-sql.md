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
ms.openlocfilehash: 2a3700b5f9bdc996b147609d86bcaed0ec0bb116
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="parameters-entity-sql"></a><span data-ttu-id="61a05-102">Параметры (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="61a05-102">Parameters (Entity SQL)</span></span>
<span data-ttu-id="61a05-103">Параметры - это переменные, определенные вне [!INCLUDE[esql](../../../../../../includes/esql-md.md)] обычно через привязку API, используемую базовым языком.</span><span class="sxs-lookup"><span data-stu-id="61a05-103">Parameters are variables that are defined outside [!INCLUDE[esql](../../../../../../includes/esql-md.md)], usually through a binding API that is used by a host language.</span></span> <span data-ttu-id="61a05-104">Каждый параметр имеет имя и тип.</span><span class="sxs-lookup"><span data-stu-id="61a05-104">Each parameter has a name and a type.</span></span> <span data-ttu-id="61a05-105">Имена параметров определены в выражениях запросов с символом (@) в качестве префикса.</span><span class="sxs-lookup"><span data-stu-id="61a05-105">Parameter names are defined in query expressions with the at (@) symbol as a prefix.</span></span> <span data-ttu-id="61a05-106">Так они отличаются от имен свойств или других имен, определенных в запросе.</span><span class="sxs-lookup"><span data-stu-id="61a05-106">This disambiguates them from the names of properties or other names that are defined in the query.</span></span>  
  
 <span data-ttu-id="61a05-107">API-привязки базового языка предоставляет API для параметров привязки.</span><span class="sxs-lookup"><span data-stu-id="61a05-107">The host-language binding API provides APIs for binding parameters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61a05-108">Пример</span><span class="sxs-lookup"><span data-stu-id="61a05-108">Example</span></span>  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## <a name="see-also"></a><span data-ttu-id="61a05-109">См. также</span><span class="sxs-lookup"><span data-stu-id="61a05-109">See Also</span></span>  
 [<span data-ttu-id="61a05-110">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="61a05-110">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="61a05-111">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="61a05-111">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
