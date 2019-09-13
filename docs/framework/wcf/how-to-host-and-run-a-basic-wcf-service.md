---
title: Учебник. Размещение и запуск базовой службы Windows Communication Foundation
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 984c5e73a8efc4e9c2d487485267868ffa2f60f3
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928716"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a>Учебник. Размещение и запуск базовой службы Windows Communication Foundation

В этом руководстве описывается третья из пяти задач, необходимых для создания приложения Basic Windows Communication Foundation (WCF). Общие сведения о учебниках см. в [разделе Учебник. Приступая к работе с](getting-started-tutorial.md)Windows Communication Foundation приложениями.

Следующей задачей для создания приложения WCF является размещение службы WCF в консольном приложении. Служба WCF предоставляет одну или несколько *конечных точек*, каждая из которых предоставляет одну или несколько операций службы. Конечная точка службы задает следующие сведения:

- Адрес, по которому можно найти службу.
- Привязка, которая содержит сведения, описывающие, как клиент должен взаимодействовать со службой. 
- Контракт, определяющий функциональные возможности, предоставляемые службой своим клиентам.

В этом руководстве вы узнаете, как:
> [!div class="checklist"]
>
> - Создание и Настройка проекта консольного приложения для размещения службы WCF.
> - Добавьте код для размещения службы WCF.
> - Обновите файл конфигурации.
> - Запустите службу WCF и убедитесь, что она запущена.

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a>Создание и Настройка проекта консольного приложения для размещения службы

1. Создание проекта консольного приложения в Visual Studio: 
 
    1. В меню **файл** выберите команду **Открыть** > **проект или решение** и перейдите к созданному ранее решению **GettingStarted** (*GettingStarted. sln*). Нажмите кнопку **Открыть**.

    2. В меню **вид** выберите **Обозреватель решений**.
    
    3. В окне **Обозреватель решений** выберите решение **GettingStarted** (верхний узел), а затем в контекстном меню выберите **добавить** > **Новый проект** . 

    4. В левой части окна **Добавление нового проекта** выберите категорию **Рабочий стол Windows** в разделе  **C# Visual** или **Visual Basic**. 

    5. Выберите шаблон **консольное приложение (.NET Framework)** и введите *GettingStartedHost* в поле **имя**. Нажмите кнопку **ОК**.

2. Добавьте ссылку в проект **GettingStartedHost** в проект **жеттингстартедлиб** : 

    1. В окне **Обозреватель решений** выберите папку **References** в проекте **GettingStartedHost** , а затем в контекстном меню выберите пункт **Добавить ссылку** . 

    2. В диалоговом окне **Добавление ссылки** в разделе **проекты** в левой части окна выберите **решение**. 
 
    3. Выберите **жеттингстартедлиб** в центральном разделе окна, а затем нажмите кнопку **ОК**. 

       Это действие делает типы, определенные в проекте **жеттингстартедлиб** , доступными для проекта **GettingStartedHost** .

3. Добавьте ссылку в проект <xref:System.ServiceModel> **GettingStartedHost** в сборку: 

    1. В окне **Обозреватель решений** выберите папку **References** в проекте **GettingStartedHost** , а затем в контекстном меню выберите пункт **Добавить ссылку** .
    
    2. В окне **Добавление ссылки** в разделе **сборки** в левой части окна выберите **платформа**. 

    3. Выберите **System. ServiceModel**и нажмите кнопку **ОК**. 
    
    4. Сохраните решение, выбрав **файл** > **сохранить все**.

## <a name="add-code-to-host-the-service"></a>Добавление кода для размещения службы

Чтобы разместить службу, добавьте код для выполнения следующих действий. 

1. Создайте универсальный код ресурса (URI) для базового адреса.
2. Создайте экземпляр класса для размещения службы.
3. Создайте конечную точку службы.
4. Включите обмен метаданными.
5. Откройте узел службы, чтобы прослушивать входящие сообщения.
  
Внесите в код следующие изменения:

