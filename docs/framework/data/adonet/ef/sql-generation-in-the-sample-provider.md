---
title: Создание кода SQL в образце поставщика
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: 88223930b65ccec9d030104c62d8b4b2e77ddbe2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879298"
---
# <a name="sql-generation-in-the-sample-provider"></a>Создание кода SQL в образце поставщика
[Образца поставщика Entity Framework](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) демонстрируются новые компоненты поставщиков данных ADO.NET, которые поддерживают [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Он работает с базой данных SQL Server 2005 и реализуется в виде оболочки для поставщика данных System.Data.SqlClient ADO.NET 2.0.  
  
 Модуль создания кода SQL в образце поставщика (расположенный в папке создания SQL, за исключением файла DmlSqlGenerator.cs) принимает входной аргумент DbQueryCommandTree и создает одну инструкцию SQL SELECT.  
  
## <a name="in-this-section"></a>В этом разделе  
 Этот раздел содержит следующие подразделы:  
  
 [Архитектура и разработка](../../../../../docs/framework/data/adonet/ef/architecture-and-design.md)  
  
 [Пошаговое руководство: Создание кода SQL](../../../../../docs/framework/data/adonet/ef/walkthrough-sql-generation.md)  
  
## <a name="see-also"></a>См. также

- [Создание SQL](../../../../../docs/framework/data/adonet/ef/sql-generation.md)
