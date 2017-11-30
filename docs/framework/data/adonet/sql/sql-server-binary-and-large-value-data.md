---
title: "Двоичные данные и данные большого объема SQL Server"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9065f467cd353c17471db2c0d67001a188459819
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="sql-server-binary-and-large-value-data"></a>Двоичные данные и данные большого объема SQL Server
В SQL Server появился описатель `max`, расширяющий возможности хранения типов данных `varchar`, `nvarchar` и `varbinary`. `varchar(max)`, `nvarchar(max)`, и `varbinary(max)` называются *типы данных больших значений*. Типы данных большого размера можно использовать для хранения данных размером до 2^31-1 байт.  
  
 В SQL Server 2008 появился атрибут FILESTREAM, который является не типом данных, а определяемым для столбца атрибутом, позволяющим хранить данные большого размера не в базе данных, а в файловой системе.  
  
## <a name="in-this-section"></a>Содержание  
 [Изменение данных большого объема (max) в ADO.NET](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 Содержит описание работы с большими типами данных.  
  
 [Данные FILESTREAM](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 Описывается работа с данными большого размера, хранящимися в SQL Server 2008 с указанием атрибута FILESTREAM.  
  
## <a name="see-also"></a>См. также  
 [Типы данных SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [Операции данных SQL Server Data в ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [Извлечение и изменение данных в ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
