---
title: "Поведение аудита службы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 59bf0cda-e496-4418-a3a1-2f0f6e85f8ce
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Поведение аудита службы
Этот образец демонстрирует, как использовать <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> для включения аудита событий безопасности во время выполнения операций службы.Этот образец основан на примере [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).Служба и клиент настроены с помощью элемента [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).Для атрибута `mode` элемента [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) задано значение `Message`, а для `clientCredentialType` задано значение `Windows`.В этом образце клиентом является консольное приложение \(EXE\), а служба размещается в службах IIS.  
  
> [!NOTE]
>  Процедура установки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В файле конфигурации службы для настройки аудита используется элемент `serviceSecurityAudit`.  
  
```  
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
  
 При выполнении образца запросы и ответы операций отображаются в окне консоли клиента.Чтобы закрыть клиент, нажмите клавишу ВВОД в окне консоли.  
  
 Получающиеся журналы аудита можно просматривать в программе Просмотр событий.По умолчанию в Windows XP события аудита отображаются в журнале приложений, а в операционных системах Windows Server 2003 и Windows Vista события аудита можно просмотреть в журнале безопасности.В Windows Server 2008 и Windows 7 события аудита можно увидеть в журналах приложений и служб.Чтобы задать местоположение событий аудита, присвойте атрибуту `auditLogLocation` значение Application или Security.Дополнительные сведения см. в разделе [Практическое руководство. Аудит событий безопасности](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).Если события записываются в журнал безопасности, то для Success и Failure необходимо выбрать параметр LocalSecurityPolicy\-\> Enable Object Access.  
  
 При просмотре журнала событий источником событий аудита является "ServiceModel Audit 3.0.0.0".Записи аудита проверки подлинности сообщений относятся к категории «MessageAuthentication», а записи аудита авторизации служб — к категории «ServiceAuthorization».  
  
 События аудита проверки подлинности сообщений указывают, не было ли сообщение подделано, не истек ли срок его действия, а также может ли клиент пройти проверку подлинности при подключении к службе.Они предоставляют следующие сведения: результат проверки подлинности, идентификационные данные клиента и конечной точки, в которую было отправлено сообщение, а также действие, связанное с сообщением.  
  
 К событиям аудита авторизации службы относится решение об авторизации, принятое диспетчером авторизации служб.Они содержат следующие сведения: результат авторизации, идентификационные данные клиента, конечная точка, в которую было направлено сообщение, действие, связанное с сообщением, идентификатор контекста авторизации, созданный на основании входящего сообщения, и тип диспетчера авторизации, принявшего решение о предоставлении доступа.  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы запустить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## См. также  
 [Аудит](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)   
 [Практическое руководство. Аудит событий безопасности](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)