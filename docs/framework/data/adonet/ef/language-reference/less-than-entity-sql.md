---
title: '&lt; (меньше) (Entity SQL)'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1fc2a039-3ad6-4b3c-b41d-09932e803f86
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 5bf1560c0bebafcfdbf79ca9a9906c9df23b7cae
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="lt-less-than-entity-sql"></a>&lt; (меньше) (Entity SQL)
Сравнивает два выражения, чтобы определить, является ли значение левого выражения меньшим, чем значение правого выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
expression < expression  
```  
  
## <a name="arguments"></a>Аргументы  
 `expression`  
 Любое допустимое выражение. Оба выражения должны иметь типы данных, допускающих неявное преобразование.  
  
## <a name="result-types"></a>Типы результата  
 `true` , если значение левого выражения меньше, чем правого; в противном случае - `false`.  
  
## <a name="example"></a>Пример  
 В следующем запросе Entity SQL оператор < используется для сравнения двух выражений, чтобы определить, является ли значение левого выражения меньшим, чем правого. Запрос основан на модели AdventureWorks Sales. Для компиляции и запуска этого запроса выполните следующие шаги.  
  
1.  Выполните процедуру из статьи [Практическое руководство. Выполнение запроса, возвращающего результаты StructuralType](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Передайте следующий запрос в качестве аргумента методу `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
