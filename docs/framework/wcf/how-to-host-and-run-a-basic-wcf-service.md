---
title: 'Учебник: Хост и запуск базового сервиса Windows Communication Foundation'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 30eb86987b83427b94c6fff22755cde3d73dd9f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184081"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a>Учебник: Хост и запуск базового сервиса Windows Communication Foundation

В этом уроке описаны третья из пяти задач, необходимых для создания базового приложения Windows Communication Foundation (WCF). Для обзора учебников [см.](getting-started-tutorial.md)

Следующей задачей для создания приложения WCF является размещение wCF-сервиса в консольном приложении. Служба WCF предоставляет одну или несколько *конечных точек,* каждая из которых предоставляет одну или несколько операций службы. Конечная точка службы определяет следующую информацию:

- Адрес, по которому можно найти услугу.
- Привязка, содержащая информацию, описывающую, как клиент должен общаться с службой.
- Контракт, определяющий функциональность, которую служба предоставляет своим клиентам.

В этом руководстве описано следующее:
> [!div class="checklist"]
>
> - Создайте и настройте проект консольного приложения для размещения сервиса WCF.
> - Добавьте код для размещения службы WCF.
> - Обновление файла конфигурации.
> - Запустите службу WCF и проверьте, что она работает.

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a>Создание и настройка проекта консольного приложения для хостинга сервиса

1. Создайте проект консольного приложения в Visual Studio:

    1. Из меню **файла** выберите **Open** > **Project/Solution** и просмотрите ранее созданное решение **GettingStarted** *(GettingStarted.sln).* Выберите **Открыть**.

    2. Из меню **View** выберите **Solution Explorer**.

    3. В окне **Solution Explorer** выберите решение **GettingStarted** (верхний узло), а затем выберите **Добавить** > **новый проект** из меню ярлыка.

    4. В окне **Добавить новый проект,** на левой стороне, выберите категорию **Windows Desktop** под **Visual C или** Visual **Basic**.

    5. Выберите шаблон **Console App (.NET Framework)** и введите *GettingStartedHost* для **name.** Нажмите кнопку **ОК**.

2. Добавьте ссылку в проект **gettingStartedHost** в проект **GettingStartedLib:**

    1. В окне **Solution Explorer** выберите папку **«Ссылки»** в рамках проекта **GettingStartedHost,** а затем выберите **«Добавить ссылку»** из меню ярлыка.

    2. В диалоге **Add Reference** под **проектами** на левой стороне окна выберите **решение.**

    3. Выберите **GettingStartedLib** в центральной части окна, а затем выберите **OK.**

       Это действие делает типы, определенные в проекте **GettingStartedLib,** доступными для проекта **GettingStartedHost.**

3. Добавьте ссылку в проект **gettingStartedHost** в сборку: <xref:System.ServiceModel>

    1. В окне **Solution Explorer** выберите папку **«Ссылки»** в рамках проекта **GettingStartedHost,** а затем выберите **«Добавить ссылку»** из меню ярлыка.

    2. В окне **справки Добавить** под **сборками** на левой стороне окна выберите **Framework**.

    3. Выберите **System.ServiceModel**, а затем выберите **OK**.

    4. Сохранить решение, выбрав **файл** > **Сохранить все**.

## <a name="add-code-to-host-the-service"></a>Добавление кода для размещения службы

Чтобы разместить службу, вы добавляете код для следующих шагов:

1. Создайте URI для базового адреса.
2. Создайте экземпляр класса для хостинга службы.
3. Создайте конечную точку обслуживания.
4. Включите обмен метаданными.
5. Откройте услик службы для прослушивания входящих сообщений.
  
Внесите следующие изменения в код:

1. Откройте файл **Program.cs** или **Module1.vb** в проекте **GettingStartedHost** и замените его код следующим кодом:

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Description;
    using GettingStartedLib;

    namespace GettingStartedHost
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Step 1: Create a URI to serve as the base address.
                Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

                // Step 2: Create a ServiceHost instance.
                ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

                try
                {
                    // Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                    // Step 4: Enable metadata exchange.
                    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                    smb.HttpGetEnabled = true;
                    selfHost.Description.Behaviors.Add(smb)    ;

                    // Step 5: Start the service.
                    selfHost.Open();
                    Console.WriteLine("The service is ready.");

                    // Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.");
                    Console.WriteLine();
                    Console.ReadLine();
                    selfHost.Close();
                }
                catch (CommunicationException ce)
                {
                    Console.WriteLine("An exception occurred: {0}", ce.Message);
                    selfHost.Abort();
                }
            }
        }
    }
    ```

    ```vb
    Imports System.ServiceModel
    Imports System.ServiceModel.Description
    Imports GettingStartedLib.GettingStartedLib

    Module Service

        Class Program
            Shared Sub Main()
                ' Step 1: Create a URI to serve as the base address.
                Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

                ' Step 2: Create a ServiceHost instance.
                Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
               Try

                    ' Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint( _
                        GetType(ICalculator), _
                        New WSHttpBinding(), _
                        "CalculatorService")

                    ' Step 4: Enable metadata exchange.
                    Dim smb As New ServiceMetadataBehavior()
                    smb.HttpGetEnabled = True
                    selfHost.Description.Behaviors.Add(smb)

                    ' Step 5: Start the service.
                    selfHost.Open()
                    Console.WriteLine("The service is ready.")

                    ' Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.")
                    Console.WriteLine()
                    Console.ReadLine()
                    selfHost.Close()

                Catch ce As CommunicationException
                    Console.WriteLine("An exception occurred: {0}", ce.Message)
                    selfHost.Abort()
                End Try
            End Sub
        End Class

    End Module
    ```

    Для получения информации о [Service hosting program steps](#service-hosting-program-steps)том, как работает этот код, см.

2. Обновление свойств проекта:

   1. В окне **Solution Explorer** выберите папку **GettingStartedHost,** а затем выберите **свойства** из меню ярлыка.

   2. На странице свойств **GettingStartedHost** выберите вкладку **Приложения:**

      - Для проектов с c, выберите **GettingStartedHost.Program** из списка **объектов запуска.**

      - Для проектов Visual Basic выберите **Service.Program** из списка **объектов запуска.**

   3. Из меню **файла** выберите **Сохранить все**.

## <a name="verify-the-service-is-working"></a>Проверка работы службы

1. Создайте решение, а затем запустите консольное приложение **GettingStartedHost** из нутри Visual Studio.

    Служба должна работать с привилегиями администратора. Поскольку вы открыли Visual Studio с привилегиями администратора, при запуске **GettingStartedHost** в Visual Studio приложение также работает с привилегиями администратора. В качестве альтернативы можно открыть новую запросную команду в качестве администратора (выберите **More** > Run в**качестве администратора** из меню ярлыка) и запустить **GettingStartedHost.exe** в нем.

2. Откройте веб-браузер и просмотрите страницу службы по адресу `http://localhost:8000/GettingStarted/CalculatorService`.

   > [!NOTE]
   > Службы, подобные этой, требуют надлежащего разрешения на регистрацию адресов HTTP на машине для прослушивания. Учетные записи с уровнем доступа администратора имеют данное разрешение, а остальным учетным записям должно быть предоставлено разрешение на использование пространства имен HTTP. Дополнительные сведения о настройке резервирования пространств имен см. в разделе [Настройка протоколов HTTP и HTTPS](feature-details/configuring-http-and-https.md).

## <a name="service-hosting-program-steps"></a>Шаги программы хостинга сервиса

Шаги в коде, добавленном для размещения службы, описаны следующим образом:

- **Шаг 1**: Создайте `Uri` экземпляр класса для удержания базового адреса службы. URL-адрес, содержащий базовый адрес, имеет дополнительный URI, который идентифицирует службу. Базовый адрес отформатирован `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`следующим образом: . Базовый адрес услуги калькулятора использует транспорт HTTP, localhost, порт 8000 и сегмент URI, GettingStarted.

