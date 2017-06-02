---
title: "Пользовательская конечная точка защищенных метаданных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9e369e99-ea4a-49ff-aed2-9fdf61091a48
caps.latest.revision: 19
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 19
---
# Пользовательская конечная точка защищенных метаданных
В этом образце показано, как реализовать службу с защищенной конечной точкой метаданных, которая использует одну из привязок, не предназначенную для обмена метаданными, и как настроить средство [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) или клиентов на извлечение метаданных из такой конечной точки метаданных.Существует две системные привязки для предоставления конечных точек метаданных: mexHttpBinding и mexHttpsBinding.Привязка mexHttpBinding используется для предоставления конечной точки метаданных через HTTP в незащищенном режиме.Привязка mexHttpsBinding используется для предоставления конечной точки метаданных через HTTP в защищенном режиме.В этом образце описывается предоставление защищенной конечной точки метаданных с использованием объекта <xref:System.ServiceModel.WSHttpBinding>.Такой подход следует использовать, если требуется изменить параметры безопасности привязки, но при этом нежелательно использовать протокол HTTPS.При использовании привязки mexHttpsBinding конечная точка метаданных будет защищена, но изменение параметров привязки окажется невозможным.  
  
> [!NOTE]
>  Процедура установки и инструкции по построению для этого образца приведены в конце этого раздела.  
  
## Служба  
 Служба в образце имеет две конечные точки.Конечная точка приложения служит в качестве контракта `ICalculator` для привязки `WSHttpBinding` с включенным сеансом `ReliableSession` и режимом безопасности `Message` с использованием сертификатов.Конечная точка метаданных также использует привязку `WSHttpBinding` с аналогичными параметрами безопасности, но без `ReliableSession`.Соответствующая конфигурация представлена ниже.  
  
```  
<services>  
    …  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
            behaviorConfiguration="CalculatorServiceBehavior">  
     <!-- use base address provided by host -->  
     <endpoint address=""  
       binding="wsHttpBinding"  
       bindingConfiguration="Binding2"  
       contract="Microsoft.ServiceModel.Samples.ICalculator" />  
     <endpoint address="mex"  
       binding="wsHttpBinding"  
       bindingConfiguration="Binding1"  
       contract="IMetadataExchange" />  
     </service>  
 </services>  
 <bindings>  
   <wsHttpBinding>  
     <binding name="Binding1">  
       <security mode="Message">  
         <message clientCredentialType="Certificate" />  
       </security>  
     </binding>  
     <binding name="Binding2">  
       <reliableSession inactivityTimeout="00:01:00" enabled="true" />  
       <security mode="Message">  
         <message clientCredentialType="Certificate" />  
       </security>  
     </binding>  
   </wsHttpBinding>  
 </bindings>  
```  
  
 Во многих других образцах конечная точка метаданных использует привязку по умолчанию `mexHttpBinding`, которая не является безопасной.В данном примере безопасность метаданных обеспечивается с помощью привязки `WSHttpBinding` с режимом безопасности `Message`.Чтобы клиенты метаданных могли извлекать эти метаданные, они должны быть настроены с соответствующей привязкой.В образце показаны два таких клиента.  
  
 Первый клиент использует Svcutil.exe для извлечения метаданных, а также создания клиентского кода и конфигурации во время разработки.Поскольку служба использует для метаданных привязку, отличную от привязки по умолчанию, средство Svcutil.exe необходимо настроить определенным образом, чтобы оно могло получать метаданные из службы с помощью данной привязки.  
  
 Второй клиент использует распознаватель `MetadataResolver` с целью динамического извлечения метаданных для известного контракта с последующим вызовом операций на динамически создаваемом клиенте.  
  
## Клиент Svcutil  
 При использовании привязки по умолчанию для размещения конечной точки `IMetadataExchange` можно запустить Svcutil.exe с указанием адреса этой конечной точки.  
  
