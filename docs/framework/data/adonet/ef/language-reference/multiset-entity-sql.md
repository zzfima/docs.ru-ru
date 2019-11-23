---
title: MULTISET (Entity SQL)
ms.date: 03/30/2017
ms.assetid: eb90a377-e47a-43a5-b308-e993b6d611e6
ms.openlocfilehash: 222be86db434b5d41c7b0536d271a3750b6afbe8
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319586"
---
# <a name="multiset-entity-sql"></a>MULTISET (Entity SQL)
Создает экземпляр мультинабора из списка значений. Все значения конструктора MULTISET должны принадлежать совместимому типу `T`. Применение пустых конструкторов мультинаборов не допускается.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
MULTISET ( expression [{, expression }] )  
-- or  
{ expression [{, expression }] }  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любой допустимый список значений.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Коллекция МУЛЬТИНАБОРов типов\<T >.  
  
## <a name="remarks"></a>Примечания  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] предоставляет три типа конструкторов: конструкторы строк, конструкторы объектов и конструкторы мультинаборов (или коллекций). Дополнительные сведения см. в разделе [Создание типов](constructing-types-entity-sql.md).  
  
 Конструктор мультинаборов создает экземпляр мультинабора из списка значений. Все значения конструктора MULTISET должны принадлежать совместимому типу.  
  
 Например, следующее выражение создает мультинабор целых чисел.  
  
 `MULTISET(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
> [!NOTE]
> Вложенные литералы мультинабора поддерживаются только в том случае, если в Мультинаборе с несколькими элементами есть один элемент мультинабора; Например, `{{1, 2, 3}}`. Когда же мультинабор-упаковщик имеет несколько элементов мультинабора (например, `{{1, 2}, {3, 4}}`), вложенные литералы мультинаборов не поддерживаются.  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL оператор MULTISET используется для создания экземпляра мультинабора из списка значений. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#MULTISET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#multiset)]  
  
## <a name="see-also"></a>См. также:

- [Сборка типов](constructing-types-entity-sql.md)
- [Справочник по Entity SQL](entity-sql-reference.md)
