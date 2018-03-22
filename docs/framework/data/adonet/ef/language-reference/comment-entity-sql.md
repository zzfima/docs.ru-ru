---
title: -- (комментарий) (Entity SQL)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 1ed1c70687b1a4aec542aff5046b237fa4710fa4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="---comment-entity-sql"></a>-- (комментарий) (Entity SQL)
Запросы[!INCLUDE[esql](../../../../../../includes/esql-md.md)] могут содержать комментарии. Строка комментария начинается с двух дефисов (`--`).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a>Аргументы  
 `text_of_comment`  
 Строка символов, содержащая текст комментария.  
  
## <a name="example"></a>Пример  
 Следующий запрос Entity SQL демонстрирует использование комментариев. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
