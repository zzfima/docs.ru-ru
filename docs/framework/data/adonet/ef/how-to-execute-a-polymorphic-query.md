---
title: "Практическое руководство. Выполнение полиморфного запроса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3f2a51276568371c48647557f286ec60ac6531b7
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-execute-a-polymorphic-query"></a>Практическое руководство. Выполнение полиморфного запроса
В этом разделе показано выполнение полиморфного [!INCLUDE[esql](../../../../../includes/esql-md.md)] запрос с использованием [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) оператор.  
  
### <a name="to-run-the-code-in-this-example"></a>Выполнение кода в этом примере  
  
1.  Добавить [модели School](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) в проект и настроить проект для использования платформы Entity Framework. Дополнительные сведения см. в разделе [как: использовать мастер моделей EDM](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  Изменить на наследования таблицы на hierrachy, описанные в концептуальной модели [Пошаговое руководство: сопоставление наследования - таблица на иерархию](http://msdn.microsoft.com/library/49b685cf-9db8-4d6d-b885-8837ed238f55).  
  
## <a name="example"></a>Пример  
 В следующем примере используется оператор OFTYPE для возврата и отображения коллекции только элементов `OnsiteCourses` из коллекции `Courses`.  
  
 [!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
 [!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]  
  
## <a name="see-also"></a>См. также  
 [Поставщик EntityClient для Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
 [Язык Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
