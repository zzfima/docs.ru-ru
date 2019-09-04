---
title: TREAT (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b77f156-55de-4cb4-8154-87f707d4c635
ms.openlocfilehash: b7393bef32b3e057eca51eb516cb72cd2de126c2
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248965"
---
# <a name="treat-entity-sql"></a>TREAT (Entity SQL)
Обрабатывает объект некоторого базового типа, как объект указанного производного типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
TREAT ( expression as type)  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение запроса, возвращающее сущность.  
  
> [!NOTE]
> Тип указанного выражения должен быть подтипом указанного типа данных, либо тип данных должен быть подтипом типа выражения.  
  
 `type`  
 Тип сущности. Для типа должно быть указано пространство имен.  
  
> [!NOTE]
> Указанное выражение должно быть подтипом указанного типа данных, либо тип данных должен быть подтипом данного выражения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение указанного типа данных.  
  
## <a name="remarks"></a>Примечания  
 Оператор TREAT предназначен для приведения связанных классов к базовому типу. Например, если тип `Employee` является производным от типа `Person` , а «p» относится к типу `Person`, то выражение `TREAT(p AS NamespaceName.Employee)` приводит общий экземпляр типа `Person` к типу `Employee`. Иными словами, он позволяет обрабатывать «p» как тип `Employee`.  
  
 Оператор TREAT используется в сценариях наследования, в которых можно выполнить запрос наподобие следующего.  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)   
```  
  
 Этот запрос приводит сущности `Person` к типу `Employee` . Если значение «p» фактически не относится к типу `Employee`, то выражение имеет значение `null`.  
  
> [!NOTE]
> Указанное выражение `Employee` должно быть подтипом указанного типа `Person`данных, либо тип данных должен быть подтипом выражения. В противном случае это выражение вызовет ошибку во время компиляции.  
  
 Следующая таблица показывает, каким образом оператор TREAT работает с некоторыми стандартными и не очень часто используемыми конструкциями. Все исключения формируются на стороне клиента перед вызовом поставщика.  
  
|Шаблон|Поведение|  
|-------------|--------------|  
|`TREAT (null AS EntityType)`|Возвращает `DbNull`.|  
|`TREAT (null AS ComplexType)`|Создает исключение.|  
|`TREAT (null AS RowType)`|Создает исключение/|  
|`TREAT (EntityType AS EntityType)`|Возвращает значение `EntityType` или `null`.|  
|`TREAT (ComplexType AS ComplexType)`|Создает исключение.|  
|`TREAT (RowType AS RowType)`|Создает исключение.|  
  
## <a name="example"></a>Пример  
 В следующем запросе [!INCLUDE[esql](../../../../../../includes/esql-md.md)] оператор TREAT используется для преобразования объекта типа Course в коллекцию объектов типа OnsiteCourse. Запрос основан на [модели School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)).  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
- [Допускающие значения NULL структурированные типы](nullable-structured-types-entity-sql.md)
