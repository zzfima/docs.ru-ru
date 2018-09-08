---
title: Двоичные данные и данные большого объема SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: 9ebbe23dfbcac7825ce449dd40f62b921d13ab4a
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44209164"
---
# <a name="sql-server-binary-and-large-value-data"></a>Двоичные данные и данные большого объема SQL Server
В SQL Server появился описатель `max`, расширяющий возможности хранения типов данных `varchar`, `nvarchar` и `varbinary`. `varchar(max)`, `nvarchar(max)`, и `varbinary(max)` называются *типы данных больших значений*. Типы данных большого размера можно использовать для хранения данных размером до 2^31-1 байт.  
  
 В SQL Server 2008 появился атрибут FILESTREAM, который является не типом данных, а определяемым для столбца атрибутом, позволяющим хранить данные большого размера не в базе данных, а в файловой системе.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Изменение данных больших объемов (max) в ADO.NET](../../../../../docs/framework/data/adonet/sql/modifying-large-value-max-data.md)  
 Содержит описание работы с большими типами данных.  
  
 [Данные FILESTREAM](../../../../../docs/framework/data/adonet/sql/filestream-data.md)  
 Описывается работа с данными большого размера, хранящимися в SQL Server 2008 с указанием атрибута FILESTREAM.  
  
## <a name="see-also"></a>См. также  
 [Типы данных SQL Server и ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [Операции данных SQL Server Data в ADO.NET](../../../../../docs/framework/data/adonet/sql/sql-server-data-operations.md)  
 [Извлечение и изменение данных в ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
