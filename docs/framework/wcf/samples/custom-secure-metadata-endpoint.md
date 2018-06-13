---
title: Пользовательская конечная точка защищенных метаданных
ms.date: 03/30/2017
ms.assetid: 9e369e99-ea4a-49ff-aed2-9fdf61091a48
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2baa99ddaf5de60407b233b5a6ea013ad87401f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33508065"
---
# <a name="custom-secure-metadata-endpoint"></a>Пользовательская конечная точка защищенных метаданных
Этот образец демонстрирует реализацию службы, конечную точку метаданных, безопасности, использующий одну из привязок, не принадлежащий метаданным exchange и настройте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) или клиентов для выборки метаданные из такой конечной точки метаданных. Существует две системные привязки для предоставления конечных точек метаданных: mexHttpBinding и mexHttpsBinding. Привязка mexHttpBinding используется для предоставления конечной точки метаданных через HTTP в незащищенном режиме. Привязка mexHttpsBinding используется для предоставления конечной точки метаданных через HTTP в защищенном режиме. В этом образце описывается предоставление защищенной конечной точки метаданных с использованием объекта <xref:System.ServiceModel.WSHttpBinding>. Такой подход следует использовать, если требуется изменить параметры безопасности привязки, но при этом нежелательно использовать протокол HTTPS. При использовании привязки mexHttpsBinding конечная точка метаданных будет защищена, но изменение параметров привязки окажется невозможным.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
## <a name="service"></a>Служба  
 Служба в образце имеет две конечные точки. Конечная точка приложения служит в качестве контракта `ICalculator` для привязки `WSHttpBinding` с включенным сеансом `ReliableSession` и режимом безопасности `Message` с использованием сертификатов. Конечная точка метаданных также использует привязку `WSHttpBinding` с аналогичными параметрами безопасности, но без `ReliableSession`. Соответствующая конфигурация представлена ниже.  
  
```xml  
<services>   
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
  
 Во многих других образцах конечная точка метаданных использует привязку по умолчанию `mexHttpBinding`, которая не является безопасной. В данном примере безопасность метаданных обеспечивается с помощью привязки `WSHttpBinding` с режимом безопасности `Message`. Чтобы клиенты метаданных могли извлекать эти метаданные, они должны быть настроены с соответствующей привязкой. В образце показаны два таких клиента.  
  
 Первый клиент использует Svcutil.exe для извлечения метаданных, а также создания клиентского кода и конфигурации во время разработки. Поскольку служба использует для метаданных привязку, отличную от привязки по умолчанию, средство Svcutil.exe необходимо настроить определенным образом, чтобы оно могло получать метаданные из службы с помощью данной привязки.  
  
 Второй клиент использует распознаватель `MetadataResolver` с целью динамического извлечения метаданных для известного контракта с последующим вызовом операций на динамически создаваемом клиенте.  
  
## <a name="svcutil-client"></a>Клиент Svcutil  
 При использовании привязки по умолчанию для размещения конечной точки `IMetadataExchange` можно запустить Svcutil.exe с указанием адреса этой конечной точки.  
  
```  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 И это будет работать. Однако в этом образце для размещения метаданных сервер использует привязку, отличную от привязки по умолчанию. Поэтому средство Svcutil.exe необходимо настроить на использование правильной привязки. Это можно сделать с помощью файла Svcutil.exe.config.  
  
 Файл Svcutil.exe.config выглядит как обычный файл конфигурации клиента. Единственными необычными аспектами являются имя и контракт конечной точки клиента:  
  
```xml  
<endpoint name="http"  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"  
          behaviorConfiguration="ClientCertificateBehavior"  
          contract="IMetadataExchange" />  
```  
  
 Имя конечной точки должно совпадать с именем схемы адреса, по которому размещаются метаданные, а контрактом конечной точки должен быть `IMetadataExchange`. Таким образом, при запуске команды  
  
```  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 выполняется поиск конечной точки с именем "http" и контракта `IMetadataExchange` для настройки привязки и поведения при взаимодействии с конечной точкой метаданных. В остальной части файла Svcutil.exe.config в образце определяются конфигурация привязки и учетные данные поведения для соответствия конфигурации сервера конечной точки метаданных.  
  
 Чтобы средство Svcutil.exe могло использовать конфигурацию, заданную в файле Svcutil.exe.config, файл Svcutil.exe должен находиться в одном каталоге с файлом конфигурации. Таким образом, необходимо скопировать файл Svcutil.exe из расположения установки в каталог, содержащий файл Svcutil.exe.config. Затем из этого каталога необходимо выполнить следующую команду:  
  
```  
.\svcutil.exe http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 Начальные». \\«гарантирует, что копия Svcutil.exe в этом каталоге (тот, который имеет соответствующий файл Svcutil.exe.config) запускается.  
  
