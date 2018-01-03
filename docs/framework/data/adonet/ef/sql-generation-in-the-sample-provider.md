---
title: "Создание кода SQL в образце поставщика"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 853bf55f96be3adeba11ff14e36fd56631536b69
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="sql-generation-in-the-sample-provider"></a>Создание кода SQL в образце поставщика
[Образца поставщика Entity Framework](http://go.microsoft.com/fwlink/?LinkId=180616) демонстрируются новые компоненты поставщиков данных ADO.NET, который поддерживает [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Он работает с базой данных SQL Server 2005 и реализуется в виде оболочки для поставщика данных System.Data.SqlClient ADO.NET 2.0.  
  
 Модуль создания кода SQL в образце поставщика (расположенный в папке создания SQL, за исключением файла DmlSqlGenerator.cs) принимает входной аргумент DbQueryCommandTree и создает одну инструкцию SQL SELECT.  
  
## <a name="in-this-section"></a>Содержание  
 Этот раздел содержит следующие подразделы:  
  
 [Архитектура и разработка](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [Пошаговое руководство. Создание кода SQL](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a>См. также  
 [Создание SQL](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
