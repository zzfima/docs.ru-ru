---
title: Создание SQL
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 108a68f74849c7fa1418775c2a37db06d9d947ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879156"
---
# <a name="sql-generation"></a>Создание SQL
При написании поставщика для [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] необходимо перевести дерево команд [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] на язык SQL, понятный базе данных, например Transact-SQL для SQL Server или PL/SQL для Oracle. В этом разделе описано, как разрабатывать компонент создания кода SQL (для запросов SELECT) для поставщика [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Дополнительные сведения о вставке обновить и удаление запросов, см. в разделе [создание кода SQL для изменения](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md).  
  
 Для усвоения данного раздела требуется знание [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] и модели поставщика ADO.NET. Также требуется знание деревьев команд и <xref:System.Data.Common.CommandTrees.DbExpression>.  
  
## <a name="the-role-of-the-sql-generation-module"></a>Роль модуля создания кода SQL  
 Модуль создания кода SQ поставщика [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] переводит данное дерево команд запроса в одну инструкцию SQL SELECT, предназначенную для базы данных, которая совместима с SQL:1999. В созданном коде SQL должно как можно меньше вложенных запросов. Упрощение дерева команд выходного запроса в модуле создания кода SQL не допускается. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] может с этой целью, например, удалить соединения и свернуть последовательные узлы фильтра.  
  
 Класс <xref:System.Data.Common.DbProviderServices> является начальной точкой для доступа к уровню создания кода SQL для преобразования деревьев команд в <xref:System.Data.Common.DbCommand>.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Форма деревьев команд](../../../../../docs/framework/data/adonet/ef/the-shape-of-the-command-trees.md)  
  
 [Создание кода SQL из деревьев команд. Рекомендации](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md)  
  
 [Создание кода SQL в образце поставщика](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a>См. также

- [Создание поставщика данных Entity Framework](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
