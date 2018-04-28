---
title: Транспорт WS с учетными данными сообщения
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7b954e2d19f601476876beef6482ca10eb3f113b
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="ws-transport-with-message-credential"></a><span data-ttu-id="a510c-102">Транспорт WS с учетными данными сообщения</span><span class="sxs-lookup"><span data-stu-id="a510c-102">WS Transport With Message Credential</span></span>
<span data-ttu-id="a510c-103">В этом примере показано использовании безопасности транспорта SSL в сочетании с передаваемыми в сообщении учетными данными клиента.</span><span class="sxs-lookup"><span data-stu-id="a510c-103">This sample demonstrates the use of SSL transport security in combination with client credential being carried in the message.</span></span> <span data-ttu-id="a510c-104">В этом примере используется привязка `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="a510c-104">This sample uses the `wsHttpBinding` binding.</span></span>  
  
 <span data-ttu-id="a510c-105">По умолчанию привязка `wsHttpBinding` обеспечивает взаимодействие по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="a510c-105">By default, the `wsHttpBinding` binding provides HTTP communication.</span></span> <span data-ttu-id="a510c-106">При настройке для безопасности транспорта привязка поддерживает взаимодействие по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a510c-106">When configured for transport security, the binding supports HTTPS communication.</span></span> <span data-ttu-id="a510c-107">Протокол HTTPS обеспечивает конфиденциальность и защиту целостности передаваемых по каналам связи сообщений.</span><span class="sxs-lookup"><span data-stu-id="a510c-107">HTTPS provides confidentiality and integrity protection for the messages that are transmitted over the wire.</span></span> <span data-ttu-id="a510c-108">Тем не менее набор механизмов аутентификации, который можно использовать для проверки подлинности клиента при соединении со службой, ограничен механизмами, поддерживаемыми транспортом HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a510c-108">However the set of authentication mechanisms that can be used to authenticate the client to the service is limited to what the HTTPS transport supports.</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="a510c-109"> предлагает `TransportWithMessageCredential` режим безопасности, который позволяет обойти это ограничение.</span><span class="sxs-lookup"><span data-stu-id="a510c-109"> offers a `TransportWithMessageCredential` security mode that is designed to overcome this limitation.</span></span> <span data-ttu-id="a510c-110">Если включен этот режим безопасности, для обеспечения конфиденциальности и целостности передаваемых сообщений, а также для проверки подлинности службы, используется безопасность транспорта.</span><span class="sxs-lookup"><span data-stu-id="a510c-110">When this security mode is configured, the transport security is used to provide confidentiality and integrity for the transmitted messages and to perform the service authentication.</span></span> <span data-ttu-id="a510c-111">Тем не менее проверка подлинности клиента выполняется путем помещения учетных данных клиента непосредственно в сообщении.</span><span class="sxs-lookup"><span data-stu-id="a510c-111">However, the client authentication is performed by putting the client credential directly in the message.</span></span> <span data-ttu-id="a510c-112">Это позволяет использовать любой тип учетных данных, поддерживаемый режим безопасности сообщений для проверки подлинности клиента, сохраняя выигрыш в производительности режим безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="a510c-112">This allows you to use any credential type that is supported by the message security mode for the client authentication while keeping the performance benefit of transport security mode.</span></span>  
  
 <span data-ttu-id="a510c-113">В этом примере для проверки подлинности клиента на стороне службы используется тип учетных данных `UserName`.</span><span class="sxs-lookup"><span data-stu-id="a510c-113">In this sample, a `UserName` credential type is used to authenticate the client to the service.</span></span>  
  
 <span data-ttu-id="a510c-114">Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) , реализующий службу калькулятора.</span><span class="sxs-lookup"><span data-stu-id="a510c-114">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="a510c-115">В файлах конфигурации клиента и службы задана и настроена привязка `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="a510c-115">The `wsHttpBinding` binding is specified and configured in the application configuration files for the client and service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a510c-116">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="a510c-116">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="a510c-117">В образце кода программы почти идентична [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) службы.</span><span class="sxs-lookup"><span data-stu-id="a510c-117">The program code in the sample is almost identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="a510c-118">Имеется одна дополнительная операция, предоставляемая контрактом службы - `GetCallerIdentity`.</span><span class="sxs-lookup"><span data-stu-id="a510c-118">There is one additional operation provided by the service contract - `GetCallerIdentity`.</span></span> <span data-ttu-id="a510c-119">Операция возвращает вызывающей стороне имя удостоверения вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="a510c-119">This operation returns the name of the caller's identity to the caller.</span></span>  