```  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 И это будет работать.Однако в этом образце для размещения метаданных сервер использует привязку, отличную от привязки по умолчанию.Поэтому средство Svcutil.exe необходимо настроить на использование правильной привязки.Это можно сделать с помощью файла Svcutil.exe.config.  
  
 Файл Svcutil.exe.config выглядит как обычный файл конфигурации клиента.Единственными необычными аспектами являются имя и контракт конечной точки клиента:  
  
```  
<endpoint name="http"  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"  
          behaviorConfiguration="ClientCertificateBehavior"  
          contract="IMetadataExchange" />  
```  
  
 Имя конечной точки должно совпадать с именем схемы адреса, по которому размещаются метаданные, а контрактом конечной точки должен быть `IMetadataExchange`.Таким образом, при запуске команды  
  
```  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 выполняется поиск конечной точки с именем "http" и контракта `IMetadataExchange` для настройки привязки и поведения при взаимодействии с конечной точкой метаданных.В остальной части файла Svcutil.exe.config в образце определяются конфигурация привязки и учетные данные поведения для соответствия конфигурации сервера конечной точки метаданных.  
  
 Чтобы средство Svcutil.exe могло использовать конфигурацию, заданную в файле Svcutil.exe.config, файл Svcutil.exe должен находиться в одном каталоге с файлом конфигурации.Таким образом, необходимо скопировать файл Svcutil.exe из расположения установки в каталог, содержащий файл Svcutil.exe.config.Затем из этого каталога необходимо выполнить следующую команду:  
  
```  
.\svcutil.exe http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 Начальнаяточка с обратной косой чертой ".'\\" в начале команды гарантирует, что будет выполнена копия Svcutil.exe, расположенная в данном каталоге \(для которой задан соответствующий файл Svcutil.exe.config\).  
  
## Клиент MetadataResolver  
 Если клиенту известен контракт и способ обращения к метаданным во время разработки, клиент может динамически определять привязку и адрес конечных точек приложения с помощью распознавателя `MetadataResolver`.Это демонстрируется в данном образце клиента: показано, как настроить привязку и учетные данные, используемые распознавателем `MetadataResolver`, путем создания и настройки клиента `MetadataExchangeClient`.  
  
 Информацию о привязке и сертификате, указанную в файле Svcutil.exe.config, можно задать императивно в клиенте `MetadataExchangeClient`:  
  
```  
// Specify the Metadata Exchange binding and its security mode  
WSHttpBinding mexBinding = new WSHttpBinding(SecurityMode.Message);  
mexBinding.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
// Create a MetadataExchangeClient for retrieving metadata, and set the // certificate details  
MetadataExchangeClient mexClient = new MetadataExchangeClient(mexBinding);  
mexClient.SoapCredentials.ClientCertificate.SetCertificate(    StoreLocation.CurrentUser, StoreName.My,  
    X509FindType.FindBySubjectName, "client.com");  
mexClient.SoapCredentials.ServiceCertificate.Authentication.    CertificateValidationMode =    X509CertificateValidationMode.PeerOrChainTrust;  
mexClient.SoapCredentials.ServiceCertificate.SetDefaultCertificate(    StoreLocation.CurrentUser, StoreName.TrustedPeople,  
    X509FindType.FindBySubjectName, "localhost");  
