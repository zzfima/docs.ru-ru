---
title: "LINQ и ADO.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec
caps.latest.revision: "8"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 9781d97a133a39a7768c853ce80f7524db87df39
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="linq-and-adonet"></a>LINQ и ADO.NET
В настоящее время многие разработчики бизнес-приложений должны использовать два (или более) языка программирования: язык высокого уровня для бизнес-логики и уровней представления (такой как [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] или [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]) и язык запросов для взаимодействия с базой данных (такой как [!INCLUDE[tsql](../../../../includes/tsql-md.md)]). Для эффективной работы разработчик должен хорошо владеть несколькими языками, кроме того, возникают несоответствия между языками в среде разработки. Например, приложение, которое использует API для доступа к данным, чтобы выполнить запрос к базе данных, указывает запрос как строковый литерал в кавычках. Такая строка запроса не читается компилятором и не проверяется на наличие синтаксических ошибок или наличие используемых строк или столбцов. Нет проверки соответствия типов параметров запроса и технологии `IntelliSense`.  
  
 [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] позволяет разработчикам формировать в программном коде запросы, основанные на наборах, без использования дополнительного языка запросов. Можно писать запросы [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] к различным перечислимым источникам данных (источникам данных, которые реализуют интерфейс <xref:System.Collections.IEnumerable>), таким как хранимые в памяти структуры данных, XML-документы, базы данных SQL и объекты <xref:System.Data.DataSet>. Несмотря на то что эти перечислимые источники данных реализованы различными способами, во всех них используется одинаковый синтаксис и языковые конструкции. Из-за того что запросы могут быть сформированы на языке программирования, нет необходимости использовать другой язык запросов, внедренный в виде строковых литералов, которые не могут быть проверены компилятором. Встраивание запросов в язык программирования позволяет программистам, использующим среду [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], быть более продуктивными, предоставляя им проверку синтаксиса и соответствия типов во время компиляции и возможности технологии `IntelliSense`. Эти функции уменьшают затраты на отладку запросов и поиск ошибок.  
  
 Передача данных из таблиц SQL в объекты в памяти часто бывает сложной и способствует совершению ошибок. Поставщик [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], реализованный в [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] и [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)], преобразует исходные данные в данные, основанные на коллекции объектов, реализующих интерфейс <xref:System.Collections.IEnumerable>. Программист всегда видит данные как коллекции <xref:System.Collections.IEnumerable> как при запросе, так и при обновлении. Для написания запросов к этим коллекциям предоставлена полная поддержка технологии `IntelliSense`.  
  
 Существуют три отдельные технологии ADO.NET [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]: [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] и [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)]. Технология [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] обеспечивает расширенные и оптимизированные запросы к <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] позволяет запрашивать непосредственно схемы базы данных [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)], а [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)] позволяет выполнять запросы к [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)].  
  
 На следующей схеме даны общие сведения о связи технологий ADO.NET LINQ с высокоуровневыми языками программирования и источниками данных с поддержкой LINQ.  
  
 ![LINQ на обзор ADO.NET](../../../../docs/framework/data/adonet/media/dpue-linqtoadonetoverview-bpuedev11.gif "DPUE_LinqToAdoNetOverview_bpuedev11")  
  
 Общие сведения о возможностях языка LINQ см. в разделе [введение в LINQ](http://msdn.microsoft.com/library/24dddf19-12a0-4707-a4bc-eba4fa7f219e). Сведения об использовании LINQ в приложениях см. в разделе [не в СБОРКЕ: LINQ общее руководство по программированию](http://msdn.microsoft.com/en-us/609c7a6b-cbdd-429d-99f3-78d13d3bc049), которая содержит подробные сведения о том, как использовать технологии LINQ.  
  
 В следующих подразделах приведены дополнительные сведения о технологиях [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] и [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)].  
  
## <a name="linq-to-dataset"></a>LINQ to DataSet  
 <xref:System.Data.DataSet> является важнейшим и широко используемым элементом модели программирования с кэшированием данных, на основе которой построен [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]. Технология [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] позволяет разработчикам создавать более функциональные запросы к <xref:System.Data.DataSet> с помощью механизма формирования запросов, который поддерживается для множества других источников данных. Дополнительные сведения см. в разделе [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md).  
  
## <a name="linq-to-sql"></a>LINQ to SQL  
 [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] - удобный инструмент для разработчиков, которым необязательно сопоставление с концептуальной моделью. Использование [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] дает возможность напрямую использовать модель программирования [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] с существующей схемой базы данных. [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] позволяет разработчикам формировать классы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для представления данных. Вместо сопоставления с концептуальной моделью эти созданные классы указывают напрямую на таблицы базы данных, представления, хранимые процедуры и определяемые пользователем функции.  
  
 С помощью [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] можно писать код, направленный прямо к схеме хранилища, используя те же программные шаблоны [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)], что и для коллекций в памяти и <xref:System.Data.DataSet>, а также к другим источникам данных, таким как XML. Дополнительные сведения см. в разделе [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).  
  
## <a name="linq-to-entities"></a>LINQ to Entities  
 Большинство приложений на данный момент создаются на основе реляционных баз данных. Этим приложениям необходимо взаимодействовать с данными, представленными в реляционном виде. Схемы баз данных не всегда идеально подходят для создания приложений, а концептуальные модели приложений не всегда совпадают с логическими моделями баз данных. [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] представляет собой концептуальную модель данных, которую можно использовать для моделирования данных конкретного домена, что позволяет приложениям взаимодействовать с данными как с объектами. В разделе [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) для получения дополнительной информации.  
  
 В модели [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] реляционные данные представлены в виде объектов в среде .NET. Благодаря этому поддержка [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] эффективно реализуется на уровне объектов, что позволяет составлять запросы баз данных на языке, используемом для сборки бизнес-логики. Эта функция называется [!INCLUDE[linq_entities](../../../../includes/linq-entities-md.md)]. Дополнительные сведения см. в разделе [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md).  
  
## <a name="see-also"></a>См. также  
 [LINQ to DataSet](../../../../docs/framework/data/adonet/linq-to-dataset.md)  
 [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)  
 [LINQ to Entities](../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)  
 [Встроенный язык запросов LINQ](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
