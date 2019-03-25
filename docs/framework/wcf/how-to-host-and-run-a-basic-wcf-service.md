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
ms.openlocfilehash: 38fd9b89e2719be8ce4d33b1b50f68171d587369
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410099"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a>Учебник. Размещение и запуск базовой службы Windows Communication Foundation

В данном учебнике третий из пяти шагов, необходимых для создания базового приложения Windows Communication Foundation (WCF). Обзор руководства, см. в разделе [руководства: Начало работы с приложениями Windows Communication Foundation](getting-started-tutorial.md).

Следующая задача по созданию приложения WCF является размещение службы WCF в консольном приложении. Служба WCF предоставляет один или несколько *конечные точки*, каждая из которых предоставляет одну или несколько операций службы. Конечная точка службы задает следующие сведения: 
- Адрес, где можно найти службу.
- Привязка, которая содержит сведения, описывающие, как клиент должен связаться со службой. 
- Контракт, который определяет возможности, которые эта служба предоставляет клиентам.

В этом руководстве вы узнаете, как:
> [!div class="checklist"]
> - Создайте и настройте проект консольного приложения для размещения службы WCF.
> - Добавьте код для размещения службы WCF.
> - Обновите файл конфигурации.
> - Запуск службы WCF и для проверки выполняется.


## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a>Создание и настройка проекта консольного приложения для размещения службы

1. Создание проекта консольного приложения в Visual Studio: 
 
    1. Из **файл** меню, выберите **откройте** > **решение или проект** и перейдите к **GettingStarted** решения вы ранее созданный (*GettingStarted.sln*). Нажмите кнопку **Открыть**.

    2. Из **представление** меню, выберите **обозревателе решений**.
    
    3. В **обозревателе решений** выберите **GettingStarted** решение (верхний узел), а затем выберите **добавить** > **новый проект** в контекстном меню. 

    4. В **Добавление нового проекта** окно, в левой части окна выберите **Windows Desktop** категорию **Visual C#**  или **Visual Basic**. 

    5. Выберите **консольное приложение (.NET Framework)** шаблона и введите *GettingStartedHost* для **имя**. Нажмите кнопку **ОК**.

2. Добавьте ссылку в **GettingStartedHost** проект **GettingStartedLib** проекта: 

    1. В **обозревателе решений** выберите **ссылки** папке **GettingStartedHost** проекта, а затем выберите **добавить ссылку на** в контекстном меню. 

    2. В **добавить ссылку** диалогового окна в разделе **проекты** в левой части окна выберите **решение**. 
 
    3. Выберите **GettingStartedLib** в центральной части окна, а затем выберите **ОК**. 

       В таком случае типов, определенных в **GettingStartedLib** проекта **GettingStartedHost** проекта.

3. Добавьте ссылку в **GettingStartedHost** проект <xref:System.ServiceModel> сборки: 

    1. В **обозревателе решений** выберите **ссылки** папке **GettingStartedHost** проекта, а затем выберите **добавить ссылку на** в контекстном меню.
    
    2. В **добавить ссылку** окна в разделе **сборки** в левой части окна выберите **Framework**. 

    3. Выберите **System.ServiceModel**, а затем выберите **ОК**. 
    
    4. Сохраните решение, выбрав **файл** > **сохранить все**.

## <a name="add-code-to-host-the-service"></a>Добавьте код для размещения службы

Чтобы разместить службу, добавьте код для выполните следующие действия: 
   1. Создайте URI для базового адреса.
   2. Создайте экземпляр класса для размещения службы.
   3. Создайте конечную точку службы.
   4. Включите обмен метаданными.
   5. Откройте узел службы для прослушивания входящих сообщений.
  
Внесите следующие изменения в код:

