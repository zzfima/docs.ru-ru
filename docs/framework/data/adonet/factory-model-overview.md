---
title: Общие сведения о модели фабрики
ms.date: 03/30/2017
ms.assetid: b5dc81c4-7554-44b9-b513-769bd61e2e7b
ms.openlocfilehash: b45e73dd21cad1381f58b578a19c39a1d89e8c3c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510044"
---
# <a name="factory-model-overview"></a>Общие сведения о модели фабрики
В ADO.NET 2.0 в пространстве имен <xref:System.Data.Common> появились новые базовые классы. Эти базовые классы являются абстрактными, что означает, что для них нельзя создавать экземпляры напрямую. К ним относятся классы <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand> и <xref:System.Data.Common.DbDataAdapter>; они совместно используются такими поставщиками данных платформы .NET Framework, как <xref:System.Data.SqlClient> и <xref:System.Data.OleDb>. Добавление базовых классов упрощает создание новых функций для поставщиков данных .NET Framework без необходимости в создании новых интерфейсов.  
  
 В ADO.NET 2.0 также появились абстрактные базовые классы, с помощью которых разработчик может создавать обобщенный код доступа к данным, не зависящий от конкретного поставщика данных.  
  
## <a name="the-factory-design-pattern"></a>Фабричный конструктивный шаблон  
 В основе модели программирования для написания не зависящего от поставщиков кода лежит использование «фабричного» конструктивного шаблона, в котором используется один API-интерфейс для доступа к базам данных нескольких поставщиков. Этому шаблону присваивается соответствующее имя, поскольку он задает использование специализированного объекта, только чтобы создавать другие объекты, что очень напоминает настоящую фабрику. Более подробное описание фабричного конструктивного шаблона, см. в разделе [универсального кода доступа к данным записи в ASP.NET 2.0 и ADO.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=55915).
  
 Начиная с ADO.NET 2.0, для создания экземпляра <xref:System.Data.Common.DbProviderFactories> класс `static` предоставляет методы `Shared` (<xref:System.Data.Common.DbProviderFactory> в Visual Basic). После этого экземпляр возвращает правильный строго типизированный объект, основанный на данных поставщика и строке соединения, предоставленной во время выполнения.  
  
## <a name="see-also"></a>См. также
- [Получение класса DbProviderFactory](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)
- [DbConnection, DbCommand и DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)
- [Изменение данных с помощью DbDataAdapter](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