1. Откройте файл **Program.CS** или **Module1. vb** в проекте **GettingStartedHost** и замените его код следующим кодом:

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
    
    Сведения о том, как работает этот код, см. в [статье этапы программы размещения службы](#service-hosting-program-steps).

2. Обновите свойства проекта:

   1. В окне **Обозреватель решений** выберите папку **GettingStartedHost** , а затем в контекстном меню выберите пункт **Свойства** .

   2. На странице свойства **GettingStartedHost** выберите вкладку **приложение** :

      - Для C# проектов выберите **GettingStartedHost. Program** из списка **автоматически запускаемых объектов** .

      - Для Visual Basic проектов выберите **Service. Program** из списка **автоматически запускаемых объектов** .

   3. В меню **файл** выберите **сохранить все**.

## <a name="verify-the-service-is-working"></a>Проверка работоспособности службы

1. Выполните сборку решения, а затем запустите консольное приложение **GettingStartedHost** в Visual Studio. 

    Служба должна запускаться с правами администратора. Так как вы открыли Visual Studio с правами администратора, при запуске **GettingStartedHost** в Visual Studio приложение также запускается с правами администратора. В качестве альтернативы можно открыть новую командную строку от имени администратора (в контекстном меню выберите **больше** > **запуска от имени администратора** ) и запустить в ней **GettingStartedHost. exe** .

2. Откройте веб-браузер и перейдите на страницу службы по адресу `http://localhost:8000/GettingStarted/CalculatorService`.
   
   > [!NOTE]
   > Для таких служб требуется разрешение на регистрацию HTTP-адресов на компьютере для прослушивания. Учетные записи с уровнем доступа администратора имеют данное разрешение, а остальным учетным записям должно быть предоставлено разрешение на использование пространства имен HTTP. Дополнительные сведения о настройке резервирования пространств имен см. в разделе [Настройка протоколов HTTP и HTTPS](feature-details/configuring-http-and-https.md). 

## <a name="service-hosting-program-steps"></a>Шаги программы размещения службы

Шаги в коде, добавленном для размещения службы, описаны ниже.

- **Шаг 1**. Создайте экземпляр `Uri` класса для хранения базового адреса службы. URL-адрес, содержащий базовый адрес, имеет необязательный URI, идентифицирующий службу. Базовый адрес форматируется следующим образом: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`. Базовый адрес службы калькулятора использует транспорт HTTP, localhost, порт 8000 и сегмент URI GettingStarted.

- **Шаг 2**. Создайте экземпляр <xref:System.ServiceModel.ServiceHost> класса, который используется для размещения службы. Конструктор принимает два параметра: тип класса, который реализует контракт службы, и базовый адрес службы.

- **Шаг 3**. Создайте экземпляр <xref:System.ServiceModel.Description.ServiceEndpoint>. Конечная точка службы состоит из адреса, привязки и контракта службы. <xref:System.ServiceModel.Description.ServiceEndpoint> Конструктор состоит из типа интерфейса контракта службы, привязки и адреса. Контракт службы - `ICalculator`. Он определен и реализуется в типе службы. Привязка для этого образца — <xref:System.ServiceModel.WSHttpBinding>это встроенная привязка, которая подключается к конечным точкам, которые соответствуют спецификациям WS-*. Дополнительные сведения о привязках WCF см. в разделе [Общие сведения о привязках WCF](bindings-overview.md). Добавьте адрес к базовому адресу, чтобы обозначить конечную точку. Код определяет адрес как CalculatorService и полный адрес конечной точки как `http://localhost:8000/GettingStarted/CalculatorService`.

    > [!IMPORTANT]
    > Для .NET Framework версии 4 и более поздних версий Добавление конечной точки службы является необязательным. В этих версиях, если не добавить код или конфигурацию, WCF добавляет одну конечную точку по умолчанию для каждого сочетания базового адреса и контракта, реализуемого службой. Дополнительные сведения о конечных точках по умолчанию см. [в разделе Указание адреса конечной точки](specifying-an-endpoint-address.md). Дополнительные сведения о конечных точках, привязках и поведении по умолчанию см. в разделе [упрощенная конфигурация](simplified-configuration.md) и [упрощенная конфигурация для служб WCF](samples/simplified-configuration-for-wcf-services.md).

- **Шаг 4**. Включите обмен метаданными. Клиенты используют обмен метаданными для создания учетных записей-посредников для вызова операций службы. Чтобы включить обмен метаданными, создайте <xref:System.ServiceModel.Description.ServiceMetadataBehavior> экземпляр, присвойте <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> его свойству `true`значение, а `ServiceMetadataBehavior` затем <xref:System.ServiceModel.ServiceHost> добавьте объект <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> в коллекцию экземпляра.

- **Шаг 5**. Откройте <xref:System.ServiceModel.ServiceHost> для прослушивания входящих сообщений. Приложение ожидает нажатия клавиши **Ввод**. После создания экземпляра <xref:System.ServiceModel.ServiceHost>приложения он выполняет блок try/catch. Дополнительные сведения о безопасном перехвате исключений <xref:System.ServiceModel.ServiceHost>, создаваемых, см. в разделе [Использование закрытия и прерывания для освобождения ресурсов клиента WCF](samples/use-close-abort-release-wcf-client-resources.md).

> [!IMPORTANT]
> При добавлении библиотеки службы WCF Visual Studio размещает ее для вас при его отладке, запуская узел службы. Чтобы избежать конфликтов, можно запретить Visual Studio размещать библиотеку службы WCF. 
>
> 1. Выберите проект **жеттингстартедлиб** в **Обозреватель решений** и в контекстном меню выберите пункт **Свойства** .
> 2. Выберите **параметры WCF** и снимите флажок **запустить узел службы WCF при отладке другого проекта в том же решении**.

## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы узнали, как:
> [!div class="checklist"]
>
> - Создание и Настройка проекта консольного приложения для размещения службы WCF.
> - Добавьте код для размещения службы WCF.
> - Обновите файл конфигурации.
> - Запустите службу WCF и убедитесь, что она запущена.

Перейдите к следующему руководству, чтобы научиться создавать клиент WCF.

> [!div class="nextstepaction"]
> [Учебник. Создание клиента WCF](how-to-create-a-wcf-client.md)
