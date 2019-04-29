---
title: Практическое руководство. Определение строки соединения
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 7fb722acbb13b3502d004978581701cc70118ff8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606114"
---
# <a name="how-to-define-the-connection-string"></a>Практическое руководство. Определение строки соединения

В этом разделе показано, как определить строку соединения, используемую при подключении к концептуальной модели. Этот раздел основан на [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) концептуальной модели. Модель AdventureWorks Sales используется во всех разделах документации платформы [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], связанных с выполнением задач. В этом разделе предполагается, что вы уже настроили [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] и определенные в модели AdventureWorks Sales. Дополнительные сведения см. в разделе [Как Вручную определите модель и файлы сопоставления](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)). Процедуры этого раздела также включены в [как: Вручную настроить проект Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).

> [!NOTE]
> Если вы используете [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] мастера в проект Visual Studio, он автоматически сформирует EDMX-файл и настроит проект для использования [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Дополнительные сведения см. в разделе [Как Использовать мастер моделей EDM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))

## <a name="to-define-the-entity-framework-connection-string"></a>Определение строки соединения Entity Framework

- Откройте файл конфигурации приложения (app.config) и добавьте следующую строку соединения:

```xml
<connectionStrings>
    <add name="AdventureWorksEntities" 
         connectionString="metadata=.\AdventureWorks.csdl|.\AdventureWorks.ssdl|.\AdventureWorks.msl;
         provider=System.Data.SqlClient;provider connection string='Data Source=localhost;
         Initial Catalog=AdventureWorks;Integrated Security=True;Connection Timeout=60;
         multipleactiveresultsets=true'" providerName="System.Data.EntityClient" />
</connectionStrings>
```

Если проект не имеет файла конфигурации приложения, можно добавить его, выбрав **Добавление нового элемента** из **проекта** меню, выбрав **Общие** категории выбрав **файла конфигурации приложения**и выбрав **добавить**.

## <a name="see-also"></a>См. также

- [Краткое руководство](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))
- [Практическое руководство. Создать новый EDMX-файл](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))
- [Средства работы с моделью EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
