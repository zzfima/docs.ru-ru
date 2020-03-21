---
title: 'Учебник: Создание клиента Фонда коммуникации Windows'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: bfa4cbacc5a947cb51d577503b5e46f9a5f8de39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184101"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a>Учебник: Создание клиента Фонда коммуникации Windows

В этом уроке описаны четвертая из пяти задач, необходимых для создания базового приложения Windows Communication Foundation (WCF). Для обзора учебников [см.](getting-started-tutorial.md)

Следующей задачей для создания приложения WCF является создание клиента путем извлечения метаданных из службы WCF. Вы используете Visual Studio для добавления справочника по обслуживанию, который получает метаданные из конечных точек службы MEX. Visual Studio затем генерирует управляемый файл исходного кода для клиентского прокси на выбранном языке. Он также создает файл конфигурации клиента (*App.config*). Этот файл позволяет клиенту приложение подключиться к службе в конечном пункте.

> [!NOTE]
> Если вы вызываете службу WCF из проекта библиотеки класса в Visual Studio, используйте функцию **справки об обслуживании Add** для автоматического создания прокси-файла и связанного файла конфигурации. Однако, поскольку проекты библиотеки классов не используют этот файл конфигурации, необходимо добавить настройки в файл сгенерированной конфигурации в файл *App.config* для исполняемой библиотеки класса.

> [!NOTE]
> В качестве альтернативы используйте [инструмент ServiceModel Metadata Utility](#servicemodel-metadata-utility-tool) вместо Visual Studio для генерации файла прокси-класса и конфигурации.

Клиентское приложение использует созданный прокси-класс для взаимодействия со службой. Эта процедура описана в [учебнике: Используйте клиента.](how-to-use-a-wcf-client.md)

В этом руководстве описано следующее:
> [!div class="checklist"]
>
> - Создайте и назначайте проект консольного приложения для клиента WCF.
> - Добавьте ссылку на службу WCF для генерации файлов прокси-класса и конфигурации.

## <a name="create-a-windows-communication-foundation-client"></a>Создание клиента Фонда коммуникаций Windows

1. Создайте проект консольного приложения в Visual Studio:

    1. Из меню **файла** выберите **Open** > **Project/Solution** и просмотрите ранее созданное решение **GettingStarted** *(GettingStarted.sln).* Выберите **Открыть**.

    2. Из меню **View** выберите **Solution Explorer**.

    3. В окне **Solution Explorer** выберите решение **GettingStarted** (верхний узло), а затем выберите **Добавить** > **новый проект** из меню ярлыка.

    4. В окне **Добавить новый проект,** на левой стороне, выберите категорию **Windows Desktop** под **Visual C или** Visual **Basic**.

    5. Выберите шаблон **Console App (.NET Framework)** и введите *GettingStartedClient* для **name**. Нажмите кнопку **ОК**.

2. Добавьте ссылку в проект **gettingStartedClient** к сборке: <xref:System.ServiceModel>

    1. В окне **Solution Explorer** выберите папку **«Ссылки»** в проекте **GettingStartedClient,** а затем выберите **«Добавить ссылку»** из меню ярлыка.

    2. В окне **справки Добавить** под **сборками** на левой стороне окна выберите **Framework**.

    3. Найти и выбрать **System.ServiceModel**, а затем выбрать **OK**.

    4. Сохранить решение, выбрав **файл** > **Сохранить все**.

3. Добавьте ссылку на услугу в службу калькулятора:

   1. В окне **Solution Explorer** выберите папку **«Ссылки»** в проекте **GettingStartedClient,** а затем выберите Ссылку на **службу** из меню ярлыка.

   2. В окне **справки об услугах Добавить** выберите **Discover**.

      Запускается сервис CalculatorService, и Visual Studio отображает его в окне **Услуг.**

   3. Выберите **CalculatorService,** чтобы расширить его и отобразить сервисные контракты, реализованные службой. Оставьте **пространство имен** по умолчанию и выберите **OK.**

      Visual Studio добавляет новый элемент в папку **«Подключенные услуги»** в проекте **GettingStartedClient.**

### <a name="servicemodel-metadata-utility-tool"></a>СервисМодель Метаданные Утилита инструмент

Ниже приведены следующие примеры, как дополнительно использовать [инструмент ServiceModel Metadata Utility (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) для генерации файла класса прокси. Этот инструмент генерирует файл класса прокси и файл *App.config.* Следующие примеры показывают, как создать прокси в C и Visual Basic, соответственно:

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a>Файл конфигурации клиента

После создания клиента Visual Studio создает файл конфигурации **App.config** в проекте **GettingStartedClient,** который должен быть похож на следующий пример:

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

В разделе [ \<system.serviceModel>,](../configure-apps/file-schema/wcf/system-servicemodel.md) обратите внимание на [ \<элемент endpoint>.](../configure-apps/file-schema/wcf/endpoint-element.md) Элемент ** &lt;конечных точек&gt; ** определяет конечную точку, которую клиент использует для доступа к службе следующим образом:

- Адрес: `http://localhost:8000/GettingStarted/CalculatorService`. Адрес конечной точки.
- Сервисный `ServiceReference1.ICalculator`контракт: . Контракт на обслуживание обрабатывает связь между клиентом WCF и службой. Visual Studio генерировал этот контракт, когда вы использовали функцию **справки add Service.** По сути, это копия контракта, который вы определили в проекте GettingStartedLib.
- Связывание: <xref:System.ServiceModel.WSHttpBinding>. Привязка определяет HTTP как транспорт, совместимую безопасность и другие детали конфигурации.

## <a name="next-steps"></a>Дальнейшие действия

В этом руководстве вы узнали, как выполнять следующие задачи:
> [!div class="checklist"]
>
> - Создайте и назначайте проект консольного приложения для клиента WCF.
> - Добавьте ссылку на службу WCF для создания прокси-класса и файлов конфигурации для клиентского приложения.

Перейти к следующему учебнику, чтобы узнать, как использовать генерируемый клиент.

> [!div class="nextstepaction"]
> [Учебник: Используйте клиент WCF](how-to-use-a-wcf-client.md)
