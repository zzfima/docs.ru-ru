---
title: "Поведение аудита службы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59bf0cda-e496-4418-a3a1-2f0f6e85f8ce
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f84bff892a35288a75738d9cfa326ffc4119b433
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="service-auditing-behavior"></a><span data-ttu-id="7a453-102">Поведение аудита службы</span><span class="sxs-lookup"><span data-stu-id="7a453-102">Service Auditing Behavior</span></span>
<span data-ttu-id="7a453-103">Этот образец демонстрирует, как использовать <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> для включения аудита событий безопасности во время выполнения операций службы.</span><span class="sxs-lookup"><span data-stu-id="7a453-103">This sample demonstrates how to use the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to enable auditing of security events during service operations.</span></span> <span data-ttu-id="7a453-104">Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="7a453-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="7a453-105">Служба и клиент были настроены с помощью [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="7a453-105">The service and client have been configured using the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="7a453-106">`mode` Атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) ему было присвоено `Message` и `clientCredentialType` ему было присвоено `Windows`.</span><span class="sxs-lookup"><span data-stu-id="7a453-106">The `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) has been set to `Message` and `clientCredentialType` has been set to `Windows`.</span></span> <span data-ttu-id="7a453-107">В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="7a453-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a453-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="7a453-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="7a453-109">В файле конфигурации службы для настройки аудита используется элемент `serviceSecurityAudit`.</span><span class="sxs-lookup"><span data-stu-id="7a453-109">The service configuration file uses the `serviceSecurityAudit` element to configure auditing.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      ...  
<!-- serviceSecurityAudit allows specification of audit location   
     and whether to audit success, failure or both. This service   
     logs success and failure of messageAuthentication   
     to the default location -->  
     <serviceSecurityAudit auditLogLocation ="Default" messageAuthenticationAuditLevel = "SuccessOrFailure" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="7a453-110">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="7a453-110">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="7a453-111">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="7a453-111">Press ENTER in the console window to shut down the client.</span></span>  
  
 <span data-ttu-id="7a453-112">Получающиеся журналы аудита можно просматривать в программе Просмотр событий.</span><span class="sxs-lookup"><span data-stu-id="7a453-112">The resulting audit logs can be seen by running the Event Viewer.</span></span> <span data-ttu-id="7a453-113">По умолчанию в Windows XP события аудита отображаются в журнале приложений, а в операционных системах Windows Server 2003 и Windows Vista события аудита можно просмотреть в журнале безопасности.</span><span class="sxs-lookup"><span data-stu-id="7a453-113">By default, on Windows XP the audit events can be seen in the Application Log while on Windows Server 2003 and Windows Vista, the audit events can be seen in the Security Log.</span></span> <span data-ttu-id="7a453-114">В Windows Server 2008 и Windows 7 события аудита можно увидеть в журналах приложений и служб.</span><span class="sxs-lookup"><span data-stu-id="7a453-114">On Windows Server 2008 and Windows 7, the audit events can be seen in the Applications and Services logs.</span></span> <span data-ttu-id="7a453-115">Местоположение событий аудита можно указать, задав `auditLogLocation` атрибут «Приложение» или «Безопасность».</span><span class="sxs-lookup"><span data-stu-id="7a453-115">The location of audit events can be specified by setting the `auditLogLocation` attribute to "Application" or "Security".</span></span> <span data-ttu-id="7a453-116">Дополнительные сведения см. в разделе [как: события аудита безопасности](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).</span><span class="sxs-lookup"><span data-stu-id="7a453-116">For more information, see [How to: Audit Security Events](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).</span></span> <span data-ttu-id="7a453-117">Если события записываются в журнал безопасности, то для Success и Failure необходимо выбрать параметр LocalSecurityPolicy-> Enable Object Access.</span><span class="sxs-lookup"><span data-stu-id="7a453-117">If the events are written in the Security Log the LocalSecurityPolicy-> Enable Object Access should be set for "Success" and "Failure".</span></span>  
  
 <span data-ttu-id="7a453-118">При просмотре журнала событий источником событий аудита является "ServiceModel Audit 3.0.0.0".</span><span class="sxs-lookup"><span data-stu-id="7a453-118">When looking at the event log, the source of the audit events is "ServiceModel Audit 3.0.0.0".</span></span> <span data-ttu-id="7a453-119">Записи аудита проверки подлинности сообщений имеют категории «Messageauthentication», а записи аудита авторизации служб к категории «ServiceAuthorization».</span><span class="sxs-lookup"><span data-stu-id="7a453-119">Message authentication audit records have a category of "MessageAuthentication" while service authorization audit records have a category of "ServiceAuthorization".</span></span>  
  
 <span data-ttu-id="7a453-120">События аудита проверки подлинности сообщений указывают, не было ли сообщение подделано, не истек ли срок его действия, а также может ли клиент пройти проверку подлинности при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="7a453-120">Message authentication audit events cover whether the message was tampered with, whether the message has expired, and whether the client can authenticate to the service.</span></span> <span data-ttu-id="7a453-121">Они предоставляют следующие сведения: результат проверки подлинности, идентификационные данные клиента и конечной точки, в которую было отправлено сообщение, а также действие, связанное с сообщением.</span><span class="sxs-lookup"><span data-stu-id="7a453-121">They provide information about whether the authentication succeeded or failed along with the identity of the client, and the endpoint the message was sent to along with the action associated with the message.</span></span>  
  
 <span data-ttu-id="7a453-122">К событиям аудита авторизации службы относится решение об авторизации, принятое диспетчером авторизации служб.</span><span class="sxs-lookup"><span data-stu-id="7a453-122">Service authorization audit events cover the authorization decision made by a service authorization manager.</span></span> <span data-ttu-id="7a453-123">Они содержат следующие сведения: результат авторизации, идентификационные данные клиента, конечная точка, в которую было направлено сообщение, действие, связанное с сообщением, идентификатор контекста авторизации, созданный на основании входящего сообщения, и тип диспетчера авторизации, принявшего решение о предоставлении доступа.</span><span class="sxs-lookup"><span data-stu-id="7a453-123">They provide information about whether authorization succeeded or failed along with the identity of the client, the endpoint the message was sent to, the action associated with the message, the identifier of the authorization context that was generated from the incoming message, and the type of the authorization manager that made the access decision.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7a453-124">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="7a453-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="7a453-125">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7a453-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="7a453-126">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7a453-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="7a453-127">Для запуска образца в конфигурации с одним или несколькими компьютерами следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7a453-127">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a453-128">См. также</span><span class="sxs-lookup"><span data-stu-id="7a453-128">See Also</span></span>  
 [<span data-ttu-id="7a453-129">Аудит</span><span class="sxs-lookup"><span data-stu-id="7a453-129">Auditing</span></span>](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 [<span data-ttu-id="7a453-130">Как: аудит событий безопасности</span><span class="sxs-lookup"><span data-stu-id="7a453-130">How to: Audit Security Events</span></span>](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)
