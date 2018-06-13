---
title: Пространства имен (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: c2ddf78dcf41f083e3d6fc5affc80276eb842e67
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32763645"
---
# <a name="namespaces-entity-sql"></a>Пространства имен (Entity SQL)
В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] были введены пространства имен, чтобы избежать возникновения конфликтов с именами глобальных идентификаторов, например именами типов, наборов сущностей, функций и т. д. Поддержка пространств имен в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] похожа на поддержку пространств имен в [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] предоставляет две формы предложения USING: полные пространства имен (для пространства имен предоставляется короткий псевдоним) и неполные пространства имен, как показано в следующем примере:  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a>Правила разрешения имен  
 Если идентификатор не удается разрешить в локальных областях, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] пытается найти имя в глобальных областях (пространствах имен). [!INCLUDE[esql](../../../../../../includes/esql-md.md)] вначале пытается сопоставить идентификатор (префикс) с одним из полных пространств имен. Если соответствие, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] пытается разрешить остальную часть идентификатора в указанном пространстве имен. Если совпадение не найдено, вызывается исключение.  
  
 Далее, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] пытается выполнить поиск всех неполных пространствах имен (указанных в прологе) для идентификатора. Если идентификатор удается найти только в одном пространстве имен, возвращается расположение. Если для идентификатора обнаружены совпадения в нескольких пространствах имен, вызывается исключение. Если пространство имен не может быть выделен для идентификатора, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] передает имя Далее, внешней области ( <xref:System.Data.Common.DbCommand> или <xref:System.Data.Common.DbConnection> объекта), как показано в следующем примере:  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a>Отличия от платформы .NET Framework  
 В платформе [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] можно использовать частичные пространства имен. В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] это недопустимо.  
  
## <a name="adonet-usage"></a>Использование ADO.NET  
 Запросы выражаются посредством объектов <xref:System.Data.Common.DbCommand> ADO.NET. Объекты <xref:System.Data.Common.DbCommand> могут быть построены на основе объектов <xref:System.Data.Common.DbConnection>. Пространства имен также могут быть указаны как часть объектов <xref:System.Data.Common.DbCommand> и <xref:System.Data.Common.DbConnection>. Если [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не удалось разрешить идентификатор в самом запросе во внешних пространствах имен проверяются (на основании похожих правил).  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Общие сведения об Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
