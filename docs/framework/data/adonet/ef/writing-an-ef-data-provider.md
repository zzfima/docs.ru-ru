---
title: Создание поставщика данных Entity Framework
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 29aa8cb1c6b31d9ada6b01860d76bcf03d37416c
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854159"
---
# <a name="writing-an-entity-framework-data-provider"></a>Создание поставщика данных Entity Framework
В этом разделе описывается написание поставщика Entity Framework для поддержки источника данных, отличного от SQL Server. Entity Framework содержит поставщик, поддерживающий SQL Server.  
  
## <a name="introducing-the-entity-framework-provider-model"></a>Знакомство с моделью поставщика Entity Framework  
 Entity Framework не зависит от базы данных, и вы можете написать поставщик с помощью модели поставщика ADO.NET для подключения к широкому набору источников данных.  
  
 Поставщик данных Entity Framework (созданный при помощи модели поставщика ADO.NET) выполняет следующие функции.  
  
- Сопоставляет примитивные типы модели EDM с типами поставщика.  
  
- Предоставляет функции данного поставщика.  
  
- Создает специальные команды поставщика для данного Дбкуерикоммандтри для поддержки запросов Entity Framework.  
  
- Создает специфические для поставщика команды обновления для данного DbModificationCommandTree для поддержки обновлений с помощью Entity Framework.  
  
- Предоставляет файлы сопоставления для определения схемы хранения для поддержки создания основанной на базе данных модели.  
  
- Предоставляет метаданные (например, таблицы и представления) посредством концептуальной модели.  
  
 ![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")  
  
## <a name="sample"></a>Пример  
 Пример поставщика Entity Framework, который поддерживает источник данных, отличный от SQL Server, см. в [Entity Framework примере поставщика](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) .  
  
## <a name="in-this-section"></a>В этом разделе  
 [Создание SQL](sql-generation.md)  
  
 [Создание кода SQL для изменения данных](modification-sql-generation.md)  
  
 [Спецификация манифеста поставщика](provider-manifest-specification.md)  
  
## <a name="see-also"></a>См. также

- [Работа с поставщиками данных](working-with-data-providers.md)
