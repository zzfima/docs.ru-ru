---
title: Пример безопасности сообщений
ms.date: 03/30/2017
ms.assetid: 82444166-6288-493a-85d4-85f43f134d19
ms.openlocfilehash: df23bf79f105cd17177cc4f67e4574dcedf20656
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714850"
---
# <a name="message-security-sample"></a><span data-ttu-id="9af2b-102">Пример безопасности сообщений</span><span class="sxs-lookup"><span data-stu-id="9af2b-102">Message Security Sample</span></span>
<span data-ttu-id="9af2b-103">Данный образец демонстрирует реализацию приложения, в котором используется привязка `basicHttpBinding` и безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="9af2b-103">This sample demonstrates how to implement an application that uses the `basicHttpBinding` and message security.</span></span> <span data-ttu-id="9af2b-104">Этот образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) , который реализует службу калькулятора.</span><span class="sxs-lookup"><span data-stu-id="9af2b-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9af2b-105">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="9af2b-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="9af2b-106">Режим безопасности `basicHttpBinding` может быть установлен в следующие значения: `Message`, `Transport`, `TransportWithMessageCredential`, `TransportCredentialOnly` и `None`.</span><span class="sxs-lookup"><span data-stu-id="9af2b-106">The security mode of `basicHttpBinding` can be set to the following values: `Message`, `Transport`, `TransportWithMessageCredential`, `TransportCredentialOnly` and `None`.</span></span> <span data-ttu-id="9af2b-107">В следующем образце файла службы App.config, в определении конечной точки задаются привязка `basicHttpBinding` и ссылки на конфигурацию привязки с именем `Binding1`, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9af2b-107">In the following sample service App.config file, the endpoint definition specifies the `basicHttpBinding` and references a binding configuration named `Binding1`, as shown in the following sample configuration:</span></span>  
  
```xml  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
             behaviorConfiguration="CalculatorServiceBehavior">  
     <!-- This endpoint is exposed at the base address provided by -->  
     <!-- host: http://localhost:8000/ServiceModelSamples/service.-->  
     <endpoint address=""  
               binding="basicHttpBinding"  
               bindingConfiguration="Binding1"   
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
  </services>  
  ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="9af2b-108">Конфигурация привязки задает атрибуту `mode` [> безопасности\<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) `Message` и устанавливает атрибут `clientCredentialType`\<ного [сообщения](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md) в >, как показано в следующем образце конфигурации:</span><span class="sxs-lookup"><span data-stu-id="9af2b-108">The binding configuration sets the `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message` and sets the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-basichttpbinding.md) to `Certificate` as shown in the following sample configuration:</span></span>  
  
```xml  
<bindings>  
  <basicHttpBinding>  
    <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
    <binding name="Binding1" >  
      <security mode = "Message">  
        <message clientCredentialType="Certificate"/>  
      </security>  
    </binding>  
  </basicHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="9af2b-109">Сертификат, используемый службой для проверки своей подлинности при подключении к клиенту, установлен в разделе поведений элемента `serviceCredentials` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9af2b-109">The certificate that the service uses to authenticate itself to the client is set in the behaviors section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="9af2b-110">Режим проверки, применяемый к сертификату, который клиент использует для проверки своей подлинности при подключении к службе, также задается в разделе поведений элемента `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="9af2b-110">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the behaviors section under the `clientCertificate` element.</span></span>  
  
```xml  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
      <!--The serviceCredentials behavior allows one to define a -->  
      <!--service certificate. A service certificate is used by a -->  
      <!--client to authenticate the service and provide message -->  
      <!-- protection. This configuration references the "localhost"-->  
      <!--certificate installed during the setup instructions. -->  
      <serviceCredentials>  
        <serviceCertificate findValue="localhost"  
               storeLocation="LocalMachine"   
               storeName="My" x509FindType="FindBySubjectName" />  
        <clientCertificate>  
          <!-- Setting the certificateValidationMode to -->  
          <!-- PeerOrChainTrust means that if the certificate -->  
          <!--is in the user's Trusted People store, then it is -->  
          <!-- trusted without performing a validation of the -->  
          <!-- certificate's issuer chain. This setting is used -->  
          <!-- here for convenience so that the sample can be run -->  
          <!-- without having to have certificates issued by a -->  
          <!-- certification authority (CA). -->  
          <!-- This setting is less secure than the default, -->  
          <!-- ChainTrust. The security implications of this -->  
          <!-- setting should be carefully considered before using -->  
          <!-- PeerOrChainTrust in production code. -->  
          <authentication   
                       certificateValidationMode="PeerOrChainTrust" />  
        </clientCertificate>  
      </serviceCredentials>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="9af2b-111">Та же привязка и данные безопасности задаются в файле конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="9af2b-111">The same binding and security details are specified in the client configuration file.</span></span>  
  
 <span data-ttu-id="9af2b-112">Идентификация абонента отображается в окне консоли службы с помощью следующего кода.</span><span class="sxs-lookup"><span data-stu-id="9af2b-112">The identity of the caller is displayed in the service console window by using the following code:</span></span>  

```csharp
Console.WriteLine("Called by {0}", ServiceSecurityContext.Current.PrimaryIdentity.Name);  
```

 <span data-ttu-id="9af2b-113">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="9af2b-113">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="9af2b-114">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="9af2b-114">Press ENTER in the client window to shut down the client.</span></span>  
  
```console
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="9af2b-115">Настройка и сборка образца</span><span class="sxs-lookup"><span data-stu-id="9af2b-115">To set up and build the sample</span></span>  
  
