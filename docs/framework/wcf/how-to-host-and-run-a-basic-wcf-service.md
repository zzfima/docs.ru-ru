---
title: Практическое руководство. Размещение и запуск базовой службы Windows Communication Foundation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: e2bf16bd07c7ac9d918a4ae95d7f4aa185d436ec
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44065384"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a>Практическое руководство. Размещение и запуск базовой службы Windows Communication Foundation
Это третья из шести задач, необходимых для создания приложения Windows Communication Foundation (WCF). Общие сведения обо всех шести задачах можно получить в разделе [Учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
 В этом разделе описывается размещение службы Windows Communication Foundation (WCF) в консольном приложении. Эта процедура состоит из следующих шагов:  
  
-   Создайте консольное приложение для размещения службы.  
  
-   Создайте узел службы для данной службы.  
  
-   Включите обмен метаданными.  
  
-   Откройте узел службы.  
  
 Полный список кодов, составленных при выполнении этой задачи, приведен в примере после описания процедуры.  
  
## <a name="to-create-a-new-console-application-to-host-the-service"></a>Создайте новое консольное приложение для размещения службы.  
  
1.  Создайте новый проект консольного приложения, щелкнув правой кнопкой мыши решение Getting Started (Приступая к работе) и выбрав пункты **Добавить**, **Создать проект**. В диалоговом окне **Добавить новый проект** в левой части окна выберите **Windows** в разделе **C#** или **VB**. В центральной части диалогового окна выберите **Консольное приложение**. Задайте имя для проекта GettingStartedHost.  
  
2.  Выберите нужную версию платформы проекта GettingStartedHost — .NET Framework 4.5, щелкнув правой кнопкой мыши **GettingStartedHost** в обозревателе решений и выбрав пункт **Свойства**. В раскрывающемся списке **Требуемая версия .NET Framework** выберите значение **.NET Framework 4.5**. Установка требуемой версии .NET Framework для проекта Visual Basic несколько отличается от варианта, приведенного выше. В диалоговом окне "Свойства" проекта GettingStartedHost перейдите на вкладку **Компиляция**, а затем нажмите кнопку **Дополнительные параметры компиляции** в нижнем левом углу диалогового окна. Выберите пункт **.NET Framework 4.5** в раскрывающемся списке **Требуемая версия .NET Framework**.  
  
     Указание требуемой версии .NET Framework приведет к перезагрузке решения в среде [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]. Нажмите кнопку **ОК**, когда появится соответствующий запрос.  
  
3.  Добавьте ссылку на проект GettingStartedLib в проект GettingStartedHost, щелкните правой кнопкой мыши папку **Ссылки** в проекте GettingStartedHost в обозревателе решений и выберите **Добавить ссылку**. В диалоговом окне **Добавить ссылку** выберите **Решение** в левой части диалогового окна, выберите GettingStartedLib в центральной части окна и нажмите кнопку **Добавить**. Это делает типы, определенные в GettingStartedLib, доступными в проекте GettingStartedHost.  
  
4.  Добавьте в проект GettingStartedHost ссылку на сборку System.ServiceModel. Для этого в обозревателе решений щелкните правой кнопкой мыши папку **Ссылка** проекта GettingStartedHost и выберите пункт **Добавить** ссылку. В диалоговом окне **Добавить ссылку** выберите в левой части диалогового окна пункт **Платформа**. В текстовом поле «Поиск сборок» введите `System.ServiceModel`. В центральной части диалогового окна выберите **System.ServiceModel**, нажмите кнопку **Добавить**, а затем кнопку **Закрыть**. Сохраните решение, нажав кнопку «Сохранить все» под главным меню.  
  
### <a name="to-host-the-service"></a>Размещение службы  
  
-   Откройте файл Program.cs или Module.vb и введите следующий код:  
  
    ```csharp
    // program.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.ServiceModel;  
    using GettingStartedLib;  
    using System.ServiceModel.Description;   
  
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
    'Module1.vb  
    Imports System  
    Imports System.ServiceModel  
    Imports System.ServiceModel.Description  
    Imports GettingStartedLibVB.GettingStartedLib  
  
    Module Service  
  
        Class Program  
            Shared Sub Main()  
                ' Step 1 Create a URI to serve as the base address  
                Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")  
  
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
  
    1.  Шаг 1. Создает экземпляр класса с именем с базовым адресом службы. Службы задаются URL-адресом, содержащим базовый адрес и дополнительный универсальный код ресурса (URI). Базовый адрес имеет следующий формат: [транспорт]://[имя компьютера или домена][:необязательно — порт #]/[необязательно — сегмент URI]. Базовый адрес службы калькулятора использует транспорт HTTP, localhost, порт 8000 и сегмент URI GettingStarted  
  
    2.  Шаг 2. Создает экземпляр класса <xref:System.ServiceModel.ServiceHost> для размещения службы. Конструктор принимает 2 параметра: тип класса, который реализует контракт службы, и базовый адрес службы.  
  
    3.  Шаг 3. Создает новый экземпляр <xref:System.ServiceModel.Description.ServiceEndpoint>. Конечная точка службы состоит из адреса, привязки и контракта службы. Таким образом, конструктор <xref:System.ServiceModel.Description.ServiceEndpoint> принимает тип интерфейса контракта службы, привязку и адрес. Контракт службы - `ICalculator`. Он определен и реализуется в типе службы. В этом образце используется встроенная привязка <xref:System.ServiceModel.WSHttpBinding> для подключения к конечным точкам, соответствующим спецификациями WS-*. Дополнительные сведения о привязках WCF см. в разделе [Общие сведения о привязках WCF](../../../docs/framework/wcf/bindings-overview.md). Адрес добавляется к базовому адресу для определения конечной точки. Адрес, указанный в этом коде является «CalculatorService», поэтому полный адрес для конечной точки `"http://localhost:8000/GettingStarted/CalculatorService"`.  
  
        > [!IMPORTANT]
        >  Добавление конечной точки службы не обязательно при использовании .NET Framework 4 или более поздней версии. В этих версиях, если конечные точки не заданы в коде или в конфигурации, WCF добавляет одну конечную точку по умолчанию для каждого базового адреса в каждом контракте, реализованном в службе. Дополнительные сведения о конечных точках по умолчанию см. в разделе [Указание адреса конечной точки](../../../docs/framework/wcf/specifying-an-endpoint-address.md). Дополнительные сведения о конечных точках по умолчанию, привязках и режимах работы см. в разделах [Упрощенная конфигурация](../../../docs/framework/wcf/simplified-configuration.md) и [Упрощенная конфигурация служб WCF](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
    4.  Шаг 4. Включение обмена метаданными. Клиенты могут использовать обмен метаданными для создания прокси-объектов, которые будут использоваться для вызова операции службы. Для поддержки обмена метаданными создайте экземпляр <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, установите для свойства <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> значение `true`, добавьте поведение в коллекцию <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A` экземпляра <xref:System.ServiceModel.ServiceHost>.  
  
    5.  Шаг 5. Откройте <xref:System.ServiceModel.ServiceHost>, чтобы прослушивать входящие сообщения. Обратите внимание, что код ожидает, пока пользователь не нажмет ENTER. Если этого не сделать, то приложение немедленно закроется и служба завершит работу. Также обратите внимание, что используется блок try/catch. После создания экземпляра <xref:System.ServiceModel.ServiceHost> другой код находится в блоке try/catch. Дополнительные сведения о перехвате исключений, формируемых системой безопасности <xref:System.ServiceModel.ServiceHost>, см. в разделе [Предотвращение проблем при использовании операторов](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
> [!IMPORTANT]
> Измените файл App.config в GettingStartedLib, чтобы отразить изменения, внесенные в код: 
> 1. Измените строку 14 `<service name="GettingStartedLib.CalculatorService">`
> 2. Измените строку 17 `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
> 3. Измените строку 22 `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`
        
### <a name="to-verify-the-service-is-working"></a>Проверка работы службы  
  
1.  Запустите консольное приложение GettingStartedHost с [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]. В [!INCLUDE[wv](../../../includes/wv-md.md)] и более поздних операционных системах служба должна запускаться пользователем с правами администратора. Так как среда Visual Studio была запущена с правами администратора, GettingStartedHost также запускается с правами администратора. Вы также можете запустить новую командную строку с правами администратора, а затем в ней запустить service.exe.  
  
2.  Откройте Internet Explorer и перейдите на страницу отладки службы по адресу `http://localhost:8000/GettingStarted/CalculatorService`.  
  
## <a name="example"></a>Пример  
 Нижеприведенный пример иллюстрирует создание контракта службы и ее реализацию (см. предыдущие шаги в руководстве), а также размещение службы в консольном приложении.  
  
 Для компиляции с помощью компилятора командной строки скомпилируйте IService1.cs и Service1.cs в библиотеку классов, ссылающуюся на `System.ServiceModel.dll`. Затем скомпилируйте Program.cs в консольное приложение.  
  
```csharp
// IService1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
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
// Service1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
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
//Program.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel;  
using GettingStartedLib;  
using System.ServiceModel.Description;   
  
namespace GettingStartedHost  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Step 1 of the address configuration procedure: Create a URI to serve as the base address.  
            Uri baseAddress = new Uri("http://localhost:8000/ServiceModelSamples/Service");  
  
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
'IService1.vb  
Imports System  
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
'Service1.vb  
Imports System  
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
'Module1.vb  
Imports System  
Imports System.ServiceModel  
Imports System.ServiceModel.Description  
Imports GettingStartedLibVB.GettingStartedLib  
  
Module Service  
  
    Class Program  
        Shared Sub Main()  
            ' Step 1 of the address configuration procedure: Create a URI to serve as the base address.  
            Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")  
  
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
>  Подобные службы требуют разрешения на регистрацию на компьютере HTTP-адресов, на которые будет ожидаться передача данных. Учетные записи с уровнем доступа администратора имеют данное разрешение, а остальным учетным записям должно быть предоставлено разрешение на использование пространства имен HTTP. Дополнительные сведения о настройке резервирования пространств имен см. в разделе [Настройка протоколов HTTP и HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md). Запуск файла service.exe в Visual Studio возможен только при наличии прав администратора.  
  
 Сейчас служба запущена. Переходите к разделу [Практическое руководство. Создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). Сведения об устранении неполадок см. в разделе [Устранение неполадок, связанных с руководством по началу работы](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).  
  
## <a name="see-also"></a>См. также  
 [Начало работы](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Резидентное размещение](../../../docs/framework/wcf/samples/self-host.md)
