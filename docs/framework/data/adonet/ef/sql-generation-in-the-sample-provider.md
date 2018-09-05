---
title: Создание кода SQL в образце поставщика
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: cba1cec6d7ef0fdf8d4d4cf6c8e44fb325cf6447
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556209"
---
# <a name="sql-generation-in-the-sample-provider"></a>Создание кода SQL в образце поставщика
[Образца поставщика Entity Framework](https://go.microsoft.com/fwlink/?LinkId=180616) демонстрируются новые компоненты поставщиков данных ADO.NET, которые поддерживают [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Он работает с базой данных SQL Server 2005 и реализуется в виде оболочки для поставщика данных System.Data.SqlClient ADO.NET 2.0.  
  
 Модуль создания кода SQL в образце поставщика (расположенный в папке создания SQL, за исключением файла DmlSqlGenerator.cs) принимает входной аргумент DbQueryCommandTree и создает одну инструкцию SQL SELECT.  
  
## <a name="in-this-section"></a>Содержание  
 Этот раздел содержит следующие подразделы:  
  
 [Архитектура и разработка](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [Пошаговое руководство. Создание кода SQL](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a>См. также  
 [Создание SQL](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