1. <span data-ttu-id="9af2b-116">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9af2b-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="9af2b-117">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9af2b-117">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="9af2b-118">Запуск образца на том же компьютере</span><span class="sxs-lookup"><span data-stu-id="9af2b-118">To run the sample on the same machine</span></span>  
  
1. <span data-ttu-id="9af2b-119">Запустите файл Setup.bat из папки установки примера.</span><span class="sxs-lookup"><span data-stu-id="9af2b-119">Run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="9af2b-120">При этом устанавливаются все сертификаты, необходимые для выполнения образца.</span><span class="sxs-lookup"><span data-stu-id="9af2b-120">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9af2b-121">Пакетный файл Setup.bat предназначен для запуска из командной строки Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="9af2b-121">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="9af2b-122">Требуется, чтобы переменная среды MSSDK указывала на каталог, в котором установлен пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="9af2b-122">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="9af2b-123">Эта переменная среды автоматически устанавливается в командной строке Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="9af2b-123">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span>  
  
2. <span data-ttu-id="9af2b-124">Запустите приложение службы из \service\bin.</span><span class="sxs-lookup"><span data-stu-id="9af2b-124">Run the service application from \service\bin.</span></span>  
  
3. <span data-ttu-id="9af2b-125">Запустите клиентское приложение из \service\bin.</span><span class="sxs-lookup"><span data-stu-id="9af2b-125">Run the client application from \client\bin.</span></span> <span data-ttu-id="9af2b-126">Действия клиента отображаются в консольном приложении клиента.</span><span class="sxs-lookup"><span data-stu-id="9af2b-126">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="9af2b-127">Если клиент и служба не могут обмениваться данными, см. раздел [Советы по устранению неполадок для примеров WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="9af2b-127">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
5. <span data-ttu-id="9af2b-128">После завершения работы образца запустите файл Cleanup.bat, чтобы удалить сертификаты.</span><span class="sxs-lookup"><span data-stu-id="9af2b-128">Remove the certificates by running Cleanup.bat when you have finished with the sample.</span></span> <span data-ttu-id="9af2b-129">В других образцах обеспечения безопасности используются те же сертификаты.</span><span class="sxs-lookup"><span data-stu-id="9af2b-129">Other security samples use the same certificates.</span></span>  
  
### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="9af2b-130">Выполнение примера на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="9af2b-130">To run the sample across machines</span></span>  
  
1. <span data-ttu-id="9af2b-131">Создайте на компьютере службы каталог для двоичных файлов службы.</span><span class="sxs-lookup"><span data-stu-id="9af2b-131">Create a directory on the service machine for the service binaries.</span></span>  
  
2. <span data-ttu-id="9af2b-132">Скопируйте файлы программ службы из каталога службы на сервер.</span><span class="sxs-lookup"><span data-stu-id="9af2b-132">Copy the service program files to the service directory on the server.</span></span> <span data-ttu-id="9af2b-133">Также скопируйте на сервер файлы Setup.bat, Cleanup.bat и ImportClientCert.bat.</span><span class="sxs-lookup"><span data-stu-id="9af2b-133">Also copy the Setup.bat, Cleanup.bat, and ImportClientCert.bat files to the server.</span></span>  
  
3. <span data-ttu-id="9af2b-134">Создайте на клиентском компьютере каталог для двоичных файлов клиента.</span><span class="sxs-lookup"><span data-stu-id="9af2b-134">Create a directory on the client machine for the client binaries.</span></span>  
  
4. <span data-ttu-id="9af2b-135">Скопируйте в клиентский каталог на клиентском компьютере файлы программы клиента.</span><span class="sxs-lookup"><span data-stu-id="9af2b-135">Copy the client program files to the client directory on the client machine.</span></span> <span data-ttu-id="9af2b-136">Кроме того, скопируйте на клиент файлы Setup.bat, Cleanup.bat и ImportServiceCert.bat.</span><span class="sxs-lookup"><span data-stu-id="9af2b-136">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="9af2b-137">На сервере выполните команду `setup.bat service`.</span><span class="sxs-lookup"><span data-stu-id="9af2b-137">On the server, run `setup.bat service`.</span></span> <span data-ttu-id="9af2b-138">При запуске `setup.bat` с аргументом `service` создается сертификат службы с полным доменным именем компьютера и экспортируется сертификат службы в файл с именем Service. cer.</span><span class="sxs-lookup"><span data-stu-id="9af2b-138">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the machine and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="9af2b-139">Измените файл Service. exe. config в соответствии с новым именем сертификата (в атрибуте `findValue` в элементе [\<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) ), который совпадает с полным доменным именем компьютера.</span><span class="sxs-lookup"><span data-stu-id="9af2b-139">Edit Service.exe.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) element) which is the same as the fully-qualified domain name of the machine.</span></span> <span data-ttu-id="9af2b-140">Также измените значение базового адреса для указания полного доменного имени компьютера вместо localhost`.`</span><span class="sxs-lookup"><span data-stu-id="9af2b-140">Also change the value of the base address to specify a fully-qualified machine name instead of localhost`.`</span></span>  
  