1. Откройте **Program.cs** или **Module1.vb** файл **GettingStartedHost** проекта и замените его код следующим кодом:

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
    
    Сведения о том, как работает этот код, см. в разделе [службы размещения действия программы](#service-hosting-program-steps).


2. Обновите свойства проекта:

   1. В **обозревателе решений** выберите **GettingStartedHost** папку, а затем выберите **свойства** в контекстном меню.

   2. На **GettingStartedHost** странице "Свойства" выберите **приложения** вкладке:

      - Для C# проектов, выберите **GettingStartedHost.Program** из **автоматически запускаемый объект** списка.

      - Для проектов Visual Basic, выберите **Service.Program** из **автоматически запускаемый объект** списка.

   3. Из **файл** меню, выберите **сохранить все**.


## <a name="verify-the-service-is-working"></a>Убедитесь, что служба работает

1. Выполните сборку решения, а затем запустите **GettingStartedHost** консоли приложению из Visual Studio. 

    Служба должна выполняться с правами администратора. Так как вы открыли Visual Studio с правами администратора, при запуске **GettingStartedHost** в Visual Studio, приложение запускается с правами администратора, а также. Кроме того, можно открыть новую командную строку с правами администратора (выберите **дополнительные** > **Запуск от имени администратора** в контекстном меню) и запустите **GettingStartedHost.exe**  внутри него.

2. Откройте веб-браузер и перейдите на страницу службы по адресу `http://localhost:8000/GettingStarted/CalculatorService`.
   
   > [!NOTE]
   > Подобные службы требуют необходимое разрешение на регистрацию HTTP-адресов на компьютере для прослушивания. Учетные записи с уровнем доступа администратора имеют данное разрешение, а остальным учетным записям должно быть предоставлено разрешение на использование пространства имен HTTP. Дополнительные сведения о настройке резервирования пространств имен см. в разделе [Настройка протоколов HTTP и HTTPS](feature-details/configuring-http-and-https.md). 


## <a name="service-hosting-program-steps"></a>Службы размещения действия программы

Действия, описанные в код, добавленный к узлу службы из них описаны, следующим образом:

- **Шаг 1**: Создайте экземпляр `Uri` класса, содержащего базовый адрес службы. URL-адрес, содержащий базовый адрес имеет дополнительный URI, который идентифицирует службу. Базовый адрес имеет следующий формат: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`. Базовый адрес для службы калькулятора использует транспорт HTTP, localhost, порт 8000 и сегмент URI, GettingStarted.

- **Шаг 2**: Создайте экземпляр <xref:System.ServiceModel.ServiceHost> класс, который можно использовать для размещения службы. Конструктор принимает два параметра: тип класса, который реализует контракт службы и базовый адрес службы.

- **Шаг 3**: Создайте экземпляр <xref:System.ServiceModel.Description.ServiceEndpoint>. Конечная точка службы состоит из адреса, привязки и контракта службы. <xref:System.ServiceModel.Description.ServiceEndpoint> Конструктора представляет собой тип интерфейса контракта службы, привязку и адрес. Контракт службы - `ICalculator`. Он определен и реализуется в типе службы. Привязка для этого примера является <xref:System.ServiceModel.WSHttpBinding>, который является встроенных привязок и подключается к конечным точкам, соответствующим WS-* спецификации. Дополнительные сведения о привязках WCF см. в разделе [Общие сведения о привязках WCF](bindings-overview.md). Добавить адрес базового адреса для идентификации этой конечной точки. Код указывает адрес как CalculatorService и полного адреса конечной точки как `http://localhost:8000/GettingStarted/CalculatorService`.

    > [!IMPORTANT]
    > .NET Framework версии 4 и более поздних версий Добавление конечной точки службы является необязательным. Для этих версий Если вы не добавите кода или конфигурации, WCF добавляет одну конечную точку по умолчанию для каждого сочетания базового адреса и контракта, реализованном в службе. Дополнительные сведения о конечных точках по умолчанию, см. в разделе [Задание адреса конечной точки](specifying-an-endpoint-address.md). Дополнительные сведения о конечных точках по умолчанию, привязках и поведениях см. в разделе [Упрощенная конфигурация](simplified-configuration.md) и [Упрощенная конфигурация служб WCF](samples/simplified-configuration-for-wcf-services.md).

- **Шаг 4**: Включите обмен метаданными. Клиенты используют обмена метаданными создавать прокси для вызова операций службы. Чтобы включить обмен метаданными, создайте <xref:System.ServiceModel.Description.ServiceMetadataBehavior> экземпляра, установите его <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> свойства `true`и добавьте `ServiceMetadataBehavior` объект <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> коллекцию <xref:System.ServiceModel.ServiceHost> экземпляра.

- **Шаг 5**: Откройте <xref:System.ServiceModel.ServiceHost> для прослушивания входящих сообщений. Приложение ожидает нажатия клавиш **ввод**. После приложение создает экземпляр <xref:System.ServiceModel.ServiceHost>, он выполняет блок try/catch. Дополнительные сведения о перехвате исключений, создаваемых <xref:System.ServiceModel.ServiceHost>, см. в разделе [используйте Close и Abort для освобождения ресурсов клиента WCF](samples/use-close-abort-release-wcf-client-resources.md).

> [!IMPORTANT]
> При добавлении библиотеки службы WCF, Visual Studio размещает ее автоматически при отладке путем запуска узла службы. Во избежание конфликтов можно запретить Visual Studio, на котором размещается в библиотеке служб WCF. 
> 1. Выберите **GettingStartedLib** в проекте **обозревателе решений** и выберите **свойства** в контекстном меню.
> 2. Выберите **параметры WCF** и снимите флажок **запуск узла службы WCF при отладке другого проекта в одном решении**.


## <a name="next-steps"></a>Следующие шаги

В этом руководстве вы узнали, как:
> [!div class="checklist"]
> - Создайте и настройте проект консольного приложения для размещения службы WCF.
> - Добавьте код для размещения службы WCF.
> - Обновите файл конфигурации.
> - Запуск службы WCF и для проверки выполняется.

Перейдите к следующему руководству, чтобы узнать, как создать клиент WCF.

> [!div class="nextstepaction"]
> [Учебник. Создание клиента WCF](how-to-create-a-wcf-client.md)
