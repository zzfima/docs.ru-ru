---
title: Пользовательская конечная точка защищенных метаданных
ms.date: 03/30/2017
ms.assetid: 9e369e99-ea4a-49ff-aed2-9fdf61091a48
ms.openlocfilehash: 89f12b4490d556884aaa15dcb102b5ad876707ba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183845"
---
# <a name="custom-secure-metadata-endpoint"></a><span data-ttu-id="e14e8-102">Пользовательская конечная точка защищенных метаданных</span><span class="sxs-lookup"><span data-stu-id="e14e8-102">Custom Secure Metadata Endpoint</span></span>
<span data-ttu-id="e14e8-103">В этом примере показано, как реализовать службу с безопасной конечной точкой метаданных, использующую одну из привязок обмена метаданными, и как настроить [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) или клиентов для извлечения метаданных из такой конечной точки метаданных.</span><span class="sxs-lookup"><span data-stu-id="e14e8-103">This sample demonstrates how to implement a service with a secure metadata endpoint that uses one of the non-metadata exchange bindings, and how to configure [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) or clients to fetch the metadata from such a metadata endpoint.</span></span> <span data-ttu-id="e14e8-104">Существует две системные привязки для предоставления конечных точек метаданных: mexHttpBinding и mexHttpsBinding.</span><span class="sxs-lookup"><span data-stu-id="e14e8-104">There are two system-provided bindings available for exposing metadata endpoints: mexHttpBinding and mexHttpsBinding.</span></span> <span data-ttu-id="e14e8-105">Привязка mexHttpBinding используется для предоставления конечной точки метаданных через HTTP в незащищенном режиме.</span><span class="sxs-lookup"><span data-stu-id="e14e8-105">mexHttpBinding is used to expose a metadata endpoint over HTTP in a non-secure manner.</span></span> <span data-ttu-id="e14e8-106">Привязка mexHttpsBinding используется для предоставления конечной точки метаданных через HTTP в защищенном режиме.</span><span class="sxs-lookup"><span data-stu-id="e14e8-106">mexHttpsBinding is used to expose a metadata endpoint over HTTPS in a secure manner.</span></span> <span data-ttu-id="e14e8-107">В этом образце описывается предоставление защищенной конечной точки метаданных с использованием объекта <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="e14e8-107">This sample illustrates how to expose a secure metadata endpoint using the <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="e14e8-108">Такой подход следует использовать, если требуется изменить параметры безопасности привязки, но при этом нежелательно использовать протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e14e8-108">You would want to do this when you want to change the security settings on the binding, but you do not want to use HTTPS.</span></span> <span data-ttu-id="e14e8-109">При использовании привязки mexHttpsBinding конечная точка метаданных будет защищена, но изменение параметров привязки окажется невозможным.</span><span class="sxs-lookup"><span data-stu-id="e14e8-109">If you use the mexHttpsBinding your metadata endpoint will be secure, but there is no way to modify the binding settings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e14e8-110">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="e14e8-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="service"></a><span data-ttu-id="e14e8-111">Служба</span><span class="sxs-lookup"><span data-stu-id="e14e8-111">Service</span></span>  
 <span data-ttu-id="e14e8-112">Служба в образце имеет две конечные точки.</span><span class="sxs-lookup"><span data-stu-id="e14e8-112">The service in this sample has two endpoints.</span></span> <span data-ttu-id="e14e8-113">Конечная точка приложения служит в качестве контракта `ICalculator` для привязки `WSHttpBinding` с включенным сеансом `ReliableSession` и режимом безопасности `Message` с использованием сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e14e8-113">The application endpoint serves the `ICalculator` contract on a `WSHttpBinding` with `ReliableSession` enabled and `Message` security using certificates.</span></span> <span data-ttu-id="e14e8-114">Конечная точка метаданных также использует привязку `WSHttpBinding` с аналогичными параметрами безопасности, но без `ReliableSession`.</span><span class="sxs-lookup"><span data-stu-id="e14e8-114">The metadata endpoint also uses `WSHttpBinding`, with the same security settings but with no `ReliableSession`.</span></span> <span data-ttu-id="e14e8-115">Соответствующая конфигурация представлена ниже.</span><span class="sxs-lookup"><span data-stu-id="e14e8-115">Here is the relevant configuration:</span></span>  
  
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
  
 <span data-ttu-id="e14e8-116">Во многих других образцах конечная точка метаданных использует привязку по умолчанию `mexHttpBinding`, которая не является безопасной.</span><span class="sxs-lookup"><span data-stu-id="e14e8-116">In many of the other samples, the metadata endpoint uses the default `mexHttpBinding`, which is not secure.</span></span> <span data-ttu-id="e14e8-117">В данном примере безопасность метаданных обеспечивается с помощью привязки `WSHttpBinding` с режимом безопасности `Message`.</span><span class="sxs-lookup"><span data-stu-id="e14e8-117">Here the metadata is secured using `WSHttpBinding` with `Message` security.</span></span> <span data-ttu-id="e14e8-118">Чтобы клиенты метаданных могли извлекать эти метаданные, они должны быть настроены с соответствующей привязкой.</span><span class="sxs-lookup"><span data-stu-id="e14e8-118">In order for metadata clients to retrieve this metadata, they must be configured with a matching binding.</span></span> <span data-ttu-id="e14e8-119">В образце показаны два таких клиента.</span><span class="sxs-lookup"><span data-stu-id="e14e8-119">This sample demonstrates two such clients.</span></span>  
  
 <span data-ttu-id="e14e8-120">Первый клиент использует Svcutil.exe для извлечения метаданных, а также создания клиентского кода и конфигурации во время разработки.</span><span class="sxs-lookup"><span data-stu-id="e14e8-120">The first client uses Svcutil.exe to fetch the metadata and generate client code and configuration at design time.</span></span> <span data-ttu-id="e14e8-121">Поскольку служба использует для метаданных привязку, отличную от привязки по умолчанию, средство Svcutil.exe необходимо настроить определенным образом, чтобы оно могло получать метаданные из службы с помощью данной привязки.</span><span class="sxs-lookup"><span data-stu-id="e14e8-121">Because the service uses a non-default binding for the metadata, the Svcutil.exe tool must be specifically configured so that it can get the metadata from the service using that binding.</span></span>  
  
 <span data-ttu-id="e14e8-122">Второй клиент использует распознаватель `MetadataResolver` с целью динамического извлечения метаданных для известного контракта с последующим вызовом операций на динамически создаваемом клиенте.</span><span class="sxs-lookup"><span data-stu-id="e14e8-122">The second client uses the `MetadataResolver` to dynamically fetch the metadata for a known contract and then invoke operations on the dynamically generated client.</span></span>  
  