7. <span data-ttu-id="9af2b-141">Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="9af2b-141">Copy the Service.cer file from the service directory to the client directory on the client machine.</span></span>  
  
8. <span data-ttu-id="9af2b-142">На клиенте выполните команду `setup.bat client`.</span><span class="sxs-lookup"><span data-stu-id="9af2b-142">On the client, run `setup.bat client`.</span></span> <span data-ttu-id="9af2b-143">При выполнении команды `setup.bat`с аргументом `client` создается сертификат клиента с именем client.com, который экспортируется в файл с именем Client.cer.</span><span class="sxs-lookup"><span data-stu-id="9af2b-143">Running `setup.bat` with the `client` argument creates a client certificate named client.com and exports the client certificate to a file named Client.cer.</span></span>  
  
9. <span data-ttu-id="9af2b-144">В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.</span><span class="sxs-lookup"><span data-stu-id="9af2b-144">In the Client.exe.config file on the client machine, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="9af2b-145">Для этого замените имя localhost полным именем домена сервера.</span><span class="sxs-lookup"><span data-stu-id="9af2b-145">You do this by replacing localhost with the fully-qualified domain name of the server.</span></span> <span data-ttu-id="9af2b-146">Также измените атрибут `findValue` [\<дефаултцертификате >](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md) на новое имя сертификата службы, которое является полным доменным именем сервера.</span><span class="sxs-lookup"><span data-stu-id="9af2b-146">Also change the `findValue` attribute of the [\<defaultCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md) to the new service certificate name which is the fully-qualified domain name of the server.</span></span>  
  
10. <span data-ttu-id="9af2b-147">Скопируйте файл Client.cer из клиентского каталога в каталог службы на сервере.</span><span class="sxs-lookup"><span data-stu-id="9af2b-147">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>  
  
11. <span data-ttu-id="9af2b-148">Запустите на клиенте файл ImportServiceCert.bat.</span><span class="sxs-lookup"><span data-stu-id="9af2b-148">On the client, run ImportServiceCert.bat.</span></span> <span data-ttu-id="9af2b-149">Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="9af2b-149">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
12. <span data-ttu-id="9af2b-150">На сервере запустите файл ImportClientCert.bat. Он импортирует сертификат клиента из файла Client.cer в хранилище LocalMachine - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="9af2b-150">On the server, run ImportClientCert.bat, This imports the client certificate from the Client.cer file into the LocalMachine - TrustedPeople store.</span></span>  
  
13. <span data-ttu-id="9af2b-151">Запустите программу Service.exe из командной строки на компьютере службы.</span><span class="sxs-lookup"><span data-stu-id="9af2b-151">On the service machine, run Service.exe from a command prompt.</span></span>  
  
14. <span data-ttu-id="9af2b-152">На клиентском компьютере из окна командной строки запустите программу Client.exe.</span><span class="sxs-lookup"><span data-stu-id="9af2b-152">On the client machine, launch Client.exe from a command prompt window.</span></span>  
  
    1. <span data-ttu-id="9af2b-153">Если клиент и служба не могут обмениваться данными, см. раздел [Советы по устранению неполадок для примеров WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="9af2b-153">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="9af2b-154">Очистка после образца</span><span class="sxs-lookup"><span data-stu-id="9af2b-154">To clean up after the sample</span></span>  
  
- <span data-ttu-id="9af2b-155">После завершения работы примера запустите в папке примеров файл Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="9af2b-155">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="9af2b-156">Этот скрипт не удаляет сертификаты службы на клиенте при выполнении примера на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="9af2b-156">This script does not remove service certificates on a client when running this sample across machines.</span></span> <span data-ttu-id="9af2b-157">Если вы выполнили примеры Windows Communication Foundation (WCF), использующие сертификаты на разных компьютерах, обязательно очистите сертификаты службы, установленные в хранилище CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="9af2b-157">If you have run Windows Communication Foundation (WCF) samples that use certificates across machines, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="9af2b-158">Для этого воспользуйтесь следующей командой: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`. Пример: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="9af2b-158">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9af2b-159">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9af2b-159">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9af2b-160">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9af2b-160">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="9af2b-161">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="9af2b-161">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9af2b-162">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="9af2b-162">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\MessageSecurity`  
