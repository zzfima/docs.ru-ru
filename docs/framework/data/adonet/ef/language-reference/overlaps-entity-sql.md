---
title: OVERLAPS (Entity SQL)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 22593af3f79e78621764ba293e65505a72b194f8
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="overlaps-entity-sql"></a>OVERLAPS (Entity SQL)
Определяет, содержат ли две коллекции общие элементы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение запроса, которое возвращает коллекцию для сравнения с коллекцией, возвращенной другим выражением запроса. Все выражения должны иметь тот же тип, что и аргумент `expression`, или принадлежать к базовому или производному типу для типа этого аргумента.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true` , если две коллекции содержат общие элементы; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 OVERLAPS функционально эквивалентен следующее:  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 Оператор OVERLAPS - это один из операторов работы с наборами в языке [!INCLUDE[esql](../../../../../../includes/esql-md.md)] . Все операторы работы с наборами [!INCLUDE[esql](../../../../../../includes/esql-md.md)] выполняются слева направо. Сведения о порядке выполнения [!INCLUDE[esql](../../../../../../includes/esql-md.md)] операторов работы с наборами см. в разделе [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md).  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL оператор OVERLAPS используется для определения, имеют ли две коллекции общее значение. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#OVERLAPS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#overlaps)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
