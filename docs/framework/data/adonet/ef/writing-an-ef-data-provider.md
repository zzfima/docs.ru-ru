---
title: Создание поставщика данных Entity Framework
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 513af001392ae0b7abe8e6c62dc74f09469b3655
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2018
ms.locfileid: "52296637"
---
# <a name="writing-an-entity-framework-data-provider"></a>Создание поставщика данных Entity Framework
В этом разделе описывается порядок написания [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] поставщика для поддержки источника данных, отличного от SQL Server. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Включает поставщика, который поддерживает SQL Server.  
  
## <a name="introducing-the-entity-framework-provider-model"></a>Знакомство с моделью поставщика Entity Framework  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] не зависит от баз данных, написать поставщика для подключения к различным источникам данных можно при помощи модели поставщика ADO.NE.  
  
 Поставщик данных Entity Framework (созданный при помощи модели поставщика ADO.NET) выполняет следующие функции.  
  
-   Сопоставляет примитивные типы модели EDM с типами поставщика.  
  
-   Предоставляет функции данного поставщика.  
  
-   Создает команды определенного поставщика для поддержки запросов [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] в данном DbQueryCommandTree.  
  
-   Формирует команды обновления для определенного поставщика для поддержки обновлений через [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] в данном DbModificationCommandTree.  
  
-   Предоставляет файлы сопоставления для определения схемы хранения для поддержки создания основанной на базе данных модели.  
  
-   Предоставляет метаданные (например, таблицы и представления) посредством концептуальной модели.  
  
 ![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")  
  
## <a name="sample"></a>Пример  
 См. в разделе [образца поставщика Entity Framework](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) пример [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] поставщика, поддерживающего источника данных, отличного от SQL Server.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Создание SQL](../../../../../docs/framework/data/adonet/ef/sql-generation.md)  
  
 [Создание кода SQL для изменения данных](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)  
  
 [Спецификация манифеста поставщика](../../../../../docs/framework/data/adonet/ef/provider-manifest-specification.md)  
  
## <a name="see-also"></a>См. также  
 [Работа с поставщиками данных](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)