## <a name="metadataresolver-client"></a>Клиент MetadataResolver  
 Если клиенту известен контракт и способ обращения к метаданным во время разработки, клиент может динамически определять привязку и адрес конечных точек приложения с помощью распознавателя `MetadataResolver`. Это демонстрируется в данном образце клиента: показано, как настроить привязку и учетные данные, используемые распознавателем `MetadataResolver`, путем создания и настройки клиента `MetadataExchangeClient`.  
  
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
  
 Основная задача данного образца клиента - показать, что при использовании распознавателя `MetadataResolver` и необходимости задания пользовательских привязок или поведений для обмена метаданными можно использовать клиент `MetadataExchangeClient` для задания этих пользовательских параметров.  
  
#### <a name="to-set-up-and-build-the-sample"></a>Настройка и сборка образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a>Запуск образца на том же компьютере  
  
1.  Запустите файл Setup.bat из папки установки примера. При этом устанавливаются все сертификаты, необходимые для выполнения образца. Обратите внимание, что файл Setup.bat использует средство FindPrivateKey.exe, которое устанавливается при запуске setupCertTool.bat из [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Запустите клиентское приложение из каталога \MetadataResolverClient\bin или \SvcutilClient\bin. Действия клиента отображаются в консольном приложении клиента.  
  
3.  Если клиенту и службе не удается взаимодействовать, см. раздел [советы по устранению неполадок](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
4.  После завершения работы образца запустите файл Cleanup.bat, чтобы удалить сертификаты. В других образцах обеспечения безопасности используются те же сертификаты.  
  
#### <a name="to-run-the-sample-across-machines"></a>Выполнение примера на нескольких компьютерах  
  
1.  На сервере выполните команду `setup.bat service`. Под управлением `setup.bat` с `service` аргумент создается сертификат службы с полным доменным именем компьютера и экспортируется в файл с именем Service.cer.  
  
2.  Измените Web.config на сервере так, чтобы в файле отражалось новое имя сертификата. То есть изменить `findValue` атрибута в [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) элемента, который требуется полное доменное имя компьютера.  
  
3.  Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.  
  
4.  На клиенте выполните команду `setup.bat client`. Под управлением `setup.bat` с `client` создается сертификат клиента с именем Client.com, который экспортируется в файл с именем Client.cer.  
  
5.  В файле App.config клиента `MetadataResolverClient` на клиентском компьютере измените значение адреса конечной точки обмена метаданными, чтобы оно соответствовало новому адресу службы. Для этого замените имя localhost полным именем домена сервера. Кроме того, замените вхождение "localhost" в файле metadataResolverClient.cs новым именем сертификата службы (полным доменным именем сервера). Выполните то же самое для файла App.config проекта SvcutilClient.  
  
6.  Скопируйте файл Client.cer из клиентского каталога в каталог службы на сервере.  
  
7.  На клиенте выполните команду `ImportServiceCert.bat`. Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser - TrustedPeople.  
  
8.  На сервере запустите файл `ImportClientCert.bat`. Он импортирует сертификат клиента из файла Client.cer в хранилище LocalMachine - TrustedPeople.  
  
9. На компьютере службы выполните построение проекта службы в Visual Studio и выберите страницу справки в веб-браузере, чтобы проверить что она запущена.  
  
10. На клиентском компьютере запустите клиент MetadataResolverClient или SvcutilClient из VS.  
  
    1.  Если клиенту и службе не удается взаимодействовать, см. раздел [советы по устранению неполадок](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
#### <a name="to-clean-up-after-the-sample"></a>Очистка после образца  
  
-   После завершения работы примера запустите в папке примеров файл Cleanup.bat.  
  
    > [!NOTE]
    >  Этот скрипт не удаляет сертификаты службы на клиенте при выполнении примера на нескольких компьютерах. При запуске образцов Windows Communication Foundation (WCF), использующих сертификаты на нескольких компьютерах, обязательно удалите сертификаты службы, которые были установлены в хранилище CurrentUser - trustedpeople. Для этого используйте следующую команду: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`. Например, `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Metadata\CustomMexEndpoint`  
  
## <a name="see-also"></a>См. также
