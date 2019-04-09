---
title: Пространства имен (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: bef2fa96ce090a600155d68ecc3daea55b675840
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59185527"
---
# <a name="namespaces-entity-sql"></a>Пространства имен (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] Знакомит с пространствами имен, чтобы избежать конфликтов с именами глобальных идентификаторов, например имена типов, наборов сущностей, функций и т. д. Поддержка пространств имен в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] похожа на поддержку пространств имен в [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] предоставляет две формы предложения USING: полные пространства имен (где предоставляется короткий псевдоним для пространства имен) и неполные пространства имен, как показано в следующем примере:  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a>Правила разрешения имен  
 Если идентификатор не может быть разрешен в локальных областях, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] пытается найти имя в глобальных областях (пространствах имен). [!INCLUDE[esql](../../../../../../includes/esql-md.md)] сначала пытается сопоставить идентификатор (префикс) с одним из полных пространств имен. Если есть совпадение имени, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] пытается разрешить остальную часть идентификатора в указанном пространстве имен. Если совпадение не найдено, вызывается исключение.  
  
 Далее, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] пытается выполнить поиск всех неполных пространствах имен (указанных в прологе) для идентификатора. Если идентификатор удается найти только в одном пространстве имен, возвращается расположение. Если для идентификатора обнаружены совпадения в нескольких пространствах имен, вызывается исключение. Если пространство имен не удается найти для идентификатора, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] передает имя Далее, внешней области ( <xref:System.Data.Common.DbCommand> или <xref:System.Data.Common.DbConnection> объекта), как показано в следующем примере:  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a>Отличия от платформы .NET Framework  
 В платформе [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] можно использовать частичные пространства имен. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Это не разрешено.  
  
## <a name="adonet-usage"></a>Использование ADO.NET  
 Запросы выражаются посредством объектов <xref:System.Data.Common.DbCommand> ADO.NET. <xref:System.Data.Common.DbCommand> объекты могут быть построены <xref:System.Data.Common.DbConnection> объектов. Пространства имен также могут быть указаны как часть объектов <xref:System.Data.Common.DbCommand> и <xref:System.Data.Common.DbConnection>. Если [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не удается разрешить идентификатор в самом запросе внешних пространствах имен проверяются (на основании похожих правил).  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [Общие сведения об Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
