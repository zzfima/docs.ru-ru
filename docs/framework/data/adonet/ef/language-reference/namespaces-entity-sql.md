---
title: "Пространства имен (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0ea5292d20aebdb27da726b0076179fb64631e5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="namespaces-entity-sql"></a><span data-ttu-id="6686a-102">Пространства имен (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6686a-102">Namespaces (Entity SQL)</span></span>
<span data-ttu-id="6686a-103">В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] были введены пространства имен, чтобы избежать возникновения конфликтов с именами глобальных идентификаторов, например именами типов, наборов сущностей, функций и т. д.</span><span class="sxs-lookup"><span data-stu-id="6686a-103">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] introduces namespaces to avoid name conflicts for global identifiers such as type names, entity sets, functions, and so on.</span></span> <span data-ttu-id="6686a-104">Поддержка пространств имен в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] похожа на поддержку пространств имен в [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6686a-104">The namespace support in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is similar to the namespace support in the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="6686a-105"> предоставляет две формы предложения USING: полные пространства имен (для пространства имен предоставляется короткий псевдоним) и неполные пространства имен, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6686a-105"> provides two forms of the USING clause: qualified namespaces (where a shorter alias is provided for the namespace), and unqualified namespaces, as illustrated in the following example:</span></span>  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a><span data-ttu-id="6686a-106">Правила разрешения имен</span><span class="sxs-lookup"><span data-stu-id="6686a-106">Name Resolution Rules</span></span>  
 <span data-ttu-id="6686a-107">Если идентификатор не удается разрешить в локальных областях, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] пытается найти имя в глобальных областях (пространствах имен).</span><span class="sxs-lookup"><span data-stu-id="6686a-107">If an identifier cannot be resolved in the local scopes, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to locate the name in the global scopes (the namespaces).</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="6686a-108"> вначале пытается сопоставить идентификатор (префикс) с одним из полных пространств имен.</span><span class="sxs-lookup"><span data-stu-id="6686a-108"> first tries to match the identifier (prefix) with one of the qualified namespaces.</span></span> <span data-ttu-id="6686a-109">Если соответствие, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] пытается разрешить остальную часть идентификатора в указанном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="6686a-109">If there is a match, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to resolve the rest of the identifier in the specified namespace.</span></span> <span data-ttu-id="6686a-110">Если совпадение не найдено, вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="6686a-110">If no match is found, an exception is thrown.</span></span>  
  
 <span data-ttu-id="6686a-111">Далее, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] пытается выполнить поиск всех неполных пространствах имен (указанных в прологе) для идентификатора.</span><span class="sxs-lookup"><span data-stu-id="6686a-111">Next, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to search all unqualified namespaces (specified in the prolog) for the identifier.</span></span> <span data-ttu-id="6686a-112">Если идентификатор удается найти только в одном пространстве имен, возвращается расположение.</span><span class="sxs-lookup"><span data-stu-id="6686a-112">If the identifier can be located in exactly one namespace, that location is returned.</span></span> <span data-ttu-id="6686a-113">Если для идентификатора обнаружены совпадения в нескольких пространствах имен, вызывается исключение.</span><span class="sxs-lookup"><span data-stu-id="6686a-113">If more than one namespace has a match for that identifier, an exception is thrown.</span></span> <span data-ttu-id="6686a-114">Если пространство имен не может быть выделен для идентификатора, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] передает имя Далее, внешней области ( <xref:System.Data.Common.DbCommand> или <xref:System.Data.Common.DbConnection> объекта), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="6686a-114">If no namespace can be identified for the identifier, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] passes the name onto the next outward scope (the <xref:System.Data.Common.DbCommand> or <xref:System.Data.Common.DbConnection> object), as illustrated in the following example:</span></span>  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a><span data-ttu-id="6686a-115">Отличия от платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6686a-115">Differences from the .NET Framework</span></span>  
 <span data-ttu-id="6686a-116">В платформе [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] можно использовать частичные пространства имен.</span><span class="sxs-lookup"><span data-stu-id="6686a-116">In the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)], you can use partially qualified namespaces.</span></span> <span data-ttu-id="6686a-117">В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] это недопустимо.</span><span class="sxs-lookup"><span data-stu-id="6686a-117">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not allow this.</span></span>  
  
## <a name="adonet-usage"></a><span data-ttu-id="6686a-118">Использование ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6686a-118">ADO.NET Usage</span></span>  
 <span data-ttu-id="6686a-119">Запросы выражаются посредством объектов <xref:System.Data.Common.DbCommand> ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="6686a-119">Queries are expressed through ADO.NET <xref:System.Data.Common.DbCommand> objects.</span></span> <span data-ttu-id="6686a-120">Объекты <xref:System.Data.Common.DbCommand> могут быть построены на основе объектов <xref:System.Data.Common.DbConnection>.</span><span class="sxs-lookup"><span data-stu-id="6686a-120"><xref:System.Data.Common.DbCommand> objects can be built over <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="6686a-121">Пространства имен также могут быть указаны как часть объектов <xref:System.Data.Common.DbCommand> и <xref:System.Data.Common.DbConnection>.</span><span class="sxs-lookup"><span data-stu-id="6686a-121">Namespaces can also be specified as part of the <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="6686a-122">Если [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не удалось разрешить идентификатор в самом запросе во внешних пространствах имен проверяются (на основании похожих правил).</span><span class="sxs-lookup"><span data-stu-id="6686a-122">If [!INCLUDE[esql](../../../../../../includes/esql-md.md)] cannot resolve an identifier within the query itself, the external namespaces are probed (based on similar rules).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6686a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="6686a-123">See Also</span></span>  
 [<span data-ttu-id="6686a-124">Справочник по Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6686a-124">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="6686a-125">Общие сведения об Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6686a-125">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