## <a name="svcutil-client"></a><span data-ttu-id="e14e8-123">Клиент Svcutil</span><span class="sxs-lookup"><span data-stu-id="e14e8-123">Svcutil client</span></span>  
 <span data-ttu-id="e14e8-124">При использовании привязки по умолчанию для размещения конечной точки `IMetadataExchange` можно запустить Svcutil.exe с указанием адреса этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e14e8-124">When using the default binding to host your `IMetadataExchange` endpoint, you can run Svcutil.exe with the address of that endpoint:</span></span>  
  
```console  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="e14e8-125">И это будет работать.</span><span class="sxs-lookup"><span data-stu-id="e14e8-125">and it works.</span></span> <span data-ttu-id="e14e8-126">Однако в этом образце для размещения метаданных сервер использует привязку, отличную от привязки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e14e8-126">But in this sample, the server uses a non-default endpoint to host the metadata.</span></span> <span data-ttu-id="e14e8-127">Поэтому средство Svcutil.exe необходимо настроить на использование правильной привязки.</span><span class="sxs-lookup"><span data-stu-id="e14e8-127">So Svcutil.exe must be instructed to use the correct binding.</span></span> <span data-ttu-id="e14e8-128">Это можно сделать с помощью файла Svcutil.exe.config.</span><span class="sxs-lookup"><span data-stu-id="e14e8-128">This can be done using a Svcutil.exe.config file.</span></span>  
  
 <span data-ttu-id="e14e8-129">Файл Svcutil.exe.config выглядит как обычный файл конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="e14e8-129">The Svcutil.exe.config file looks like a normal client configuration file.</span></span> <span data-ttu-id="e14e8-130">Единственными необычными аспектами являются имя и контракт конечной точки клиента:</span><span class="sxs-lookup"><span data-stu-id="e14e8-130">The only unusual aspects are the client endpoint name and contract:</span></span>  
  
```xml  
<endpoint name="http"  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"  
          behaviorConfiguration="ClientCertificateBehavior"  
          contract="IMetadataExchange" />  
