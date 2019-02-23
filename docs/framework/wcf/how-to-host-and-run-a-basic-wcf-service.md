---
title: Размещение и запуск базовой службы Windows Communication Foundation
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 73633c2c6119204f2fb608b32ae794a2e07b27d0
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747078"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a>Размещение и запуск базовой службы Windows Communication Foundation

Это третья из шести задач, необходимых для создания приложения Windows Communication Foundation (WCF). Общие сведения обо всех шести задачах можно получить в разделе [Учебник по началу работы](getting-started-tutorial.md).

В этом разделе описывается размещение службы Windows Communication Foundation (WCF) в консольном приложении. Эта процедура состоит из следующих шагов:

- Создайте консольное приложение для размещения службы.

- Создайте узел службы для данной службы.

- Включите обмен метаданными.

- Откройте узел службы.

Полный список кодов, составленных при выполнении этой задачи, приведен в примере после описания процедуры.

## <a name="create-a-new-console-application-to-host-the-service"></a>Создайте новое консольное приложение для размещения службы

1. Создайте новый проект консольного приложения в Visual Studio, щелкнув решение Приступая к работе и выбрав **добавить** > **новый проект**. В **Добавление нового проекта** диалоговое окно, в левой части окна выберите **Windows Desktop** категорию **Visual C#** или **Visual Basic**. Выберите **консольное приложение (.NET Framework)** шаблона и назовите проект **GettingStartedHost**.

2. Добавьте ссылку на проект GettingStartedLib в проект GettingStartedHost. Щелкните правой кнопкой мыши **ссылки** папки в проекте GettingStartedHost в **обозревателе решений**, а затем выберите **добавить ссылку**. В **добавить ссылку** диалоговом окне выберите **решение** в левой части диалогового окна, выберите GettingStartedLib в центральной части диалогового окна и выберите **добавить**. Это делает типы, определенные в GettingStartedLib, доступными в проекте GettingStartedHost.

3. Добавьте ссылку на сборку System.ServiceModel в проекте GettingStartedHost. Щелкните правой кнопкой мыши **ссылки** папки в проекте GettingStartedHost в **обозревателе решений** и выберите **добавить ссылку**. В **добавить ссылку** диалоговом окне выберите **Framework** в левой части диалогового окна в разделе **сборки**. Найдите и выберите **System.ServiceModel**, а затем выберите **ОК**. Сохраните решение, выбрав **файл** > **сохранить все**.

## <a name="host-the-service"></a>Размещение службы