- **Шаг 2**: Создайте <xref:System.ServiceModel.ServiceHost> экземпляр класса, который используется для размещения службы. Конструктор принимает два параметра: тип класса, который реализует контракт на обслуживание, и базовый адрес службы.

- **Шаг 3**: <xref:System.ServiceModel.Description.ServiceEndpoint> Создайте экземпляр. Конечная точка службы состоит из адреса, привязки и контракта службы. Конструктор <xref:System.ServiceModel.Description.ServiceEndpoint> состоит из типа интерфейса контракта службы, привязки и адреса. Контракт службы - `ICalculator`. Он определен и реализуется в типе службы. Привязка для <xref:System.ServiceModel.WSHttpBinding>этого образца, которая является встроенной привязкой и подключается к конечным точкам, которые соответствуют спецификациям WS-'. Для получения дополнительной информации о привязки WCF, [см.](bindings-overview.md) Вы приговыте адрес к базовому адресу, чтобы определить конечную точку. Код определяет адрес как CalculatorService и полностью квалифицированный адрес `http://localhost:8000/GettingStarted/CalculatorService`для конечных точек как.

    > [!IMPORTANT]
    > Для .NET Framework Version 4 и позже добавление конечная точка обслуживания не является обязательным. Для этих версий, если вы не добавляете свой код или конфигурацию, WCF добавляет одну конечную точку по умолчанию для каждой комбинации базового адреса и контракта, реализованного службой. Для получения дополнительной информации о конечных точках по умолчанию [см.](specifying-an-endpoint-address.md) Для получения дополнительной информации о конечных точках по умолчанию, привязки и поведении [см. Упрощенная конфигурация](simplified-configuration.md) и [упрощенная конфигурация для служб WCF.](samples/simplified-configuration-for-wcf-services.md)

- **Шаг 4**: Включить обмен метаданными. Клиенты используют обмен метаданными для генерации прокси-сервисов для вызова службы. Для обеспечения обмена метаданными <xref:System.ServiceModel.Description.ServiceMetadataBehavior> создайте <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> экземпляр, установите `ServiceMetadataBehavior` его <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> свойство `true` <xref:System.ServiceModel.ServiceHost> и добавьте объект в сбор экземпляра.

- **Шаг 5** <xref:System.ServiceModel.ServiceHost> : Открыть для прослушивания входящих сообщений. Приложение ждет вас, чтобы нажать **Enter**. После мгновенного <xref:System.ServiceModel.ServiceHost>приложения, он выполняет попробовать / поймать блок. Для получения дополнительной информации о <xref:System.ServiceModel.ServiceHost>безопасной ловле исключений, брошенных, см. [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md)

> [!IMPORTANT]
> При добавлении библиотеки обслуживания WCF Visual Studio принимает ее для вас, если вы отладите ее, забрав усваиватель службы. Чтобы избежать конфликтов, вы можете предотвратить Visual Studio от размещения библиотеки wCF службы.
>
> 1. Выберите проект **GettingStartedLib** в **Solution Explorer** и выберите **свойства** из меню ярлыка.
> 2. Выберите **параметры WCF** и отрежь **от запуска wCF Service Host при отладке другого проекта в том же решении.**

## <a name="next-steps"></a>Дальнейшие действия

В этом руководстве вы узнали, как выполнять следующие задачи:
> [!div class="checklist"]
>
> - Создайте и настройте проект консольного приложения для размещения сервиса WCF.
> - Добавьте код для размещения службы WCF.
> - Обновление файла конфигурации.
> - Запустите службу WCF и проверьте, что она работает.

Перейти к следующему учебнику, чтобы узнать, как создать клиента WCF.

> [!div class="nextstepaction"]
> [Учебник: Создание клиента WCF](how-to-create-a-wcf-client.md)