```  
  
 <span data-ttu-id="e14e8-131">Имя конечной точки должно совпадать с именем схемы адреса, по которому размещаются метаданные, а контрактом конечной точки должен быть `IMetadataExchange`.</span><span class="sxs-lookup"><span data-stu-id="e14e8-131">The endpoint name must be the name of the scheme of the address where the metadata is hosted and the endpoint contract must be `IMetadataExchange`.</span></span> <span data-ttu-id="e14e8-132">Таким образом, при запуске команды</span><span class="sxs-lookup"><span data-stu-id="e14e8-132">Thus, when Svcutil.exe is run with a command-line such as the following:</span></span>  
  
```console  
svcutil http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="e14e8-133">выполняется поиск конечной точки с именем "http" и контракта `IMetadataExchange` для настройки привязки и поведения при взаимодействии с конечной точкой метаданных.</span><span class="sxs-lookup"><span data-stu-id="e14e8-133">it looks for the endpoint named "http" and contract `IMetadataExchange` to configure the binding and behavior of the communication exchange with the metadata endpoint.</span></span> <span data-ttu-id="e14e8-134">В остальной части файла Svcutil.exe.config в образце определяются конфигурация привязки и учетные данные поведения для соответствия конфигурации сервера конечной точки метаданных.</span><span class="sxs-lookup"><span data-stu-id="e14e8-134">The rest of the Svcutil.exe.config file in the sample specifies the binding configuration and behavior credentials to match the server's configuration of the metadata endpoint.</span></span>  
  
 <span data-ttu-id="e14e8-135">Чтобы средство Svcutil.exe могло использовать конфигурацию, заданную в файле Svcutil.exe.config, файл Svcutil.exe должен находиться в одном каталоге с файлом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e14e8-135">In order for Svcutil.exe to pick up the configuration in Svcutil.exe.config, Svcutil.exe must be in the same directory as the configuration file.</span></span> <span data-ttu-id="e14e8-136">Таким образом, необходимо скопировать файл Svcutil.exe из расположения установки в каталог, содержащий файл Svcutil.exe.config.</span><span class="sxs-lookup"><span data-stu-id="e14e8-136">As a result, you must copy Svcutil.exe from its install location to the directory that contains the Svcutil.exe.config file.</span></span> <span data-ttu-id="e14e8-137">Затем из этого каталога необходимо выполнить следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e14e8-137">Then from that directory, run the following command:</span></span>  
  
```console  
.\svcutil.exe http://localhost/servicemodelsamples/service.svc/mex  
```  
  
 <span data-ttu-id="e14e8-138">Ведущий ". \\" гарантирует, что копия Svcutil.exe в этом каталоге (тот, который имеет соответствующий Svcutil.exe.config) будет запущен.</span><span class="sxs-lookup"><span data-stu-id="e14e8-138">The leading ".\\" ensures that the copy of Svcutil.exe in this directory (the one which has a corresponding Svcutil.exe.config) is run.</span></span>  
  
