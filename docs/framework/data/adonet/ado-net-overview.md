---
title: Общие сведения о ADO.NET
ms.date: 03/30/2017
ms.assetid: ee3bc1d8-11db-4be4-89eb-c708cf04117d
ms.openlocfilehash: 50881c05c8b6f2602d19817373a16e4661d3d133
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757948"
---
# <a name="adonet-overview"></a>Общие сведения о ADO.NET
ADO.NET предоставляет согласованный доступ к таким источникам данных, как SQL Server и XML, а также к источникам данных, предоставляемым при помощи OLE DB и ODBC. Пользовательские приложения, использующие общие данные, могут использовать ADO.NET для соединения с этими источниками данных и для получения, обработки и обновления имеющихся в них данных.  
  
 ADO.NET разделят доступ к данным и обработку данных на дискретные компоненты, которые могут использоваться отдельно или совместно. ADO.NET включает поставщиков данных .NET Framework для соединения с базой данных, выполнения команд и получения результатов. Эти результаты, помещенные в объект ADO.NET <xref:System.Data.DataSet>, обрабатываются непосредственно, чтобы они могли быть предоставлены пользователю нерегламентированным образом, объединенные с данными из многих источников или передаваемые между уровнями. Объект `DataSet` также может независимо использоваться поставщиком данных .NET Framework для управления локальными для приложения данными или данными, источником которых является XML.  
  
 Классы ADO.NET имеются в System.Data.dll и интегрируются с классами XML, имеющимися в System.Xml.dll. Пример кода, который подключается к базе данных получает данные из него, а затем отображаются в окне консоли, см. в разделе [примеры кода ADO.NET](../../../../docs/framework/data/adonet/ado-net-code-examples.md).  
  
 Для разработчиков, которые пишут управляемый код, ADO.NET предоставляет функциональный набор, сходный с функциональным набором, который предоставляют объекты данных ActiveX (ADO) разработчикам моделей объектов собственных компонентов (COM). Для доступа к данным в приложении .NET мы рекомендуем использовать ADO.NET, а не ADO.  
  
 ADO.NET предоставляет самый прямой способ доступа к данным в .NET Framework. Для более высокого уровня абстракции, который позволяет приложениям работать к концептуальной модели, а не базовой модели хранения, в разделе [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md).  
  
 **Заявление о конфиденциальности**: сборки System.Data.dll, System.Data.Design.dll, System.Data.OracleClient.dll, System.Data.SqlXml.dll, System.Data.Linq.dll, System.Data.SqlServerCe.dll и System.Data.DataSetExtensions.dll не различать личных данных и неконфиденциальные данные пользователя.  Эти сборки не собирают, не хранят и не переносят пользовательские личные данные. Но приложения сторонних производителей могут собирать, хранить и переносить пользовательские личные данные с использованием этих сборок.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Архитектура ADO.NET](../../../../docs/framework/data/adonet/ado-net-architecture.md)  
 Предоставляет общие сведения об архитектуре и компонентах ADO.NET.  
  
 [Возможности технологии и рекомендации по ADO.NET](../../../../docs/framework/data/adonet/ado-net-technology-options-and-guidelines.md)  
 Описываются продукты и технологии, входящие в состав платформы Entity Data Platform.  
  
 [LINQ и ADO.NET](../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 Описывается реализация технологии LINQ (Language-Integrated Query) в ADO.NET и приводятся ссылки на соответствующие разделы.  
  
 [Поставщики данных .NET Framework](../../../../docs/framework/data/adonet/data-providers.md)  
 Предоставляет общие сведения о конструкции поставщика данных .NET Framework и поставщиков данных .NET Framework, включенных при помощи ADO.NET.  
  
 [DataSets в ADO.NET](../../../../docs/framework/data/adonet/ado-net-datasets.md)  
 Предоставляет общие сведения о конструкции и компонентах `DataSet`.  
  
 [Одновременное выполнение в ADO.NET](../../../../docs/framework/data/adonet/side-by-side-execution.md)  
 Рассматривает различия версий ADO.NET и их влияние на параллельное выполнение и совместимость приложений.  
  
 [Примеры кода ADO.NET](../../../../docs/framework/data/adonet/ado-net-code-examples.md)  
 Предоставляет образцы кода, который получает данные при помощи поставщиков данных ADO.NET.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Новые возможности в ADO.NET](../../../../docs/framework/data/adonet/whats-new.md)  
 Представляет новые для [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] функции.  
  
 [Защита приложений ADO.NET](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 Описывает приемы безопасного программирования при использовании ADO.NET.  
  
 [Сопоставления типов данных в ADO.NET](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 Описывается сопоставление между типами данных .NET Framework и поставщиками данных .NET Framework.  
  
 [Извлечение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 Описывает, как выполнять соединение с источником данных, получать и изменять данные. К этому относятся `DataReaders` и `DataAdapters`.  
  
## <a name="see-also"></a>См. также  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)  
 [Доступ к данным в Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
