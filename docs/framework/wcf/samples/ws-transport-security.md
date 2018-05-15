---
title: Безопасность транспорта WS
ms.date: 03/30/2017
ms.assetid: 33a20358-5e1b-458a-a6a9-15753bc7b99b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 66834a8bd8e783c0795cc65b3b197056b7c8da33
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ws-transport-security"></a><span data-ttu-id="d7dc2-102">Безопасность транспорта WS</span><span class="sxs-lookup"><span data-stu-id="d7dc2-102">WS Transport Security</span></span>
<span data-ttu-id="d7dc2-103">В этом образце показано использование безопасности транспорта SSL с привязкой <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-103">This sample demonstrates the use of SSL transport security with the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span> <span data-ttu-id="d7dc2-104">По умолчанию привязка `wsHttpBinding` обеспечивает взаимодействие по протоколу HTTP.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-104">By default, the `wsHttpBinding` binding provides HTTP communication.</span></span> <span data-ttu-id="d7dc2-105">При настройке для безопасности транспорта привязка поддерживает взаимодействие по протоколу HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-105">When configured for transport security, the binding supports HTTPS communication.</span></span> <span data-ttu-id="d7dc2-106">Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) , реализующий службу калькулятора.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-106">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="d7dc2-107">В файлах конфигурации клиента и службы задана и настроена привязка `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-107">The `wsHttpBinding` is specified and configured in the application configuration files for the client and service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d7dc2-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-108">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d7dc2-109">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d7dc2-110">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d7dc2-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d7dc2-111">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d7dc2-112">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsTransportSecurity`  
  
 <span data-ttu-id="d7dc2-113">В образце кода программы, идентичной [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) службы.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-113">The program code in the sample is identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="d7dc2-114">Перед построением и запуском примера необходимо с помощью мастера сертификатов веб-сервера создать и назначить сертификат.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-114">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="d7dc2-115">Определения конечной точки и привязки в файле конфигурации устанавливают режим безопасности `Transport`, как показано в следующем примере файла конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-115">The endpoint definition and binding definition in the configuration file settings enable `Transport` security mode, as shown in the following sample configuration for the client.</span></span>  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address="https://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as None -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="d7dc2-116">Заданный адрес использует схему https://.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-116">The address specified uses the https:// scheme.</span></span> <span data-ttu-id="d7dc2-117">Конфигурация привязки задает режим безопасности `Transport`.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-117">The binding configuration sets the security mode to `Transport`.</span></span> <span data-ttu-id="d7dc2-118">Тот же режим безопасности необходимо задать в файле Web.config службы.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-118">The same security mode must be specified in the service's Web.config file.</span></span>  
  
 <span data-ttu-id="d7dc2-119">Так как сертификат, используемый в этом примере является тестовым сертификатом, созданным Makecert.exe, появляется предупреждение системы безопасности появляется при попытке получить доступ к https: адреса, такие как https://localhost/servicemodelsamples/service.svc, из браузера.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-119">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as https://localhost/servicemodelsamples/service.svc, from your browser.</span></span> <span data-ttu-id="d7dc2-120">Чтобы разрешить клиента Windows Communication Foundation (WCF) для работы с тестовым сертификатом, в месте, был добавлен дополнительный код клиенту, чтобы подавить появление предупреждения системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-120">To allow the Windows Communication Foundation (WCF) client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="d7dc2-121">При использовании рабочих сертификатов этот код и соответствующие классы не требуются.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-121">This code, and the accompanying class, is not required when using production certificates.</span></span>  

```csharp
// This code is required only for test certificates like those created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```

 <span data-ttu-id="d7dc2-122">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-122">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="d7dc2-123">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-123">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d7dc2-124">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="d7dc2-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d7dc2-125">Установите [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0, выполнив следующую команду.</span><span class="sxs-lookup"><span data-stu-id="d7dc2-125">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="d7dc2-126">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d7dc2-126">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="d7dc2-127">Убедитесь, что вы выполнили [инструкции по установке сертификата сервера Internet Information Services (IIS)](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="d7dc2-127">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
4.  <span data-ttu-id="d7dc2-128">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d7dc2-128">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="d7dc2-129">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d7dc2-129">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7dc2-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d7dc2-130">See Also</span></span>