```  
  
 При настроенном клиенте `mexClient` можно перечислить требуемые контракты и использовать распознаватель `MetadataResolver` для получения списка конечных точек с этими контрактами.  
  
```  
// The contract we want to fetch metadata for  
Collection<ContractDescription> contracts =    new Collection<ContractDescription>();  
ContractDescription contract =    ContractDescription.GetContract(typeof(ICalculator));  
contracts.Add(contract);  
// Find endpoints for that contract  
EndpointAddress mexAddress = new    EndpointAddress(ConfigurationManager.AppSettings["mexAddress"]);  
ServiceEndpointCollection endpoints =    MetadataResolver.Resolve(contracts, mexAddress, mexClient);  
```  
  
 Наконец, можно использовать информацию из этих конечных точек для инициализации привязки и адреса фабрики `ChannelFactory`, используемой для создания каналов взаимодействия с конечными точками приложения.  
  
```  
ChannelFactory<ICalculator> cf = new    ChannelFactory<ICalculator>(endpoint.Binding, endpoint.Address);  
```  
  
 Основная задача данного образца клиента — показать, что при использовании распознавателя `MetadataResolver` и необходимости задания пользовательских привязок или поведений для обмена метаданными можно использовать клиент `MetadataExchangeClient` для задания этих пользовательских параметров.  
  
#### Настройка и построение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы построить решение, следуйте инструкциям раздела [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
#### Запуск образца на том же компьютере  
  
1.  Запустите файл Setup.bat из папки установки образца.При этом устанавливаются все сертификаты, необходимые для запуска образца.Обратите внимание, что файл Setup.bat использует средство FindPrivateKey.exe, которое устанавливается путем запуска файла setupCertTool.bat, указанного в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Запустите клиентское приложение из каталога \\MetadataResolverClient\\bin или \\SvcutilClient\\bin.Действия клиента отображаются в консольном приложении клиента.  
  
3.  Если клиенту и службе не удается взаимодействовать, см. раздел [Troubleshooting Tips](http://msdn.microsoft.com/ru-ru/8787c877-5e96-42da-8214-fa737a38f10b).  
  
4.  После завершения работы образца запустите файл Cleanup.bat, чтобы удалить сертификаты.В других образцах обеспечения безопасности используются те же сертификаты.  
  
#### Выполнение образца на нескольких компьютерах  
  
1.  На сервере выполните команду `setup.bat service`.При выполнении команды `setup.bat` с аргументом `service` создается сертификат службы с полным именем домена компьютера, который экспортируется в файл с именем Service.cer.  
  
2.  Измените Web.config на сервере так, чтобы в файле отражалось новое имя сертификата.Для этого необходимо изменить атрибут `findValue` в элементе [\<serviceCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) на полное доменное имя компьютера.  
  
3.  Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.  
  
4.  На клиенте выполните команду `setup.bat client`.При выполнении команды `setup.bat` с аргументом `client` создается сертификат клиента с именем Client.com, который экспортируется в файл с именем Client.cer.  
  
5.  В файле App.config клиента `MetadataResolverClient` на клиентском компьютере измените значение адреса конечной точки обмена метаданными, чтобы оно соответствовало новому адресу службы.Для этого замените имя localhost полным именем домена сервера.Кроме того, замените вхождение "localhost" в файле metadataResolverClient.cs новым именем сертификата службы \(полным доменным именем сервера\).Выполните то же самое для файла App.config проекта SvcutilClient.  
  
6.  Скопируйте файл Client.cer из клиентского каталога в каталог службы на сервере.  
  
7.  На клиенте запустите файл `ImportServiceCert.bat`.Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser \- TrustedPeople.  
  
8.  На сервере запустите файл `ImportClientCert.bat`. Он импортирует сертификат клиента из файла Client.cer в хранилище LocalMachine \- TrustedPeople.  
  
9. На компьютере службы выполните построение проекта службы в Visual Studio и выберите страницу справки в веб\-браузере, чтобы проверить что она запущена.  
  
10. На клиентском компьютере запустите клиент MetadataResolverClient или SvcutilClient из VS.  
  
    1.  Если клиенту и службе не удается взаимодействовать, см. раздел [Troubleshooting Tips](http://msdn.microsoft.com/ru-ru/8787c877-5e96-42da-8214-fa737a38f10b).  
  
#### Очистка после образца  
  
-   После завершения работы образца запустите в папке образцов файл Cleanup.bat.  
  
    > [!NOTE]
    >  Этот скрипт не удаляет сертификаты службы на клиенте при выполнении образца на нескольких компьютерах.Если образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], в которых использовались сертификаты, выполнялись на нескольких компьютерах, обязательно удалите сертификаты службы, которые были установлены в хранилище «CurrentUser \- TrustedPeople».Для этого используйте следующую команду: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`.Например, `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Extensibility\Metadata\CustomMexEndpoint`  
  
## См. также