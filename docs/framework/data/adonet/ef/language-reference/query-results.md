---
title: "Результаты запроса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: bcd7b699-4e50-4523-8c33-2f54a103d94e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 32133d1b6fce619fb9990ab89820b7f19b6a5926
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="query-results"></a>Результаты запроса
После преобразования запроса [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] в деревья команд и последующего выполнения результаты запроса обычно возвращаются в одной из следующих форм.  
  
-   Коллекция из нуля или большего числа типизированных объектов сущностей или проекция сложных типов в концептуальной модели.  
  
-   Типы CLR, поддерживаемые концептуальной моделью.  
  
-   Встроенные коллекции.  
  
-   Анонимные типы.  
  
 При выполнении запроса к источнику данных результаты материализуются в типы CLR и возвращаются клиенту. Материализация объектов полностью обеспечивается платформой [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]. Любые ошибки, вызванные невозможностью сопоставления объектов платформы [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] и среды CLR, вызовут исключения во время материализации объекта.  
  
 Если в результате выполнения запроса возвращаются типы-примитивы концептуальной модели, то результаты состоят из изолированных типов CLR, которые не связаны с платформой [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]. Однако если запрос вернул коллекцию типизированных объектов сущностей, представленных <xref:System.Data.Objects.ObjectQuery%601>, то эти типы отслеживаются контекстом объекта. Все объекта (например, дочерние и родительские коллекции, отслеживание изменений, полиморфизм и т. д.) выполнятся согласно определениям в [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]. Эти функции можно могут быть использованы в пределах, определяемых [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]. Дополнительные сведения см. в разделе [работа с объектами](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).  
  
 Типы структур, возвращаемые из запросов (например, анонимные и сложные типы, допускающие значение null), могут иметь значение `null`. Свойство <xref:System.Data.Objects.DataClasses.EntityCollection%601> возвращаемой сущности также может иметь значение `null`. Это может произойти в результате проецирования свойства коллекции для сущности, имеющей значение `null`, например, при вызове метода <xref:System.Linq.Queryable.FirstOrDefault%2A> для объекта <xref:System.Data.Objects.ObjectQuery%601>, который не содержит элементов.  
  
 В некоторых ситуациях может показаться, что запрос создает материализованный результат во время выполнения, но в действительности запрос будет выполняться на сервере и объект сущности никогда не окажется материализован в среде CLR. Это может вызвать проблемы, если приложение рассчитывает на побочные эффекты материализации.  
  
 В следующем примере имеется пользовательский класс `MyContact` со свойством `LastName`. При присваивании значения свойству `LastName` переменная `count` увеличивается на единицу. Если выполнить два приведенных ниже запроса, то первый запрос увеличит значение `count` на единицу, а второй - нет. Причина этого заключается в том, что во втором запросе свойство `LastName` спроецировано из результатов, а класс `MyContact` не создается, поскольку он не является необходимым для выполнения запроса в хранилище.  
  
 [!code-csharp[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#materializationsideeffects)]
 [!code-vb[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#materializationsideeffects)]  
  
 [!code-csharp[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#mycontactclass)]
 [!code-vb[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#mycontactclass)]
