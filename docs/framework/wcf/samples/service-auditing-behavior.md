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
ms.workload: dotnet
ms.openlocfilehash: 140793e41be012a777dbfa4bf66528612ab33da7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="service-auditing-behavior"></a>Поведение аудита службы
Этот образец демонстрирует, как использовать <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> для включения аудита событий безопасности во время выполнения операций службы. Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md). Служба и клиент были настроены с помощью [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). `mode` Атрибут [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) ему было присвоено `Message` и `clientCredentialType` ему было присвоено `Windows`. В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В файле конфигурации службы для настройки аудита используется элемент `serviceSecurityAudit`.  
  
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
  
 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне консоли.  
  
 Получающиеся журналы аудита можно просматривать в программе Просмотр событий. По умолчанию в Windows XP события аудита отображаются в журнале приложений, а в операционных системах Windows Server 2003 и Windows Vista события аудита можно просмотреть в журнале безопасности. В Windows Server 2008 и Windows 7 события аудита можно увидеть в журналах приложений и служб. Местоположение событий аудита можно указать, задав `auditLogLocation` атрибут «Приложение» или «Безопасность». Дополнительные сведения см. в разделе [как: события аудита безопасности](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md). Если события записываются в журнал безопасности, то для Success и Failure необходимо выбрать параметр LocalSecurityPolicy-> Enable Object Access.  
  
 При просмотре журнала событий источником событий аудита является "ServiceModel Audit 3.0.0.0". Записи аудита проверки подлинности сообщений имеют категории «Messageauthentication», а записи аудита авторизации служб к категории «ServiceAuthorization».  
  
 События аудита проверки подлинности сообщений указывают, не было ли сообщение подделано, не истек ли срок его действия, а также может ли клиент пройти проверку подлинности при подключении к службе. Они предоставляют следующие сведения: результат проверки подлинности, идентификационные данные клиента и конечной точки, в которую было отправлено сообщение, а также действие, связанное с сообщением.  
  
 К событиям аудита авторизации службы относится решение об авторизации, принятое диспетчером авторизации служб. Они содержат следующие сведения: результат авторизации, идентификационные данные клиента, конечная точка, в которую было направлено сообщение, действие, связанное с сообщением, идентификатор контекста авторизации, созданный на основании входящего сообщения, и тип диспетчера авторизации, принявшего решение о предоставлении доступа.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Для запуска образца в конфигурации с одним или несколькими компьютерами следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>См. также  
 [Аудит](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 [Практическое руководство. Аудит событий безопасности](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)
