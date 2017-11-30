---
title: WSHttpBinding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WS Profile binding
ms.assetid: 22d85b19-0135-4141-9179-a0e9c343ad73
caps.latest.revision: "39"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 81fe90c717a01cfc5f5669f8c22cdc34f8a1ab1b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="wshttpbinding"></a><span data-ttu-id="d8a11-102">WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="d8a11-102">WSHttpBinding</span></span>
<span data-ttu-id="d8a11-103">В этом образце показано, как с помощью [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] реализовать типовую службу и типовой клиент.</span><span class="sxs-lookup"><span data-stu-id="d8a11-103">This sample demonstrates how to implement a typical service and a typical client using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="d8a11-104">Этот образец содержит консольную программу клиента (client.exe) и библиотеку службы, размещаемую в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="d8a11-104">This sample consists of a client console program (client.exe) and a service library hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="d8a11-105">Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="d8a11-105">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="d8a11-106">Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (сложение, вычитание, умножение и деление).</span><span class="sxs-lookup"><span data-stu-id="d8a11-106">The contract is defined by the `ICalculator` interface, which exposes math operations (add, subtract, multiply, and divide).</span></span> <span data-ttu-id="d8a11-107">Клиент осуществляет синхронные вызовы заданной математической операции, а служба отправляет в ответ результат.</span><span class="sxs-lookup"><span data-stu-id="d8a11-107">The client makes synchronous requests to a given math operation and the service replies with the result.</span></span> <span data-ttu-id="d8a11-108">Действия клиента отображаются в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="d8a11-108">Client activity is visible in the console window.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d8a11-109">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d8a11-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d8a11-110">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="d8a11-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d8a11-111">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d8a11-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d8a11-112">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="d8a11-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsHttp`  
  
> [!NOTE]
>  <span data-ttu-id="d8a11-113">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="d8a11-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="d8a11-114">Этот образец предоставляет `ICalculator` контракта с помощью [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="d8a11-114">This sample exposes the `ICalculator` contract using the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="d8a11-115">Конфигурация этой привязки была расширена в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="d8a11-115">The configuration of this binding has been expanded in the Web.config file.</span></span>  
  
```xml
<bindings>  
  <wsHttpBinding>  
    <!--The following is the expanded configuration section for a-->  
    <!--WSHttpBinding. Each property is configured with the default-->   
    <!--value. See the ReliableSession, TransactionFlow, -->  
    <!--TransportSecurity, and MessageSecurity samples in the WS -->  
    <!--directory to learn how to configure these features. -->  
    <binding name="Binding1"  
              bypassProxyOnLocal="false"   
              transactionFlow="false"   
              hostNameComparisonMode="StrongWildcard"  
              maxBufferPoolSize="524288"   
              maxReceivedMessageSize="65536"  
              messageEncoding="Text"   
              textEncoding="utf-8"   
              useDefaultWebProxy="true"  
              allowCookies="false">  
      <reliableSession ordered="true"   
                       inactivityTimeout="00:10:00"  
                       enabled="false" />  
      <security mode="Message">  
        <message clientCredentialType="Windows"   
                 negotiateServiceCredential="true"  
                 algorithmSuite="Default"   
                 establishSecurityContext="true" />  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="d8a11-116">На базе элемента `binding` значение `maxReceivedMessageSize` позволяет задавать максимальный размер входящих сообщений (в байтах).</span><span class="sxs-lookup"><span data-stu-id="d8a11-116">On the base `binding` element, the `maxReceivedMessageSize` value lets you configure the maximum size of an incoming message (in bytes).</span></span> <span data-ttu-id="d8a11-117">Значение `hostNameComparisonMode` позволяет определить, нужно ли при демультиплексировании сообщений для службы учитывать имя узла.</span><span class="sxs-lookup"><span data-stu-id="d8a11-117">The `hostNameComparisonMode` value lets you configure whether the hostname is considered when de-multiplexing messages to the service.</span></span> <span data-ttu-id="d8a11-118">Значение `messageEncoding` позволяет задать кодирование сообщений (текст или MTOM).</span><span class="sxs-lookup"><span data-stu-id="d8a11-118">The `messageEncoding` value lets you configure whether to use Text or MTOM encoding for messages.</span></span> <span data-ttu-id="d8a11-119">Значение `textEncoding` позволяет задать кодировку сообщений.</span><span class="sxs-lookup"><span data-stu-id="d8a11-119">The `textEncoding` value lets you configure the character encoding for messages.</span></span> <span data-ttu-id="d8a11-120">Значение `bypassProxyOnLocal` позволяет задать, нужно ли использовать для локального взаимодействия HTTP-прокси.</span><span class="sxs-lookup"><span data-stu-id="d8a11-120">The `bypassProxyOnLocal` value lets you configure whether to use an HTTP proxy for local communication.</span></span> <span data-ttu-id="d8a11-121">Значение `transactionFlow` определяет, передается ли текущая транзакция через поток (если для операции включен поток транзакций).</span><span class="sxs-lookup"><span data-stu-id="d8a11-121">The `transactionFlow` value configures whether the current transaction is flowed (if an operation is configured for transaction flow).</span></span>  
  
 <span data-ttu-id="d8a11-122">На [ \<reliableSession >](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) включена логическое значение, которое настраивает ли включена поддержка надежных сеансов.</span><span class="sxs-lookup"><span data-stu-id="d8a11-122">On the [\<reliableSession>](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) element, the enabled Boolean value configures whether reliable sessions are enabled.</span></span> <span data-ttu-id="d8a11-123">Значение `ordered` определяет, сохраняется ли порядок сообщений.</span><span class="sxs-lookup"><span data-stu-id="d8a11-123">The `ordered` value configures whether message ordering is preserved.</span></span> <span data-ttu-id="d8a11-124">Значение `inactivityTimeout` определяет время, в течение которого сеанс может оставаться в состоянии бездействия, прежде чем он будет прерван.</span><span class="sxs-lookup"><span data-stu-id="d8a11-124">The `inactivityTimeout` value configures how long a session can be idle before being faulted.</span></span>  
  
 <span data-ttu-id="d8a11-125">На [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md), `mode` задает используемый режим безопасности.</span><span class="sxs-lookup"><span data-stu-id="d8a11-125">On the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md), the `mode` value configures which security mode should be used.</span></span> <span data-ttu-id="d8a11-126">В этом образце сообщений используется безопасность, передаваемый в том, почему [ \<сообщения >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) указывается внутри [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="d8a11-126">In this sample, messages security is being used, which is why the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) is specified inside the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="d8a11-127">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="d8a11-127">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="d8a11-128">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="d8a11-128">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d8a11-129">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="d8a11-129">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d8a11-130">Установите [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0, выполнив следующую команду.</span><span class="sxs-lookup"><span data-stu-id="d8a11-130">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="d8a11-131">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d8a11-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="d8a11-132">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d8a11-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="d8a11-133">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d8a11-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8a11-134">См. также</span><span class="sxs-lookup"><span data-stu-id="d8a11-134">See Also</span></span>
