---
title: Транспорт WS с учетными данными сообщения
ms.date: 03/30/2017
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
ms.openlocfilehash: cc452ade4ef7d0d2d197f058d74ca0c3d0e0230d
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423077"
---
# <a name="ws-transport-with-message-credential"></a><span data-ttu-id="ecbd1-102">Транспорт WS с учетными данными сообщения</span><span class="sxs-lookup"><span data-stu-id="ecbd1-102">WS Transport With Message Credential</span></span>
<span data-ttu-id="ecbd1-103">В этом примере показано использовании безопасности транспорта SSL в сочетании с передаваемыми в сообщении учетными данными клиента.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-103">This sample demonstrates the use of SSL transport security in combination with client credential being carried in the message.</span></span> <span data-ttu-id="ecbd1-104">В этом примере используется привязка `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-104">This sample uses the `wsHttpBinding` binding.</span></span>  
  
 <span data-ttu-id="ecbd1-105">По умолчанию привязка `wsHttpBinding` обеспечивает взаимодействие по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-105">By default, the `wsHttpBinding` binding provides HTTP communication.</span></span> <span data-ttu-id="ecbd1-106">При настройке для безопасности транспорта привязка поддерживает взаимодействие по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-106">When configured for transport security, the binding supports HTTPS communication.</span></span> <span data-ttu-id="ecbd1-107">Протокол HTTPS обеспечивает конфиденциальность и защиту целостности передаваемых по каналам связи сообщений.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-107">HTTPS provides confidentiality and integrity protection for the messages that are transmitted over the wire.</span></span> <span data-ttu-id="ecbd1-108">Тем не менее набор механизмов аутентификации, который можно использовать для проверки подлинности клиента при соединении со службой, ограничен механизмами, поддерживаемыми транспортом HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-108">However the set of authentication mechanisms that can be used to authenticate the client to the service is limited to what the HTTPS transport supports.</span></span> <span data-ttu-id="ecbd1-109">Windows Communication Foundation (WCF) предлагает режим безопасности `TransportWithMessageCredential`, предназначенный для преодоления этого ограничения.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-109">Windows Communication Foundation (WCF) offers a `TransportWithMessageCredential` security mode that is designed to overcome this limitation.</span></span> <span data-ttu-id="ecbd1-110">Если включен этот режим безопасности, для обеспечения конфиденциальности и целостности передаваемых сообщений, а также для проверки подлинности службы, используется безопасность транспорта.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-110">When this security mode is configured, the transport security is used to provide confidentiality and integrity for the transmitted messages and to perform the service authentication.</span></span> <span data-ttu-id="ecbd1-111">Однако проверка подлинности клиента выполняется путем помещения учетных данных клиента непосредственно в сообщение.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-111">However, the client authentication is performed by putting the client credential directly in the message.</span></span> <span data-ttu-id="ecbd1-112">Это позволяет использовать любой тип учетных данных, поддерживаемый режимом безопасности сообщений для проверки подлинности клиента, сохраняя при этом преимущества производительности в режиме безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-112">This allows you to use any credential type that is supported by the message security mode for the client authentication while keeping the performance benefit of transport security mode.</span></span>  
  
 <span data-ttu-id="ecbd1-113">В этом примере для проверки подлинности клиента на стороне службы используется тип учетных данных `UserName`.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-113">In this sample, a `UserName` credential type is used to authenticate the client to the service.</span></span>  
  
 <span data-ttu-id="ecbd1-114">Этот образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) , который реализует службу калькулятора.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-114">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="ecbd1-115">В файлах конфигурации клиента и службы задана и настроена привязка `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-115">The `wsHttpBinding` binding is specified and configured in the application configuration files for the client and service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ecbd1-116">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-116">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ecbd1-117">Код программы в образце практически идентичен службе [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) .</span><span class="sxs-lookup"><span data-stu-id="ecbd1-117">The program code in the sample is almost identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="ecbd1-118">Имеется одна дополнительная операция, предоставляемая контрактом службы - `GetCallerIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-118">There is one additional operation provided by the service contract - `GetCallerIdentity`.</span></span> <span data-ttu-id="ecbd1-119">Операция возвращает вызывающей стороне имя удостоверения вызывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-119">This operation returns the name of the caller's identity to the caller.</span></span>  

```csharp
public string GetCallerIdentity()  
{  
    // Use ServiceSecurityContext.WindowsIdentity to get the name of the caller.  
    return ServiceSecurityContext.Current.WindowsIdentity.Name;  
}  
```

 <span data-ttu-id="ecbd1-120">Перед построением и запуском примера необходимо с помощью мастера сертификатов веб-сервера создать и назначить сертификат.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-120">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="ecbd1-121">Определения конечной точки и привязки в файле конфигурации устанавливают режим безопасности `TransportWithMessageCredential`, как показано в следующем примере файла конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-121">The endpoint definition and binding definition in the configuration file settings enable `TransportWithMessageCredential` security mode, as shown in the following sample configuration for the client.</span></span>  
  
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
  
 <span data-ttu-id="ecbd1-122">Заданный адрес использует схему https://.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-122">The address specified uses the https:// scheme.</span></span> <span data-ttu-id="ecbd1-123">Конфигурация привязки задает режим безопасности `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-123">The binding configuration sets the security mode to `TransportWithMessageCredential`.</span></span> <span data-ttu-id="ecbd1-124">Тот же режим безопасности необходимо задать в файле Web.config службы.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-124">The same security mode must be specified in the service's Web.config file.</span></span>  
  
 <span data-ttu-id="ecbd1-125">Так как сертификат, используемый в этом примере, является тестовым сертификатом, созданным с помощью Makecert. exe, при попытке получить доступ к адресу https:, например `https://localhost/servicemodelsamples/service.svc`, в браузере появится предупреждение системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-125">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as  `https://localhost/servicemodelsamples/service.svc`, from your browser.</span></span> <span data-ttu-id="ecbd1-126">Чтобы разрешить клиенту WCF работать с тестовым сертификатом, к клиенту был добавлен дополнительный код для подавления оповещения системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-126">To allow the WCF client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="ecbd1-127">При использовании рабочих сертификатов этот код и соответствующие классы не требуются.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-127">This code, and the accompanying class, is not required when using production certificates.</span></span>  

```csharp
// WARNING: This code is only needed for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```
  
 <span data-ttu-id="ecbd1-128">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="ecbd1-129">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="ecbd1-129">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ecbd1-130">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="ecbd1-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ecbd1-131">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ecbd1-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ecbd1-132">Убедитесь, что выполнены инструкции по [установке сертификата сервера службы IIS (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="ecbd1-132">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
3. <span data-ttu-id="ecbd1-133">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ecbd1-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="ecbd1-134">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ecbd1-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
