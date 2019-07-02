---
title: LINQ и ADO.NET
ms.date: 03/30/2017
ms.assetid: bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec
ms.openlocfilehash: 16b06549573bc79378539cf7f5ccdcb60c812e81
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504464"
---
# <a name="linq-and-adonet"></a>LINQ и ADO.NET
В настоящее время многие разработчики бизнес-приложений должны использовать два (или более) языка программирования: язык высокого уровня для бизнес-логики и презентации уровней (например Visual C# или Visual Basic) и язык запросов для взаимодействия с базой данных (например, Transact-SQL) . Для эффективной работы разработчик должен хорошо владеть несколькими языками, кроме того, возникают несоответствия между языками в среде разработки. Например, приложение, которое использует API для доступа к данным, чтобы выполнить запрос к базе данных, указывает запрос как строковый литерал в кавычках. Такая строка запроса не читается компилятором и не проверяется на наличие синтаксических ошибок или наличие используемых строк или столбцов. Нет проверки соответствия типов параметров запроса и технологии `IntelliSense`.  
  
 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] позволяет разработчикам формировать в программном коде запросы, основанные на наборах, без использования дополнительного языка запросов. Можно писать запросы [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] к различным перечислимым источникам данных (источникам данных, которые реализуют интерфейс <xref:System.Collections.IEnumerable>), таким как хранимые в памяти структуры данных, XML-документы, базы данных SQL и объекты <xref:System.Data.DataSet>. Несмотря на то что эти перечислимые источники данных реализованы различными способами, во всех них используется одинаковый синтаксис и языковые конструкции. Из-за того что запросы могут быть сформированы на языке программирования, нет необходимости использовать другой язык запросов, внедренный в виде строковых литералов, которые не могут быть проверены компилятором. Встраивание запросов в язык программирования позволяет программистам работать более производительно, предоставляя типов во время компиляции и проверки синтаксиса, Visual Studio и `IntelliSense`. Эти функции уменьшают затраты на отладку запросов и поиск ошибок.  
  
 Передача данных из таблиц SQL в объекты в памяти часто бывает сложной и способствует совершению ошибок. [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] Поставщика, реализуемый LINQ to DataSet и [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] преобразует исходные данные в <xref:System.Collections.IEnumerable>-на основе коллекций объектов. Программист всегда видит данные как коллекции <xref:System.Collections.IEnumerable> как при запросе, так и при обновлении. Для написания запросов к этим коллекциям предоставлена полная поддержка технологии `IntelliSense`.  
  
 Существуют три отдельные технологии ADO.NET [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]: LINQ to DataSet, [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)], и [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)]. LINQ to DataSet предоставляет расширенные и оптимизированные запросы к <xref:System.Data.DataSet> и [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] позволяет непосредственно запрашивать схемы баз данных SQL Server, и [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)] позволяет выполнять запросы к модели EDM.  
  
 На следующей схеме даны общие сведения о связи технологий ADO.NET LINQ с высокоуровневыми языками программирования и источниками данных с поддержкой LINQ.  
  
 ![LINQ к обзору ADO.NET](../../../../docs/framework/data/adonet/media/dpue-linqtoadonetoverview-bpuedev11.gif "DPUE_LinqToAdoNetOverview_bpuedev11")  
  
 Дополнительные сведения о LINQ см. в разделе [Language Integrated Query (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md).
  
 В следующих разделах Дополнительные сведения о LINQ to DataSet, [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)], и [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)].  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> — Это ключевой элемент модели автономного программирования, который выполняется на основе ADO.NET и широко используется. LINQ to DataSet позволяет разработчикам создавать расширенные возможности запросов в <xref:System.Data.DataSet> с помощью механизма составления запросов, доступный для многих других источников данных. Дополнительные сведения см. в разделе [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] - удобный инструмент для разработчиков, которым необязательно сопоставление с концептуальной моделью. Использование [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] дает возможность напрямую использовать модель программирования [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] с существующей схемой базы данных. [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] Разработчики могут создавать классы .NET Framework, которые представляют данные. Вместо сопоставления с концептуальной моделью эти созданные классы указывают напрямую на таблицы базы данных, представления, хранимые процедуры и определяемые пользователем функции.  
  
 С помощью [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] можно писать код, направленный прямо к схеме хранилища, используя те же программные шаблоны [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], что и для коллекций в памяти и <xref:System.Data.DataSet>, а также к другим источникам данных, таким как XML. Дополнительные сведения см. в разделе [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 Большинство приложений на данный момент создаются на основе реляционных баз данных. Этим приложениям необходимо взаимодействовать с данными, представленными в реляционном виде. Схемы баз данных не всегда идеально подходят для создания приложений, а концептуальные модели приложений не всегда совпадают с логическими моделями баз данных. Модель EDM — это концептуальная модель данных, можно использовать для моделирования данных определенного домена, чтобы приложения могли взаимодействовать с данными как объектами. См. в разделе [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) Дополнительные сведения.  
  
 Через модель EDM реляционные данные представлены в виде объектов в среде .NET. Благодаря этому поддержка [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] эффективно реализуется на уровне объектов, что позволяет составлять запросы баз данных на языке, используемом для сборки бизнес-логики. Эта функция называется [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)]. Дополнительные сведения см. в разделе [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>См. также

- [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md)
- [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)
- [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
- [LINQ](../../../csharp/programming-guide/concepts/linq/index.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
