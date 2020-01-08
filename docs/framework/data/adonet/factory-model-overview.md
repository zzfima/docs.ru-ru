---
title: Общие сведения о модели фабрики
ms.date: 03/30/2017
ms.assetid: b5dc81c4-7554-44b9-b513-769bd61e2e7b
ms.openlocfilehash: f344502453acbbb5c08e49b7c21a0f4e84a29ffa
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348398"
---
# <a name="factory-model-overview"></a>Общие сведения о модели фабрики
В ADO.NET 2.0 в пространстве имен <xref:System.Data.Common> появились новые базовые классы. Эти базовые классы являются абстрактными, что означает, что для них нельзя создавать экземпляры напрямую. К ним относятся классы <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand> и <xref:System.Data.Common.DbDataAdapter>; они совместно используются такими поставщиками данных платформы .NET Framework, как <xref:System.Data.SqlClient> и <xref:System.Data.OleDb>. Добавление базовых классов упрощает создание новых функций для поставщиков данных .NET Framework без необходимости в создании новых интерфейсов.  
  
 В ADO.NET 2.0 также появились абстрактные базовые классы, с помощью которых разработчик может создавать обобщенный код доступа к данным, не зависящий от конкретного поставщика данных.  
  
## <a name="the-factory-design-pattern"></a>Фабричный конструктивный шаблон  
 В основе модели программирования для написания не зависящего от поставщиков кода лежит использование «фабричного» конструктивного шаблона, в котором используется один API-интерфейс для доступа к базам данных нескольких поставщиков. Этому шаблону присваивается соответствующее имя, поскольку он задает использование специализированного объекта, только чтобы создавать другие объекты, что очень напоминает настоящую фабрику. Более подробное описание шаблона проектирования фабрики см. в статье [написание универсального кода доступа к данным в ASP.NET 2,0 и ADO.NET 2,0](https://docs.microsoft.com/previous-versions/dotnet/articles/ms971499(v=msdn.10)).
  
 Начиная с ADO.NET 2.0, для создания экземпляра <xref:System.Data.Common.DbProviderFactories> класс `static` предоставляет методы `Shared` (<xref:System.Data.Common.DbProviderFactory> в Visual Basic). После этого экземпляр возвращает правильный строго типизированный объект, основанный на данных поставщика и строке соединения, предоставленной во время выполнения.  
  
## <a name="see-also"></a>См. также:

- [Получение класса DbProviderFactory](obtaining-a-dbproviderfactory.md)
- [DbConnection, DbCommand и DbException](dbconnection-dbcommand-and-dbexception.md)
- [Изменение данных с помощью DbDataAdapter](modifying-data-with-a-dbdataadapter.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
