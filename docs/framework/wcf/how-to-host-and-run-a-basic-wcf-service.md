---
title: "Практическое руководство. Размещение и запуск базовой службы Windows Communication Foundation"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1e1c00abfec36622f5da493165259fb1786ab8d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a>Практическое руководство. Размещение и запуск базовой службы Windows Communication Foundation
Это третий из шести шагов, необходимый для создания приложения [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]. Общие сведения обо всех шести задач см. в разделе [учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md) раздела.  
  
 В этом разделе описывается размещение службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] в консольном приложении. Эта процедура состоит из следующих шагов:  
  
-   Создайте консольное приложение для размещения службы.  
  
-   Создайте узел службы для данной службы.  
  
-   Включите обмен метаданными.  
  
-   Откройте узел службы.  
  
 Полный список кодов, составленных при выполнении этой задачи, приведен в примере после описания процедуры.  
  
## <a name="to-create-a-new-console-application-to-host-the-service"></a>Создайте новое консольное приложение для размещения службы.  
  
1.  Создайте новый проект консольного приложения, щелкнув решение Приступая к работе, выбрав, **добавить**, **новый проект**. В **Добавление нового проекта** диалогового окна в левой части окна выберите **Windows** под **C#** или **VB**. В центральной части диалогового окна выберите **консольное приложение**. Задайте имя для проекта GettingStartedHost.  
  
2.  Значение целевой платформы проекта GettingStartedHost .NET Framework 4.5, щелкнув правой кнопкой мыши **GettingStartedHost** в обозревателе решений и выбрав **свойства**. В раскрывающемся списке **требуемой версии .NET Framework** выберите **.NET Framework 4.5**. Установка требуемой версии .NET framework для проекта Visual Basic несколько отличается, в диалоговом окне свойств проекта GettingStartedHost, щелкните **компиляции** с левой стороны экрана, а затем щелкните **Advanced компиляции Параметры** кнопки в левом нижнем углу диалогового окна. Выберите **.NET Framework 4.5** в раскрывающемся списке **требуемой версии .NET Framework**.  
  
     Настройка целевой версии .NET framework приведет к [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] к перезагрузке решения, нажмите клавишу **ОК** при появлении запроса.  
  
3.  Добавьте ссылку на проект GettingStartedLib в проект gettingstartedhost, щелкните правой кнопкой мыши **ссылки** папки в проекте GettingStartedHost в обозревателе решений и выберите **Добавление ссылки** . В **добавить ссылку** диалогового окна выберите **решения** с левой стороны диалогового окна, выберите GettingStartedLib в центральной части окна и нажмите кнопку **добавить**. Это делает типы, определенные в GettingStartedLib, доступными в проекте GettingStartedHost.  
  