Откройте файл Program.cs или Module.vb и введите следующий код:

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
            // Step 1 Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

            // Step 2 Create a ServiceHost instance
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

            try
            {
                // Step 3 Add a service endpoint.
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                // Step 4 Enable metadata exchange.
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                smb.HttpGetEnabled = true;
                selfHost.Description.Behaviors.Add(smb);

                // Step 5 Start the service.
                selfHost.Open();
                Console.WriteLine("The service is ready.");
                Console.WriteLine("Press <ENTER> to terminate service.");
                Console.WriteLine();
                Console.ReadLine();

                // Close the ServiceHostBase to shutdown the service.
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
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 Create a URI to serve as the base address
            Dim baseAddress As New Uri("http://localhost:8000/GettingStarted")

            ' Step 2 Create a ServiceHost instance
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
           Try

                ' Step 3 Add a service endpoint
                ' Add a service endpoint
                selfHost.AddServiceEndpoint( _
                    GetType(ICalculator), _
                    New WSHttpBinding(), _
                    "CalculatorService")

                ' Step 4 Enable metadata exchange.
                Dim smb As New ServiceMetadataBehavior()
                smb.HttpGetEnabled = True
                selfHost.Description.Behaviors.Add(smb)

                ' Step 5 Start the service
                selfHost.Open()
                Console.WriteLine("The service is ready.")
                Console.WriteLine("Press <ENTER> to terminate service.")
                Console.WriteLine()
                Console.ReadLine()

                ' Close the ServiceHostBase to shutdown the service.
                selfHost.Close()
            Catch ce As CommunicationException
                Console.WriteLine("An exception occurred: {0}", ce.Message)
                selfHost.Abort()
            End Try
        End Sub
    End Class

End Module
```

**Шаг 1** -создает экземпляр класса Uri для хранения базового адреса службы. Службы задаются URL-адресом, содержащим базовый адрес и дополнительный универсальный код ресурса (URI). Базовый адрес имеет следующий формат: [транспорт]://[имя компьютера или домена][:необязательно — порт #]/[необязательно — сегмент URI]. Базовый адрес службы калькулятора использует транспорт HTTP, localhost, порт 8000 и сегмент URI GettingStarted

**Шаг 2** — создает экземпляр класса <xref:System.ServiceModel.ServiceHost> класса для размещения службы. Конструктор принимает 2 параметра: тип класса, который реализует контракт службы, и базовый адрес службы.

**Шаг 3** — создание <xref:System.ServiceModel.Description.ServiceEndpoint> экземпляра. Конечная точка службы состоит из адреса, привязки и контракта службы. Таким образом, конструктор <xref:System.ServiceModel.Description.ServiceEndpoint> принимает тип интерфейса контракта службы, привязку и адрес. Контракт службы - `ICalculator`. Он определен и реализуется в типе службы. В этом образце используется встроенная привязка <xref:System.ServiceModel.WSHttpBinding> для подключения к конечным точкам, соответствующим спецификациями WS-*. Дополнительные сведения о привязках WCF см. в разделе [Общие сведения о привязках WCF](bindings-overview.md). Адрес добавляется к базовому адресу для определения конечной точки. Адрес, указанный в этом коде является «CalculatorService», поэтому полный адрес для конечной точки `"http://localhost:8000/GettingStarted/CalculatorService"`.

> [!IMPORTANT]
> Добавление конечной точки службы не обязательно при использовании .NET Framework 4 или более поздней версии. В этих версиях, если конечные точки не заданы в коде или в конфигурации, WCF добавляет одну конечную точку по умолчанию для каждого базового адреса в каждом контракте, реализованном в службе. Дополнительные сведения о конечных точках по умолчанию см. в разделе [Указание адреса конечной точки](specifying-an-endpoint-address.md). Дополнительные сведения о конечных точках по умолчанию, привязках и режимах работы см. в разделах [Упрощенная конфигурация](simplified-configuration.md) и [Упрощенная конфигурация служб WCF](./samples/simplified-configuration-for-wcf-services.md).

**Шаг 4** — включите обмен метаданными. Клиенты могут использовать обмен метаданными для создания прокси-объектов, которые будут использоваться для вызова операции службы. Для поддержки обмена метаданными создайте экземпляр <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, установите <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> в значении `true`, добавьте поведение в коллекцию <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> экземпляра <xref:System.ServiceModel.ServiceHost>.

**Шаг 5** — откройте <xref:System.ServiceModel.ServiceHost> для прослушивания входящих сообщений. Обратите внимание, что код ожидает, пока пользователь не нажмет ENTER. Если этого не сделать, то приложение немедленно закроется и служба завершит работу. Также обратите внимание, что используется блок try/catch. После создания экземпляра <xref:System.ServiceModel.ServiceHost> другой код находится в блоке try/catch. Дополнительные сведения о перехвате исключений, создаваемых <xref:System.ServiceModel.ServiceHost>, см. в разделе [используйте Close и Abort для освобождения ресурсов клиента WCF](samples/use-close-abort-release-wcf-client-resources.md)

> [!IMPORTANT]
> При добавлении библиотеки службы WCF, Visual Studio можно разместить его автоматически при отладке путем запуска узла службы. Во избежание конфликтов можно отключить это. 
> 1. Откройте свойства проекта для GettingStartedLib.
> 2. Перейдите к **параметры WCF** и снимите флажок **запуск узла службы WCF при отладке**.

## <a name="verify-the-service-is-working"></a>Убедитесь, что служба работает

1. Запустите консоль GettingStartedHost приложению из Visual Studio.

   Служба должна выполняться с правами администратора. Поскольку Visual Studio был открыт с правами администратора, GettingStartedHost также запускается с правами администратора. Также можно открыть новую командную строку, используя **Запуск от имени администратора** и в ней запустить service.exe.

2. Откройте веб-браузер и перейдите на страницу отладки службы по адресу `http://localhost:8000/GettingStarted/`. **Обратите внимание! Имеет значение заканчивается косой черты.**

## <a name="example"></a>Пример

Нижеприведенный пример иллюстрирует создание контракта службы и ее реализацию (см. предыдущие шаги в руководстве), а также размещение службы в консольном приложении.

Для компиляции с помощью компилятора командной строки, скомпилируйте IService1.cs и Service1.cs в библиотеку классов, который ссылается на `System.ServiceModel.dll`. Скомпилируйте Program.cs в консольном приложении.

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
        [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
        public interface ICalculator
        {
            [OperationContract]
            double Add(double n1, double n2);
            [OperationContract]
            double Subtract(double n1, double n2);
            [OperationContract]
            double Multiply(double n1, double n2);
            [OperationContract]
            double Divide(double n1, double n2);
        }
}
```

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    public class CalculatorService : ICalculator
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            // Code added to write output to the console window.
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

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
            // Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

            // Step 2 of the hosting procedure: Create ServiceHost
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

            try
            {
                // Step 3 of the hosting procedure: Add a service endpoint.
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                // Step 4 of the hosting procedure: Enable metadata exchange.
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                smb.HttpGetEnabled = true;
                selfHost.Description.Behaviors.Add(smb);

                // Step 5 of the hosting procedure: Start (and then stop) the service.
                selfHost.Open();
                Console.WriteLine("The service is ready.");
                Console.WriteLine("Press <ENTER> to terminate service.");
                Console.WriteLine();
                Console.ReadLine();

                // Close the ServiceHostBase to shutdown the service.
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

Namespace GettingStartedLib

    <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
    Public Interface ICalculator

        <OperationContract()> _
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
    End Interface
End Namespace
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    Public Class CalculatorService
        Implements ICalculator

        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
            Dim result As Double = n1 + n2
            ' Code added to write output to the console window.
            Console.WriteLine("Received Add({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result
        End Function

        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
            Dim result As Double = n1 - n2
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
            Dim result As Double = n1 * n2
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
            Dim result As Double = n1 / n2
            Console.WriteLine("Received Divide({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function
    End Class
End Namespace
```

```vb
Imports System.ServiceModel
Imports System.ServiceModel.Description
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

            ' Step 2 of the hosting procedure: Create ServiceHost
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
            Try

                ' Step 3 of the hosting procedure: Add a service endpoint.
                ' Add a service endpoint
                selfHost.AddServiceEndpoint( _
                    GetType(ICalculator), _
                    New WSHttpBinding(), _
                    "CalculatorService")

                ' Step 4 of the hosting procedure: Enable metadata exchange.
                ' Enable metadata exchange
                Dim smb As New ServiceMetadataBehavior()
                smb.HttpGetEnabled = True
                selfHost.Description.Behaviors.Add(smb)

                ' Step 5 of the hosting procedure: Start (and then stop) the service.
                selfHost.Open()
                Console.WriteLine("The service is ready.")
                Console.WriteLine("Press <ENTER> to terminate service.")
                Console.WriteLine()
                Console.ReadLine()

                ' Close the ServiceHostBase to shutdown the service.
                selfHost.Close()
            Catch ce As CommunicationException
                Console.WriteLine("An exception occurred: {0}", ce.Message)
                selfHost.Abort()
            End Try
        End Sub
    End Class

End Module
```

> [!NOTE]
> Подобные службы требуют разрешения на регистрацию на компьютере HTTP-адресов, на которые будет ожидаться передача данных. Учетные записи с уровнем доступа администратора имеют данное разрешение, а остальным учетным записям должно быть предоставлено разрешение на использование пространства имен HTTP. Дополнительные сведения о настройке резервирования пространств имен см. в разделе [Настройка протоколов HTTP и HTTPS](feature-details/configuring-http-and-https.md). Запуск файла service.exe в Visual Studio возможен только при наличии прав администратора.

## <a name="next-steps"></a>Следующие шаги

Сейчас служба запущена. В следующей задаче вы создадите клиента WCF.

> [!div class="nextstepaction"]
> [Практическое руководство. Создание клиента WCF](how-to-create-a-wcf-client.md)

Сведения об устранении неполадок см. в разделе [Устранение неполадок, связанных с руководством по началу работы](troubleshooting-the-getting-started-tutorial.md).

## <a name="see-also"></a>См. также

- [Начало работы](samples/getting-started-sample.md)
- [Резидентное размещение](samples/self-host.md)
- [Размещение служб](hosting-services.md)
