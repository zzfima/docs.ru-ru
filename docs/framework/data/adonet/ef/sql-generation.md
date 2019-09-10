---
title: Создание SQL
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 9c5301d3f4d5bc2e0db4a138c6d8ceb06d3a7845
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854354"
---
# <a name="sql-generation"></a>Создание SQL
При написании поставщика Entity Framework необходимо преобразовать деревья команд Entity Framework в SQL, которые может распознать конкретная база данных, например Transact-SQL для SQL Server или PL/SQL для Oracle. В этом разделе вы узнаете, как разработать компонент создания SQL (для запросов SELECT) для поставщика Entity Framework. Дополнительные сведения о вставке, обновлении и удалении запросов см. в разделе [изменение создания SQL](modification-sql-generation.md).  
  
 Чтобы понять этот раздел, необходимо ознакомиться с Entity Framework и моделью поставщика ADO.NET. Также требуется знание деревьев команд и <xref:System.Data.Common.CommandTrees.DbExpression>.  
  
## <a name="the-role-of-the-sql-generation-module"></a>Роль модуля создания кода SQL  
 Модуль создания SQL поставщика Entity Framework преобразует заданное дерево команд запроса в одну инструкцию SQL SELECT, предназначенную для базы данных SQL: 1999. В созданном коде SQL должно как можно меньше вложенных запросов. Упрощение дерева команд выходного запроса в модуле создания кода SQL не допускается. Entity Framework сделает это, например, исключив объединения и свертывание последовательных узлов фильтров.  
  
 Класс <xref:System.Data.Common.DbProviderServices> является начальной точкой для доступа к уровню создания кода SQL для преобразования деревьев команд в <xref:System.Data.Common.DbCommand>.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Форма деревьев команд](the-shape-of-the-command-trees.md)  
  
 [Создание кода SQL из деревьев команд. Рекомендации](generating-sql-from-command-trees-best-practices.md)  
  
 [Создание кода SQL в образце поставщика](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a>См. также

- [Создание поставщика данных Entity Framework](writing-an-ef-data-provider.md)
