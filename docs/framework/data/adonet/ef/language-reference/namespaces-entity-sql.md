---
title: Пространства имен (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: 395ffb23859be27b4897dfc352f6e44d52286b26
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249996"
---
# <a name="namespaces-entity-sql"></a>Пространства имен (Entity SQL)
В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] были введены пространства имен, чтобы избежать возникновения конфликтов с именами глобальных идентификаторов, например именами типов, наборов сущностей, функций и т. д. Поддержка пространства имен в [!INCLUDE[esql](../../../../../../includes/esql-md.md)] аналогична поддержке пространства имен в .NET Framework.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] предоставляет две формы предложения USING: полные пространства имен (для пространства имен предоставляется короткий псевдоним) и неполные пространства имен, как показано в следующем примере:  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a>Правила разрешения имен  
 Если идентификатор не может быть разрешен в локальных областях, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] пытается определить имя в глобальных областях (пространства имен). [!INCLUDE[esql](../../../../../../includes/esql-md.md)] вначале пытается сопоставить идентификатор (префикс) с одним из полных пространств имен. При наличии совпадения [!INCLUDE[esql](../../../../../../includes/esql-md.md)] пытается разрешить оставшуюся часть идентификатора в указанном пространстве имен. Если совпадение не найдено, вызывается исключение.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Затем пытается выполнить поиск идентификатора в всех неполных пространствах имен (указанных в прологе). Если идентификатор удается найти только в одном пространстве имен, возвращается расположение. Если для идентификатора обнаружены совпадения в нескольких пространствах имен, вызывается исключение. Если для идентификатора не может быть определено пространство имен [!INCLUDE[esql](../../../../../../includes/esql-md.md)] , передает имя в следующую внешную область <xref:System.Data.Common.DbCommand> (объект или <xref:System.Data.Common.DbConnection> ), как показано в следующем примере:  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a>Отличия от платформы .NET Framework  
 В .NET Framework можно использовать частично определенные пространства имен. В [!INCLUDE[esql](../../../../../../includes/esql-md.md)] это недопустимо.  
  
## <a name="adonet-usage"></a>Использование ADO.NET  
 Запросы выражаются посредством объектов <xref:System.Data.Common.DbCommand> ADO.NET. Объекты <xref:System.Data.Common.DbCommand> могут быть построены на основе объектов <xref:System.Data.Common.DbConnection>. Пространства имен также могут быть указаны как часть объектов <xref:System.Data.Common.DbCommand> и <xref:System.Data.Common.DbConnection>. Если [!INCLUDE[esql](../../../../../../includes/esql-md.md)] не может разрешить идентификатор внутри самого запроса, внешние пространства имен проходят проверку (на основе аналогичных правил).  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
- [Общие сведения об Entity SQL](entity-sql-overview.md)
