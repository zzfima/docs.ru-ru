---
title: UNION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
ms.openlocfilehash: a5a20beb0ab55dcbaf2dbbb75801b50ab9ef6722
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319220"
---
# <a name="union-entity-sql"></a>UNION (Entity SQL)
Сводит результаты двух или более запросов в одну коллекцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```sql  
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
  
## <a name="remarks"></a>Заметки  
 UNION - это один из операторов работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо. Сведения о приоритетах для операторов установки [!INCLUDE[esql](../../../../../../includes/esql-md.md)] см. в разделе [except](except-entity-sql.md).  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL оператор UNION ALL используется, чтобы объединить результаты двух запросов в единую коллекцию. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1. Выполните процедуру из статьи [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2. Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-sql[DP EntityServices Concepts#UNION](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#union)]  
  
## <a name="see-also"></a>См. также

- [Справочник по Entity SQL](entity-sql-reference.md)
