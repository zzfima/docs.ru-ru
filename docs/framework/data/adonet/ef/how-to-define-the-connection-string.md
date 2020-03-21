---
title: Практическое руководство. Определение строки подключения
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: e5b675a50f883825cce97275048447b79b64cc97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150575"
---
# <a name="how-to-define-the-connection-string"></a>Практическое руководство. Определение строки подключения

В этом разделе показано, как определить строку соединения, используемую при подключении к концептуальной модели. Эта тема основана на концептуальной модели [AdventureWorks Sales.](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) Модель AdventureWorks Sales используется во всех разделах документации платформы Entity Framework, описывающих выполнение задач. Эта тема предполагает, что вы уже настроили рамку сущности и определили модель продаж AdventureWorks. Для получения дополнительной информации [см. Как: Вручную определить модель и картографические файлы](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100)). Процедуры в этой теме также включены в [Как: Вручную настроить рамочный проект entity](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).

> [!NOTE]
> Если вы используете Волшебник модели данных Сущности в проекте Visual Studio, он автоматически генерирует файл .edmx и настраивает проект на использование рамочной программы Entity. Для получения дополнительной информации [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))

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

Если в проекте нет файла конфигурации приложения, вы можете добавить его, выбрав **добавить новый элемент** из меню **проекта,** выбрав **общую** категорию, выбрав **файл конфигурации приложения,** а затем нажав **добавить.**

## <a name="see-also"></a>См. также раздел

- [Краткое руководство](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))
- [Как создать новый EDMX-файл](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))
- [Средства работы с моделью EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
