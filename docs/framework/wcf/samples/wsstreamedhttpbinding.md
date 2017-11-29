---
title: WSStreamedHttpBinding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97ce4d3d-ca6f-45fa-b33b-2429bb84e65b
caps.latest.revision: "27"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8238ede6fd43cc5cca2df1f8c7f9162f9c4a1302
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="wsstreamedhttpbinding"></a>WSStreamedHttpBinding
В этом образце показано, как создать привязку, предназначенную для поддержки сценариев работы с потоками при использовании транспорта HTTP.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Binding\WSStreamedHttpBinding`  
  
 Ниже приводятся действия по созданию и настройке новой стандартной привязки.  
  
1.  Создание новой стандартной привязки  
  
     Стандартные привязки в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], такие как basicHttpBinding и netTcpBinding, настраивают соответствующие транспорты и стек каналов под конкретные требования. В этом образце привязка `WSStreamedHttpBinding` настраивает стек каналов на поддержку потоковой передачи. По умолчанию функции WS-Security и надежного обмена сообщениями не добавляются в стек каналов, поскольку обе эти функции не поддерживаются при потоковой передаче. Новая привязка реализуется в классе `WSStreamedHttpBinding`, наследуемом от <xref:System.ServiceModel.Channels.Binding>. `WSStreamedHttpBinding` содержит следующие элементы привязки: <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> и <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>. Класс предоставляет метод `CreateBindingElements()` для настройки результирующего стека привязок, как показано в следующем образце кода.  
  
    ```  
    public override BindingElementCollection CreateBindingElements()  
    {  
         // return collection of BindingElements  
         BindingElementCollection bindingElements = new BindingElementCollection();  
  
        // the order of binding elements within the collection is important: layered channels are applied in the order included, followed by  
        // the message encoder, and finally the transport at the end  
        if (flowTransactions)  
        {  
            bindingElements.Add(transactionFlow);  
        }  
        bindingElements.Add(textEncoding);  
  
        // add transport (http or https)  
        bindingElements.Add(transport);  
        return bindingElements.Clone();  
    }  
    ```  
  
2.  Добавление поддержки конфигурации  
  
     Для предоставления транспорта через конфигурацию в образце реализуется два дополнительных класса -`WSStreamedHttpBindingConfigurationElement` и `WSStreamedHttpBindingSection`. Класс `WSStreamedHttpBindingSection` является типом <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602>, который предоставляет привязку `WSStreamedHttpBinding` системе конфигурации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Основная часть реализации делегируется классу `WSStreamedHttpBindingConfigurationElement`, наследуемому от класса <xref:System.ServiceModel.Configuration.StandardBindingElement>. Класс `WSStreamedHttpBindingConfigurationElement` имеет свойства, соответствующие свойствам класса `WSStreamedHttpBinding`, и функции для сопоставления каждого элемента конфигурации привязке.  
  
     Зарегистрируйте обработчик в системе конфигурации, добавив в файл конфигурации службы следующий раздел.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <extensions>  
          <bindingExtensions>  
            <add name="wsStreamedHttpBinding" type="Microsoft.ServiceModel.Samples.WSStreamedHttpBindingCollectionElement, WSStreamedHttpBinding, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
          </bindingExtensions>  
        </extensions>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     После этого на обработчик можно сослаться из раздела конфигурации serviceModel.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint  
                    address="https://localhost/servicemodelsamples/service.svc"  
                    bindingConfiguration="Binding"  
                    binding="wsStreamedHttpBinding"  
                    contract="Microsoft.ServiceModel.Samples.IStreamedEchoService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Установите [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0, выполнив следующую команду.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  Убедитесь, что вы выполнили шаги, указанные в [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Убедитесь, что вы выполнили [инструкции по установке сертификата сервера Internet Information Services (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).  
  
4.  Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
5.  Для запуска образца в конфигурации между компьютерами, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
6.  При отображении окна клиента введите "Sample.txt". Копия файла "Sample.txt" должна находиться в каталоге пользователя.  
  
## <a name="the-wsstreamedhttpbinding-sample-service"></a>Образец службы WSStreamedHttpBinding  
 Образец службы, использующей привязку `WSStreamedHttpBinding`, расположен в подкаталоге службы. Реализация `OperationContract` использует `MemoryStream` для извлечения всех данных из входящего потока перед возвратом `MemoryStream`. Служба размещается в IIS.  
  
```  
[ServiceContract]  
public interface IStreamedEchoService  
{  
    [OperationContract]  
    Stream Echo(Stream data);  
}  
  
public class StreamedEchoService : IStreamedEchoService  
{  
    public Stream Echo(Stream data)  
    {  
        MemoryStream dataStorage = new MemoryStream();  
        byte[] byteArray = new byte[8192];  
        int bytesRead = data.Read(byteArray, 0, 8192);  
        while (bytesRead > 0)  
        {  
            dataStorage.Write(byteArray, 0, bytesRead);  
            bytesRead = data.Read(byteArray, 0, 8192);  
        }  
        data.Close();  
        dataStorage.Seek(0, SeekOrigin.Begin);  
  
        return dataStorage;  
    }  
}  
```  
  
## <a name="the-wsstreamedhttpbinding-sample-client"></a>Образец клиента WSStreamedHttpBinding  
 Клиент, используемый для взаимодействия со службой с помощью привязки `WSStreamedHttpBinding`, расположен в подкаталоге клиента. При попытке доступа через браузер к адресу HTTPS, такому как https://localhost/servicemodelsamples/service.svc, появляется предупреждение системы безопасности, поскольку сертификат, используемый в этом образце, является тестовым сертификатом, созданным Makecert.exe. Чтобы клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] мог работать с используемым тестовым сертификатом, в клиент был добавлен дополнительный код, подавляющий появление предупреждения системы безопасности. При использовании рабочих сертификатов этот код и соответствующие классы не требуются.  
  
```  
// WARNING: This code is only required for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
## <a name="see-also"></a>См. также