## <a name="metadataresolver-client"></a><span data-ttu-id="e14e8-139">Клиент MetadataResolver</span><span class="sxs-lookup"><span data-stu-id="e14e8-139">MetadataResolver client</span></span>  
 <span data-ttu-id="e14e8-140">Если клиенту известен контракт и способ обращения к метаданным во время разработки, клиент может динамически определять привязку и адрес конечных точек приложения с помощью распознавателя `MetadataResolver`.</span><span class="sxs-lookup"><span data-stu-id="e14e8-140">If the client knows the contract and how to talk to the metadata at design time, the client can dynamically find out the binding and address of application endpoints using the `MetadataResolver`.</span></span> <span data-ttu-id="e14e8-141">Это демонстрируется в данном образце клиента: показано, как настроить привязку и учетные данные, используемые распознавателем `MetadataResolver`, путем создания и настройки клиента `MetadataExchangeClient`.</span><span class="sxs-lookup"><span data-stu-id="e14e8-141">This sample client demonstrates this, showing how to configure the binding and credentials used by `MetadataResolver` by creating and configuring a `MetadataExchangeClient`.</span></span>  
  
 <span data-ttu-id="e14e8-142">Информацию о привязке и сертификате, указанную в файле Svcutil.exe.config, можно задать императивно в клиенте `MetadataExchangeClient`:</span><span class="sxs-lookup"><span data-stu-id="e14e8-142">The same binding and certificate information that appeared in Svcutil.exe.config can be specified imperatively on the `MetadataExchangeClient`:</span></span>  
  
```csharp  
// Specify the Metadata Exchange binding and its security mode  
WSHttpBinding mexBinding = new WSHttpBinding(SecurityMode.Message);  
mexBinding.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
// Create a MetadataExchangeClient for retrieving metadata, and set the // certificate details  
MetadataExchangeClient mexClient = new MetadataExchangeClient(mexBinding);  
mexClient.SoapCredentials.ClientCertificate.SetCertificate(    StoreLocation.CurrentUser, StoreName.My,  
    X509FindType.FindBySubjectName, "client.com");  
mexClient.SoapCredentials.ServiceCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;  
mexClient.SoapCredentials.ServiceCertificate.SetDefaultCertificate(    StoreLocation.CurrentUser, StoreName.TrustedPeople,  
    X509FindType.FindBySubjectName, "localhost");  
```  
  
 <span data-ttu-id="e14e8-143">При настроенном клиенте `mexClient` можно перечислить требуемые контракты и использовать распознаватель `MetadataResolver` для получения списка конечных точек с этими контрактами.</span><span class="sxs-lookup"><span data-stu-id="e14e8-143">With the `mexClient` configured, we can enumerate the contracts we are interested in, and use `MetadataResolver` to fetch a list of endpoints with those contracts:</span></span>  
  
```csharp  
// The contract we want to fetch metadata for  
Collection<ContractDescription> contracts = new Collection<ContractDescription>();  
ContractDescription contract = ContractDescription.GetContract(typeof(ICalculator));  
contracts.Add(contract);  
// Find endpoints for that contract  
EndpointAddress mexAddress = new EndpointAddress(ConfigurationManager.AppSettings["mexAddress"]);  
ServiceEndpointCollection endpoints = MetadataResolver.Resolve(contracts, mexAddress, mexClient);  
```  
  
 <span data-ttu-id="e14e8-144">Наконец, можно использовать информацию из этих конечных точек для инициализации привязки и адреса фабрики `ChannelFactory`, используемой для создания каналов взаимодействия с конечными точками приложения.</span><span class="sxs-lookup"><span data-stu-id="e14e8-144">Finally we can use the information from those endpoints to initialize the binding and address of a `ChannelFactory` used to create channels to communicate with the application endpoints.</span></span>  
  
```csharp  
ChannelFactory<ICalculator> cf = new ChannelFactory<ICalculator>(endpoint.Binding, endpoint.Address);  
```  
  
 <span data-ttu-id="e14e8-145">Основная задача данного образца клиента - показать, что при использовании распознавателя `MetadataResolver` и необходимости задания пользовательских привязок или поведений для обмена метаданными можно использовать клиент `MetadataExchangeClient` для задания этих пользовательских параметров.</span><span class="sxs-lookup"><span data-stu-id="e14e8-145">The key point of this sample client is to demonstrate that, if you are using `MetadataResolver`, and you must specify custom bindings or behaviors for the metadata exchange communication, you can use a `MetadataExchangeClient` to specify those custom settings.</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="e14e8-146">Настройка и сборка образца</span><span class="sxs-lookup"><span data-stu-id="e14e8-146">To set up and build the sample</span></span>  
  
