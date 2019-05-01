---
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: 736b92f7aac89c309b37a8ac61a295c8d1495d6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034106"
---
# <a name="union-entity-sql"></a>UNION (Entity SQL)
Сводит результаты двух или более запросов в одну коллекцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression  
UNION [ ALL ]  
expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение запроса, возвращающее коллекцию для объединения с данной коллекцией. Все выражения должны быть одного типа с параметром `expression`либо базового или производного типа для типа этого параметра.  
  
 UNION  
 Указывает на то, что несколько коллекций следует объединить и возвратить в виде единой коллекции.  
  
 ALL  
 Указывает на то, что несколько коллекций следует объединить и возвратить в виде единой коллекции, включая повторения. Если этот аргумент не указан, то повторения удаляются из итоговой коллекции.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Коллекция того же типа, что и параметр `expression`, или же базового или производного типа для типа этого параметра.  
  
## <a name="remarks"></a>Примечания  
 UNION - это один из операторов работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо. Сведения о порядке выполнения [!INCLUDE[esql](../../../../../../includes/esql-md.md)] операторы работы с наборами, см. в разделе [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL оператор UNION ALL используется, чтобы объединить результаты двух запросов в единую коллекцию. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру, описанную в [как: Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#UNION](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#union)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