```csharp
public string GetCallerIdentity()  
{  
    // Use ServiceSecurityContext.WindowsIdentity to get the name of the caller.  
    return ServiceSecurityContext.Current.WindowsIdentity.Name;  
}  
```

 <span data-ttu-id="a510c-120">Перед построением и запуском примера необходимо с помощью мастера сертификатов веб-сервера создать и назначить сертификат.</span><span class="sxs-lookup"><span data-stu-id="a510c-120">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="a510c-121">Определения конечной точки и привязки в файле конфигурации устанавливают режим безопасности `TransportWithMessageCredential`, как показано в следующем примере файла конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="a510c-121">The endpoint definition and binding definition in the configuration file settings enable `TransportWithMessageCredential` security mode, as shown in the following sample configuration for the client.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
              address="https://localhost/servicemodelsamples/service.svc"   
              binding="wsHttpBinding"   
              bindingConfiguration="Binding1"   
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
        This configuration defines the security mode as TransportWithMessageCredential.  
        and the clientCredentialType as UserName.  
        -->  
      <binding name="Binding1">  
        <security mode ="TransportWithMessageCredential">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="a510c-122">Заданный адрес использует схему https://.</span><span class="sxs-lookup"><span data-stu-id="a510c-122">The address specified uses the https:// scheme.</span></span> <span data-ttu-id="a510c-123">Конфигурация привязки задает режим безопасности `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="a510c-123">The binding configuration sets the security mode to `TransportWithMessageCredential`.</span></span> <span data-ttu-id="a510c-124">Тот же режим безопасности необходимо задать в файле Web.config службы.</span><span class="sxs-lookup"><span data-stu-id="a510c-124">The same security mode must be specified in the service's Web.config file.</span></span>  
  
 <span data-ttu-id="a510c-125">Так как сертификат, используемый в этом примере является тестовым сертификатом, созданным Makecert.exe, появляется предупреждение системы безопасности появляется при попытке получить доступ к https: адреса, такие как https://localhost/servicemodelsamples/service.svc, из браузера.</span><span class="sxs-lookup"><span data-stu-id="a510c-125">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as https://localhost/servicemodelsamples/service.svc, from your browser.</span></span> <span data-ttu-id="a510c-126">Чтобы клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] мог работать с используемым тестовым сертификатом, в клиент был добавлен дополнительный код, подавляющий появление предупреждения системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="a510c-126">To allow the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="a510c-127">При использовании рабочих сертификатов этот код и соответствующие классы не требуются.</span><span class="sxs-lookup"><span data-stu-id="a510c-127">This code, and the accompanying class, is not required when using production certificates.</span></span>  

```csharp
// WARNING: This code is only needed for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```
  
 <span data-ttu-id="a510c-128">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="a510c-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="a510c-129">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="a510c-129">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Username authentication required.  
Provide a valid machine or domain account. [domain\\user]  
   Enter username:   
YourDomainName\YourAccountName  
   Enter password:   
********  
YourDomainName\YourAccountName  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a510c-130">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="a510c-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a510c-131">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a510c-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="a510c-132">Убедитесь, что вы выполнили [инструкции по установке сертификата сервера Internet Information Services (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="a510c-132">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
3.  <span data-ttu-id="a510c-133">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a510c-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="a510c-134">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a510c-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a510c-135">См. также</span><span class="sxs-lookup"><span data-stu-id="a510c-135">See Also</span></span>
