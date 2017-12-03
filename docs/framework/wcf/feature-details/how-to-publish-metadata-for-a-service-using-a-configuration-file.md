---
title: "Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f061443f-92df-4824-b36a-609c4cd14a17
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 16e278fd0eb227ddd382157d38c7370e604c35d3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-publish-metadata-for-a-service-using-a-configuration-file"></a>Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации
Это одно из двух практических руководств, в которых демонстрируется публикация метаданных для службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Существуют два способа указать, как служба должна публиковать метаданные: с помощью файла конфигурации и с помощью кода. В этом разделе показано, как публиковать метаданные для службы с помощью файла конфигурации.  
  
> [!CAUTION]
>  В этом разделе показано, как опубликовать метаданные незащищенным образом. Любой клиент может получить метаданные из службы. Если требуется, чтобы службы для публикации метаданных в безопасном режиме, см. раздел [настраиваемый защищенной конечной точки метаданных](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Публикация метаданных в коде, в разделе [как: публикация метаданных для службы с помощью кода](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md). Публикация метаданных позволяет клиентам извлекать метаданные с помощью запроса WS-Transfer GET или запроса HTTP/GET, используя строку запроса `?wsdl`. Чтобы убедиться в работоспособности кода, создайте простую службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Для упрощения в следующем коде представлена несложная резидентная служба.  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Metadata.Samples  
{  
    [ServiceContract]  
    public interface ISimpleService  
    {  
        [OperationContract]  
        string SimpleMethod(string msg);  
    }  
  
    class SimpleService : ISimpleService  
    {  
        public string SimpleMethod(string msg)  
        {  
            Console.WriteLine("The caller passed in " + msg);  
            return "Hello " + msg;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost host = new ServiceHost(typeof(SimpleService),  
                new Uri("http://localhost:8001/MetadataSample"));   
            try  
            {  
                // Open the service host to accept incoming calls  
                host.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                host.Close();  
            }  
            catch (CommunicationException commProblem)  
            {  
                Console.WriteLine("There was a communication problem. " + commProblem.Message);  
                Console.Read();  
            }  
        }  
    }  
}  
```  
  
 Эта служба представляет собой резидентную службу, настраиваемую посредством файла конфигурации. Отправной точкой будет служить следующий файл конфигурации.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Metadata.Example.SimpleService">  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  contract="Metadata.Example.ISimpleService" />  
      </service>  
    </services>  
    <behaviors>  
  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-publish-metadata-for-a-wcf-service-using-an-application-configuration-file"></a>Публикация метаданных для службы WCF с помощью файла конфигурации приложения  
  
1.  В файле App.config после закрывающего элемента `</services>` создайте элемент `<behaviors>`.  
  
  
  
2.  Внутри элемента `<behaviors>` добавьте элемент `<serviceBehaviors>`.  
  
  
  
3.  Добавьте элемент `<behavior>``name` в элемент `<serviceBehaviors>``<behavior>` и задайте значение для атрибута  элемента .  
  
  
  
4.  Добавьте элемент `<serviceMetadata>` в элемент `<behavior>`. Задайте атрибуту `httpGetEnabled` значение `true`, а атрибуту `policyVersion` значение Policy15. `httpGetEnabled` позволяет службе отвечать на запросы метаданных, переданные с помощью запроса HTTP GET. `policyVersion` сообщает службе, что формируемые метаданные должны соответствовать спецификации WS-Policy 1.5.  
  
  
  
5.  Добавьте атрибут `behaviorConfiguration` элементу `<service>``<behavior>` и задайте атрибут `name` элемента , добавленного на шаге 1, как показано в следующем примере кода.  
  
    ```xml  
    <services>  
      <service  
          name="Metadata.Example.SimpleService"  
          behaviorConfiguration="SimpleServiceBehavior">  
        ...  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="SimpleServiceBehavior">  
          <serviceMetadata httpGetEnabled="True" policyVersion="Policy15" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
6.  Добавьте один или несколько элементов `<endpoint>` с контрактом `IMetadataExchange`, как показано в следующем примере кода.  
  
    ```xml  
    <services>  
      <service  
          name="Metadata.Example.SimpleService"  
          behaviorConfiguration="SimpleServiceBehavior">  
  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Metadata.Example.ISimpleService" />  
  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    ```  
  
7.  В конечных точках метаданных, добавленных на предыдущем шаге, присвойте атрибуту `binding` одно из следующих значений:  
  
    -   `mexHttpBinding` для публикации по HTTP;  
  
    -   `mexHttpsBinding` для публикации по HTTPS;  
  
    -   `mexNamedPipeBinding` для публикации по именованному каналу;  
  
    -   `mexTcpBinding` для публикации по TCP.  
  
8.  В конечных точках метаданных, добавленных на предыдущем шаге, задайте для адреса одно из следующих значений:  
  
    -   пустую строку, чтобы использовать в качестве точки публикации базовый адрес ведущего приложения, если базовый адрес совпадает с привязкой метаданных;  
  
    -   относительный адрес, если ведущее приложение имеет базовый адрес;  
  
    -   абсолютный адрес.  
  
9. Постройте и запустите консольное приложение.  
  
10. В программе Internet Explorer перейдите по базовому адресу службы (в данном примере http://localhost:8001/MetadataSample) и убедитесь, что публикация метаданных включена. В противном случае вверху страницы отображается сообщение "Публикация метаданных для этой службы в настоящее время отключена".  
  
### <a name="to-use-default-endpoints"></a>Использование конечных точек по умолчанию  
  
1.  Чтобы настроить метаданные в службе, которая использует конечные точки по умолчанию, укажите <xref:System.ServiceModel.Description.ServiceMetadataBehavior> в файле конфигурации, как показано в предыдущем примере, но не указывайте конечные точки. Файл конфигурации будет иметь следующий вид.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="SimpleServiceBehavior">  
              <serviceMetadata httpGetEnabled="True" policyVersion="Policy12" />  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     Поскольку служба имеет <xref:System.ServiceModel.Description.ServiceMetadataBehavior> со свойством `httpGetEnabled`, установленным в значение `true`, то для службы включена публикация метаданных, а поскольку конечные точки не были добавлены явно, среда выполнения добавляет конечные точки по умолчанию. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]см. по умолчанию конечные точки, привязки и поведения, [упрощенной конфигурации](../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода показана реализация простой службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и файл конфигурации, обеспечивающий публикацию метаданных для этой службы.  
  
```csharp  
using System;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Description;  
  
namespace Metadata.Samples  
{  
    [ServiceContract]  
    public interface ISimpleService  
    {  
        [OperationContract]  
        string SimpleMethod(string msg);  
    }  
  
    class SimpleService : ISimpleService  
    {  
        public string SimpleMethod(string msg)  
        {  
            Console.WriteLine("The caller passed in " + msg);  
            return "Hello " + msg;  
        }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost host = new ServiceHost(typeof(SimpleService),  
                new Uri("http://localhost:8001/MetadataSample"));   
            try  
            {  
                // Open the service host to accept incoming calls  
                host.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                host.Close();  
            }  
            catch (CommunicationException commProblem)  
            {  
                Console.WriteLine("There was a communication problem. " + commProblem.Message);  
                Console.Read();  
            }  
        }  
    }  
}  
```  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="SimpleServiceBehavior">  
          <serviceMetadata httpGetEnabled="True" policyVersion="Policy12" />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
 [Практическое руководство. Размещение службы WCF в управляемом приложении](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)  
 [Резидентное размещение](../../../../docs/framework/wcf/samples/self-host.md)  
 [Общие сведения об архитектуре метаданных](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)  
 [Использование метаданных](../../../../docs/framework/wcf/feature-details/using-metadata.md)  
 [Как: публикация метаданных для службы в коде](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)
