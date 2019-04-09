---
title: Учебник. Создание клиента Windows Communication Foundation
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: a16a0ccabfd0f9fbe69db1ea88d4613185f3c1da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174373"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a>Учебник. Создание клиента Windows Communication Foundation

В данном учебнике четвертый из пяти шагов, необходимых для создания базового приложения Windows Communication Foundation (WCF). Обзор руководства, см. в разделе [руководства: Начало работы с приложениями Windows Communication Foundation](getting-started-tutorial.md).

Следующая задача по созданию приложения WCF — для создания клиента путем извлечения метаданных из службы WCF. Используйте Visual Studio для добавления ссылки на службу, которая получает метаданные из конечной точки службы обмена Метаданными. Затем Visual Studio создает файл управляемого исходного кода для клиентского прокси на языке, который вы выбрали. Он также создает файл конфигурации клиента (*App.config*). Этот файл позволяет клиентскому приложению подключаться к службе в конечной точке. 

> [!NOTE]
> Если вызов службы WCF из проекта библиотеки классов в Visual Studio, используйте **Add Service Reference** компонентов для автоматического создания прокси-сервера и связанный файл конфигурации. Тем не менее, так как библиотеки классов не используют этот файл конфигурации, необходимо добавить параметры в созданный файл конфигурации для *App.config* файл для исполняемого файла, который вызывает библиотеку классов.

> [!NOTE]
> В качестве альтернативы использовать [средство ServiceModel Metadata Utility](#servicemodel-metadata-utility-tool) вместо Visual Studio для создания файла класса и конфигурации прокси-сервера.

Клиентское приложение использует созданный прокси-класс для взаимодействия со службой. Эта процедура описана в [руководства: Использование клиента](how-to-use-a-wcf-client.md).

В этом руководстве вы узнаете, как:
> [!div class="checklist"]
> - Создание и настройка проекта консольного приложения для клиента WCF.
> - Добавьте ссылку на службу в службу WCF, чтобы создать файлы класса и конфигурации прокси-сервера.

## <a name="create-a-windows-communication-foundation-client"></a>Создание клиента Windows Communication Foundation

1. Создание проекта консольного приложения в Visual Studio: 

    1. Из **файл** меню, выберите **откройте** > **решение или проект** и перейдите к **GettingStarted** решения вы ранее созданный (*GettingStarted.sln*). Нажмите кнопку **Открыть**.

    2. Из **представление** меню, выберите **обозревателе решений**.

    3. В **обозревателе решений** выберите **GettingStarted** решение (верхний узел), а затем выберите **добавить** > **новый проект** в контекстном меню. 
    
    4. В **Добавление нового проекта** окно, в левой части окна выберите **Windows Desktop** категорию **Visual C#**  или **Visual Basic**. 

    5. Выберите **консольное приложение (.NET Framework)** шаблона и введите *GettingStartedClient* для **имя**. Нажмите кнопку **ОК**.

2. Добавьте ссылку в **GettingStartedClient** проект <xref:System.ServiceModel> сборки: 

    1.  В **обозревателе решений** выберите **ссылки** папке **GettingStartedClient** проекта, а затем выберите **добавить ссылку на** в контекстном меню. 

    2. В **добавить ссылку** окна в разделе **сборки** в левой части окна выберите **Framework**.
    
    3. Найдите и выберите **System.ServiceModel**, а затем выберите **ОК**. 

    4. Сохраните решение, выбрав **файл** > **сохранить все**.

3. Добавьте ссылку на службу для службы калькулятора:

   1. В **обозревателе решений** выберите **ссылки** папке **GettingStartedClient** проекта, а затем выберите **Add Service Reference**  в контекстном меню.

   2. В **Add Service Reference** выберите **Discover**.

      Запускает службу CalculatorService и Visual Studio отображает его в **служб** поле.

   3. Выберите **CalculatorService** чтобы развернуть ее и отобразить контрактов службы, реализованном в службе. Оставьте значение по умолчанию **пространства имен** и выберите **ОК**.

      Visual Studio добавляет новый элемент в разделе **подключенных служб** папку в **GettingStartedClient** проекта. 

### <a name="servicemodel-metadata-utility-tool"></a>Средство ServiceModel Metadata Utility

Следующие примеры показывают, как при необходимости использовать [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) для создания файла класса прокси-сервера. Это средство создает файл класса прокси-сервера и *App.config* файл. Следующие примеры показывают, как для создания прокси-сервера в C# и Visual Basic, соответственно:

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a>Файл конфигурации клиента

После создания клиента, Visual Studio создает **App.config** файл конфигурации в **GettingStartedClient** проект, который должен выглядеть следующим образом:

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
            <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/GettingStarted/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <dns value="localhost" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

В разделе [ \<system.serviceModel >](../configure-apps/file-schema/wcf/system-servicemodel.md) разделе, обратите внимание, что [ \<конечной точки >](../configure-apps/file-schema/wcf/endpoint-element.md) элемент. **&lt;Конечной точки&gt;** элемент определяет конечную точку, которую клиент использует для доступа к службе, следующим образом:
- Адрес: `http://localhost:8000/GettingStarted/CalculatorService`. Адрес конечной точки.
- Контракт службы: `ServiceReference1.ICalculator`. Контракт службы обеспечивает взаимодействие между клиентом WCF и службой. Visual Studio создается этот контракт, когда вы использовали его **Add Service Reference** функции. Это по сути копию контракта, которое было определено в проекте GettingStartedLib. 
- Привязки: <xref:System.ServiceModel.WSHttpBinding>. Привязка задает HTTP в качестве транспорта, безопасности с возможностью взаимодействия и другие сведения о конфигурации.

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы узнали, как:
> [!div class="checklist"]
> - Создание и настройка проекта консольного приложения для клиента WCF.
> - Добавьте ссылку на службу в службу WCF, чтобы создать файлы класса и конфигурации прокси-сервера для клиентского приложения.

Перейдите к следующему руководству, чтобы сведения об использовании созданного клиента.

> [!div class="nextstepaction"]
> [Учебник. Использование клиента WCF](how-to-use-a-wcf-client.md)
