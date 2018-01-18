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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 7a7f95f7432fdac00a34e7d878ef979656a7af4e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
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
