---
title: Результаты запроса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bcd7b699-4e50-4523-8c33-2f54a103d94e
ms.openlocfilehash: 3ac80cfe06f8531dcd2343f676a6f78f8eb0e8f6
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854306"
---
# <a name="query-results"></a>Результаты запроса
После преобразования LINQ to Entities запроса в деревья команд и выполнения результаты запроса обычно возвращаются в виде одного из следующих значений:  
  
- Коллекция из нуля или большего числа типизированных объектов сущностей или проекция сложных типов в концептуальной модели.  
  
- Типы CLR, поддерживаемые концептуальной моделью.  
  
- Встроенные коллекции.  
  
- Анонимные типы.  
  
 При выполнении запроса к источнику данных результаты материализуются в типы CLR и возвращаются клиенту. Вся материализация объектов проводится платформой Entity Framework. Все ошибки, вызванные невозможностью сопоставления между платформой Entity Framework и средой CLR, вызовут создание исключений во время материализации объекта.
  
 Если выполнение запроса возвращает примитивные типы концептуальной модели, результаты состоят из типов CLR, которые являются изолированными и отключены от Entity Framework. Однако если запрос вернул коллекцию типизированных объектов сущностей, представленных <xref:System.Data.Objects.ObjectQuery%601>, то эти типы отслеживаются контекстом объекта. Все поведение объектов (таких как дочерние и родительские коллекции, отслеживание изменений, полиморфизм и т. д.) задается в Entity Framework. Эту функцию можно использовать в своей емкости, как определено в Entity Framework. Дополнительные сведения см. в разделе [Работа с объектами](../working-with-objects.md).
  
 Типы структур, возвращаемые из запросов (например, анонимные и сложные типы, допускающие значение null), могут иметь значение `null`. Свойство <xref:System.Data.Objects.DataClasses.EntityCollection%601> возвращаемой сущности также может иметь значение `null`. Это может произойти в результате проецирования свойства коллекции для сущности, имеющей значение `null`, например, при вызове метода <xref:System.Linq.Queryable.FirstOrDefault%2A> для объекта <xref:System.Data.Objects.ObjectQuery%601>, который не содержит элементов.  
  
 В некоторых ситуациях может показаться, что запрос создает материализованный результат во время выполнения, но в действительности запрос будет выполняться на сервере и объект сущности никогда не окажется материализован в среде CLR. Это может вызвать проблемы, если приложение рассчитывает на побочные эффекты материализации.  
  
 В следующем примере имеется пользовательский класс `MyContact` со свойством `LastName`. При присваивании значения свойству `LastName` переменная `count` увеличивается на единицу. Если выполнить два приведенных ниже запроса, то первый запрос увеличит значение `count` на единицу, а второй - нет. Причина этого заключается в том, что во втором запросе свойство `LastName` спроецировано из результатов, а класс `MyContact` не создается, поскольку он не является необходимым для выполнения запроса в хранилище.  
  
 [!code-csharp[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#materializationsideeffects)]
 [!code-vb[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#materializationsideeffects)]  
  
 [!code-csharp[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#mycontactclass)]
 [!code-vb[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#mycontactclass)]