1. <span data-ttu-id="e14e8-147">Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)</span><span class="sxs-lookup"><span data-stu-id="e14e8-147">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="e14e8-148">Чтобы создать решение, следуйте инструкциям по [созданию образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/building-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="e14e8-148">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="e14e8-149">Запуск образца на том же компьютере</span><span class="sxs-lookup"><span data-stu-id="e14e8-149">To run the sample on the same machine</span></span>  
  
1. <span data-ttu-id="e14e8-150">Запустите файл Setup.bat из папки установки примера.</span><span class="sxs-lookup"><span data-stu-id="e14e8-150">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="e14e8-151">При этом устанавливаются все сертификаты, необходимые для выполнения образца.</span><span class="sxs-lookup"><span data-stu-id="e14e8-151">This installs all the certificates required for running the sample.</span></span> <span data-ttu-id="e14e8-152">Обратите внимание, что Setup.bat использует инструмент FindPrivateKey.exe, который устанавливается при запуске setupCertTool.bat из [одноразовой настройки процедуры для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)</span><span class="sxs-lookup"><span data-stu-id="e14e8-152">Note that Setup.bat uses the FindPrivateKey.exe tool, which is installed by running setupCertTool.bat from [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="e14e8-153">Запустите клиентское приложение из каталога \MetadataResolverClient\bin или \SvcutilClient\bin.</span><span class="sxs-lookup"><span data-stu-id="e14e8-153">Run the client application from \MetadataResolverClient\bin or \SvcutilClient\bin.</span></span> <span data-ttu-id="e14e8-154">Действия клиента отображаются в консольном приложении клиента.</span><span class="sxs-lookup"><span data-stu-id="e14e8-154">Client activity is displayed on the client console application.</span></span>  
  
3. <span data-ttu-id="e14e8-155">Если клиент и служба не в состоянии общаться, [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e14e8-155">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
4. <span data-ttu-id="e14e8-156">После завершения работы образца запустите файл Cleanup.bat, чтобы удалить сертификаты.</span><span class="sxs-lookup"><span data-stu-id="e14e8-156">Remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="e14e8-157">В других образцах обеспечения безопасности используются те же сертификаты.</span><span class="sxs-lookup"><span data-stu-id="e14e8-157">Other security samples use the same certificates.</span></span>  
  
#### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="e14e8-158">Выполнение примера на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="e14e8-158">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="e14e8-159">На сервере выполните команду `setup.bat service`.</span><span class="sxs-lookup"><span data-stu-id="e14e8-159">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="e14e8-160">Запуск `setup.bat` с `service` аргументом создает сертификат обслуживания с полностью квалифицированным доменным именем машины и экспортирует сертификат обслуживания в файл под названием Service.cer.</span><span class="sxs-lookup"><span data-stu-id="e14e8-160">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the machine and exports the service certificate to a file named Service.cer.</span></span>  
  
2. <span data-ttu-id="e14e8-161">Измените Web.config на сервере так, чтобы в файле отражалось новое имя сертификата.</span><span class="sxs-lookup"><span data-stu-id="e14e8-161">On the server, edit Web.config to reflect the new certificate name.</span></span> <span data-ttu-id="e14e8-162">То есть изменить `findValue` атрибут в [ \<сервисеСертификат>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) элемент на полностью квалифицированное доменное имя машины.</span><span class="sxs-lookup"><span data-stu-id="e14e8-162">That is, change the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) element to the fully-qualified domain name of the machine.</span></span>  
  
3. <span data-ttu-id="e14e8-163">Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="e14e8-163">Copy the Service.cer file from the service directory to the client directory on the client machine.</span></span>  
  
4. <span data-ttu-id="e14e8-164">На клиенте выполните команду `setup.bat client`.</span><span class="sxs-lookup"><span data-stu-id="e14e8-164">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="e14e8-165">Запуск `setup.bat` с `client` аргументом создает сертификат клиента под названием Client.com и экспортирует сертификат клиента в файл под названием Client.cer.</span><span class="sxs-lookup"><span data-stu-id="e14e8-165">Running `setup.bat` with the `client` argument creates a client certificate named Client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
5. <span data-ttu-id="e14e8-166">В файле App.config клиента `MetadataResolverClient` на клиентском компьютере измените значение адреса конечной точки обмена метаданными, чтобы оно соответствовало новому адресу службы.</span><span class="sxs-lookup"><span data-stu-id="e14e8-166">In the App.config file of the `MetadataResolverClient` on the client machine, change the address value of the mex endpoint to match the new address of your service.</span></span> <span data-ttu-id="e14e8-167">Для этого замените имя localhost полным именем домена сервера.</span><span class="sxs-lookup"><span data-stu-id="e14e8-167">You do this by replacing localhost with the fully-qualified domain name of the server.</span></span> <span data-ttu-id="e14e8-168">Кроме того, замените вхождение "localhost" в файле metadataResolverClient.cs новым именем сертификата службы (полным доменным именем сервера).</span><span class="sxs-lookup"><span data-stu-id="e14e8-168">Also change the occurrence of "localhost" in the metadataResolverClient.cs file to the new service certificate name (the fully-qualified domain name of the server).</span></span> <span data-ttu-id="e14e8-169">Выполните то же самое для файла App.config проекта SvcutilClient.</span><span class="sxs-lookup"><span data-stu-id="e14e8-169">Do the same thing for the App.config of the SvcutilClient project.</span></span>  
  
6. <span data-ttu-id="e14e8-170">Скопируйте файл Client.cer из клиентского каталога в каталог службы на сервере.</span><span class="sxs-lookup"><span data-stu-id="e14e8-170">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
7. <span data-ttu-id="e14e8-171">На клиенте выполните команду `ImportServiceCert.bat`.</span><span class="sxs-lookup"><span data-stu-id="e14e8-171">On the client, run `ImportServiceCert.bat`.</span></span> <span data-ttu-id="e14e8-172">Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="e14e8-172">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
8. <span data-ttu-id="e14e8-173">На сервере запустите файл `ImportClientCert.bat`. Он импортирует сертификат клиента из файла Client.cer в хранилище LocalMachine - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="e14e8-173">On the server, run `ImportClientCert.bat`, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
9. <span data-ttu-id="e14e8-174">На компьютере службы выполните построение проекта службы в Visual Studio и выберите страницу справки в веб-браузере, чтобы проверить что она запущена.</span><span class="sxs-lookup"><span data-stu-id="e14e8-174">On the service machine, build the service project in Visual Studio and select the help page in a web browser to verify that it is running.</span></span>  
  
10. <span data-ttu-id="e14e8-175">На клиентском компьютере запустите клиент MetadataResolverClient или SvcutilClient из VS.</span><span class="sxs-lookup"><span data-stu-id="e14e8-175">On the client machine, run the MetadataResolverClient or the SvcutilClient from VS.</span></span>  
  
    1. <span data-ttu-id="e14e8-176">Если клиент и служба не в состоянии общаться, [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e14e8-176">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="e14e8-177">Очистка после образца</span><span class="sxs-lookup"><span data-stu-id="e14e8-177">To clean up after the sample</span></span>  
  
- <span data-ttu-id="e14e8-178">После завершения работы примера запустите в папке примеров файл Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="e14e8-178">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e14e8-179">Этот скрипт не удаляет сертификаты службы на клиенте при выполнении примера на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="e14e8-179">This script does not remove service certificates on a client when running this sample across machines.</span></span> <span data-ttu-id="e14e8-180">Если вы используете образцы Windows Communication Foundation (WCF), которые используют сертификаты в разных машинах, обязательно очистите сертификаты обслуживания, установленные в магазине CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="e14e8-180">If you have run Windows Communication Foundation (WCF) samples that use certificates across machines, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="e14e8-181">Для этого используйте следующую команду: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`.</span><span class="sxs-lookup"><span data-stu-id="e14e8-181">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`.</span></span> <span data-ttu-id="e14e8-182">Например: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="e14e8-182">For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e14e8-183">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e14e8-183">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e14e8-184">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e14e8-184">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="e14e8-185">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="e14e8-185">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e14e8-186">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="e14e8-186">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Metadata\CustomMexEndpoint`  
