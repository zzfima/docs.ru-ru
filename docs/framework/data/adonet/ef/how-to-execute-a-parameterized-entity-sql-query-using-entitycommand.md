---
title: "Практическое руководство. Выполнение параметризованного запроса Entity SQL с использованием EntityCommand"
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
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d43be857e4f920a1ce36625d9be207b9025ff423
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a>Практическое руководство. Выполнение параметризованного запроса Entity SQL с использованием EntityCommand
В этом разделе показано выполнение [!INCLUDE[esql](../../../../../includes/esql-md.md)] запрос с параметрами с помощью <xref:System.Data.EntityClient.EntityCommand> объекта.  
  
### <a name="to-run-the-code-in-this-example"></a>Выполнение кода в этом примере  
  
1.  Добавить [модели AdventureWorks Sales](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) в проект и настроить проект для использования [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Дополнительные сведения см. в разделе [как: использовать мастер моделей EDM](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  На странице кода приложения добавьте следующие инструкции `using` (`Imports` в Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Пример  
 Следующий пример показывает, как создать строку запроса с двумя параметрами. Затем создается объект <xref:System.Data.EntityClient.EntityCommand>, добавляются два параметра в коллекцию <xref:System.Data.EntityClient.EntityParameter> этого объекта <xref:System.Data.EntityClient.EntityCommand> и совершается проход по элементам коллекции объектов `Contact`.  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## <a name="see-also"></a>См. также  
 [Как: выполнение параметризованного запроса](http://msdn.microsoft.com/library/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
 [Язык Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
