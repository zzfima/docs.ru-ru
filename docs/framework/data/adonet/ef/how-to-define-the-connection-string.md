---
title: Практическое руководство. Определение строки соединения
ms.date: 03/30/2017
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
ms.openlocfilehash: 9ce0b427cac17fc338877c5f85d3648d15d5ee14
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833949"
---
# <a name="how-to-define-the-connection-string"></a>Практическое руководство. Определение строки соединения

В этом разделе показано, как определить строку соединения, используемую при подключении к концептуальной модели. Этот раздел основан на концептуальной модели [AdventureWorks Sales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb387147(v=vs.100)) . Модель AdventureWorks Sales используется во всех разделах документации платформы Entity Framework, описывающих выполнение задач. В этом разделе предполагается, что вы уже настроили Entity Framework и определили модель AdventureWorks Sales. Дополнительные сведения см. в разделе [Практическое руководство. Вручную Определите файлы](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399785(v=vs.100))модели и сопоставления. Процедуры, описанные в этом разделе, также [включены в процедуру: Вручную настройте проект](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))Entity Framework.

> [!NOTE]
> При использовании мастера EDM в проекте Visual Studio он автоматически создает EDMX-файл и настраивает проект для использования Entity Framework. Дополнительные сведения см. в разделе [Практическое руководство. Используйте мастер](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))EDM.

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

Если в проекте нет файла конфигурации приложения, его можно добавить, выбрав в меню **проект** пункт **Добавить новый элемент** , выбрав категорию **Общие** , выбрав **файл конфигурации приложения**, а затем нажав кнопку **Добавить**.

## <a name="see-also"></a>См. также

- [Краткое руководство](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100))
- [Практическое руководство. Создание нового EDMX-файла](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716703(v=vs.100))
- [Средства работы с моделью EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
