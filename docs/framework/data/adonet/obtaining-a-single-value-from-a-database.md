---
title: Получение одного значения из базы данных
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 41c3547d203a9958d3ad84303469c1e9591e6bd3
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2018
---
# <a name="obtaining-a-single-value-from-a-database"></a>Получение одного значения из базы данных
Может возникнуть необходимость вернуть сведения из базы данных, которые представляют собой одиночное значение, а не форму таблицы или поток данных. Например, может потребоваться вернуть результат агрегатной функции, например COUNT (\*), SUM(Price) или AVG(Quantity). **Команда** объект предоставляет возможность возвращать одиночные значения при помощи **ExecuteScalar** метод. **ExecuteScalar** метод возвращает в виде скалярного значения, значение первого столбца первой строки результирующего набора.  
  
 В следующем примере кода в базу данных при помощи <xref:System.Data.SqlClient.SqlCommand> вставляется новое значение. Метод <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> используется, чтобы вернуть значение столбца идентификатора для вставленной записи.  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Выполнение команды](../../../../docs/framework/data/adonet/executing-a-command.md)  
 [DbConnection, DbCommand и DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