4.  Добавить ссылку на сборку System.ServiceModel в проекте GettingStartedHost, щелкните правой кнопкой мыши **ссылки** папки в проекте GettingStartedHost в обозревателе решений и выберите **добавить** Ссылка. В **добавить ссылку** окна выберите **Framework** с левой стороны диалогового окна. В текстовом поле «Поиск сборок» введите `System.ServiceModel`. В центральной части диалогового окна выберите **System.ServiceModel**, нажмите кнопку **добавить** и нажмите кнопку **закрыть** кнопки. Сохраните решение, нажав кнопку «Сохранить все» под главным меню.  
  
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
  
    1.  Шаг 1. Создает экземпляр класса с именем с базовым адресом службы. Службы задаются URL-адресом, содержащим базовый адрес и дополнительный универсальный код ресурса (URI). Базовый адрес имеет следующий формат: [транспорт] :// [имя компьютера или домена] [: необязательно порт #] / [необязательно-сегмент URI] базовый адрес службы калькулятора использует транспорт HTTP, localhost, порт 8000 и сегмент URI «Приступая к работе»  
  
    2.  Шаг 2. Создает экземпляр класса <xref:System.ServiceModel.ServiceHost> для размещения службы. Конструктор принимает 2 параметра: тип класса, который реализует контракт службы, и базовый адрес службы.  
  
    3.  Шаг 3 – создает <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` экземпляра. Конечная точка службы состоит из адреса, привязки и контракта службы. <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` Таким образом конструктор принимает тип интерфейса контракта службы, привязку и адрес. Контракт службы - `ICalculator`. Он определен и реализуется в типе службы. В этом образце используется встроенная привязка <xref:System.ServiceModel.WSHttpBinding> для подключения к конечным точкам, соответствующим спецификациями WS-*. Дополнительные сведения о привязках WCF см. в разделе [Общие сведения о привязках WCF](../../../docs/framework/wcf/bindings-overview.md). Адрес добавляется к базовому адресу для определения конечной точки. Адрес, указанный в этом коде является «CalculatorService», поэтому полного адреса конечной точки `"http://localhost:8000/GettingStarted/CalculatorService"` Добавление конечной точки службы, обязательно при использовании .NET Framework 4.0 или более поздней версии. В этих версиях, если конечные точки не заданы в коде или в конфигурации, WCF добавляет одну конечную точку по умолчанию для каждого базового адреса в каждом контракте, реализованном в службе. Дополнительные сведения о умолчанию конечные точки в разделе [Задание адреса конечной точки](../../../docs/framework/wcf/specifying-an-endpoint-address.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)] о конечных точках по умолчанию, привязках и режимах работы см. в разделах [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
        > [!IMPORTANT]
        >  Добавление конечной точки службы не обязательно при использовании .NET Framework 4 или более поздней версии. В этих версиях, если конечные точки не заданы в коде или в конфигурации, WCF добавляет одну конечную точку по умолчанию для каждого базового адреса в каждом контракте, реализованном в службе. Дополнительные сведения о умолчанию конечные точки в разделе [Задание адреса конечной точки](../../../docs/framework/wcf/specifying-an-endpoint-address.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)] о конечных точках по умолчанию, привязках и режимах работы см. в разделах [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
    4.  Шаг 4. Включение обмена метаданными. Клиенты могут использовать обмен метаданными для создания прокси-объектов, которые будут использоваться для вызова операции службы. Включение обмена метаданными создайте <xref:System.ServiceModel.Description.ServiceMetadataBehavior> экземпляра, установите его на <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> свойства `true`и добавьте поведение <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  --> `System.ServiceModel.ServiceHost.Behaviors%2A` коллекцию <xref:System.ServiceModel.ServiceHost> экземпляра.  
  
    5.  Шаг 5. Откройте <xref:System.ServiceModel.ServiceHost>, чтобы прослушивать входящие сообщения. Обратите внимание, что код ожидает, пока пользователь не нажмет ENTER. Если этого не сделать, то приложение немедленно закроется и служба завершит работу. Также обратите внимание, что используется блок try/catch. После создания экземпляра <xref:System.ServiceModel.ServiceHost> другой код находится в блоке try/catch. Дополнительные сведения о перехвате исключений, вызванных безопасно <xref:System.ServiceModel.ServiceHost>, в разделе [как избежать проблем при использовании операторов](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)  
  
### <a name="to-verify-the-service-is-working"></a>Проверка работы службы  
  
1.  Запустите консольное приложение GettingStartedHost с [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]. В [!INCLUDE[wv](../../../includes/wv-md.md)] и более поздних операционных системах служба должна запускаться пользователем с правами администратора. Так как [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] была запущена с правами администратора, GettingStartedHost также запускается с правами администратора. Вы также можете запустить новую командную строку с правами администратора, а затем в ней запустить service.exe.  
  
2.  Откройте Internet Explorer и перейдите на страницу отладки службы по адресу `http://localhost:8000/GettingStarted/CalculatorService`.  
  
## <a name="example"></a>Пример  
 Нижеприведенный пример иллюстрирует создание контракта службы и ее реализацию (см. предыдущие шаги в руководстве), а также размещение службы в консольном приложении.  
  
 Для компиляции с помощью компилятора командной строки, скомпилируйте IService1.cs и Service1.cs в библиотеке класса ссылки на `System.ServiceModel.dll`. Затем скомпилируйте Program.cs в консольное приложение.  
  
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
>  Подобные службы требуют разрешения на регистрацию на компьютере HTTP-адресов, на которые будет ожидаться передача данных. Учетные записи с уровнем доступа администратора имеют данное разрешение, а остальным учетным записям должно быть предоставлено разрешение на использование пространства имен HTTP. [!INCLUDE[crabout](../../../includes/crabout-md.md)]как настроить резервирование пространства имен см. в разделе [Настройка протоколов HTTP и HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md). Запуск файла service.exe на [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] возможен только при наличии прав администратора.  
  
 Сейчас служба запущена. Перейти к [как: создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md). Сведения об устранении неполадок в разделе [Устранение неполадок учебник по началу работы](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).  
  
## <a name="see-also"></a>См. также  
 [Начало работы](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Резидентное размещение](../../../docs/framework/wcf/samples/self-host.md)
