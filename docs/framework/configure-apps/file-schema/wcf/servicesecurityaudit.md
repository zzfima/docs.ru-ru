---
title: "&lt;serviceSecurityAudit&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
caps.latest.revision: 17
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 17
---
# &lt;serviceSecurityAudit&gt;
Задает параметры, позволяющие проводить аудит событий безопасности во время обслуживания.  
  
## Синтаксис  
  
```  
  
<serviceSecurityAudit   
   auditLogLocation="Default/Application/Security"  
   messageAuthenticationAuditLevel= None/Success/Failure/SuccessAndFailure"  
   serviceAuthorizationAuditLevel="None/Success/Failure/SuccessAndFailure"  
   suppressAuditFailure="Boolean"  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|auditLogLocation|Задает местоположение журнала аудита.  Допустимы следующие значения:<br /><br /> -   Default: в ОС Windows XP события безопасности записываются в журнал приложений, а в Windows Server 2003 и Windows Vista \- в журнал событий.<br />-   Application: события аудита записываются в журнал событий приложений.<br />-   Security: события аудита записываются в журнал событий безопасности.<br /><br /> Значением по умолчанию является Default.  Для получения дополнительной информации см. <xref:System.ServiceModel.AuditLogLocation>.|  
|suppressAuditFailure|Логическое значение, задающее поведение для подавления ошибок записи в журнал аудита.<br /><br /> Приложения должны уведомляться об ошибках записи в журнал аудита.  Если в приложении не предусмотрена обработка ошибок аудита, необходимо использовать этот атрибут для подавления ошибок записи в журнал аудита.<br /><br /> Если этот атрибут имеет значение `true`, исключения, кроме OutOfMemoryException, StackOverFlowException, ThreadAbortException и ArgumentException, которые являются результатом попыток записи событий аудита, обрабатываются системой и не распространяются на приложение.  Если значением этого атрибута является `false`, все исключения, которые являются результатом попыток записи событий аудита, пропускаются в приложение.<br /><br /> Значение по умолчанию — `true`.|  
|serviceAuthorizationAuditLevel|Задает типы событий авторизации, записываемых в журнал аудита.  Допустимы следующие значения:<br /><br /> -   None: аудит событий авторизации службы не проводится.<br />-   Success: аудит выполняется только в отношении событий успешной авторизации службы.<br />-   Failure: аудит выполняется только в отношении событий неудачной авторизации службы.<br />-   SuccessAndFailure: выполняется аудит событий как успешной, так и неудачной авторизации службы.<br /><br /> По умолчанию используется значение None.  Для получения дополнительной информации см. <xref:System.ServiceModel.AuditLevel>.|  
|messageAuthenticationAuditLevel|Задает тип событий аудита проверки подлинности сообщений, заносимых в журнал.  Допустимы следующие значения:<br /><br /> -   None: события аудита не создаются.<br />-   Success: регистрируются только успешные события системы безопасности \(полная проверка, включая проверку сигнатуры сообщения, проверку шифрования и маркера\).<br />-   Failure: в журнал заносятся только ошибки.<br />-   SuccessAndFailure: в журнал заносятся как успешные события, так и ошибки.<br /><br /> По умолчанию используется значение None.  Для получения дополнительной информации см. <xref:System.ServiceModel.AuditLevel>.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<поведение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
  
## Заметки  
 Этот элемент конфигурации используется для аудита событий проверки подлинности [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  При включенном аудите может выполняться аудит либо успешных, либо неудачных попыток проверки подлинности \(или попыток обоих видов\).  События записываются в один из трех журналов событий: журнал приложения, журнал безопасности или журнал, используемый по умолчанию в данной версии операционной системы.  Все журналы событий можно просматривать при помощи средства просмотра событий Windows.  
  
 Подробный пример использования этого элемента конфигурации см. в разделе [Поведение аудита службы](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md).  
  
 По умолчанию в Windows XP события аудита отображаются в журнале приложений, а в операционных системах Windows Server 2003 и Windows Vista события аудита можно просмотреть в журнале безопасности.  Местоположение событий аудита можно задать, присвоив атрибуту `auditLogLocation` значение "Application" или "Security".  Для получения дополнительной информации см. [Практическое руководство. Аудит событий безопасности](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).  Если события записываются в журнал безопасности, то для «Success» и «Failure» необходимо выбрать параметр LocalSecurityPolicy\-\> Enable Object Access.  
  
 При просмотре журнала событий источником событий аудита является "ServiceModel Audit 3.0.0.0".  Записи аудита проверки подлинности сообщений относятся к категории "MessageAuthentication", а записи аудита авторизации служб \- к категории "ServiceAuthorization".  
  
 События аудита проверки подлинности сообщений указывают, не было ли сообщение подделано, не истек ли срок сообщения, а также может ли клиент пройти проверку подлинности при подключении к службе.  Они предоставляют следующие сведения: результат проверки подлинности, идентификационные данные клиента и конечной точки, в которую было отправлено сообщение, а также действие, связанное с сообщением.  
  
 К событиям аудита авторизации службы относится решение об авторизации, принятое диспетчером авторизации служб.  Они содержат следующие сведения: результат авторизации, идентификационные данные клиента, конечная точка, в которую было направлено сообщение, действие, связанное с сообщением, идентификатор контекста авторизации, созданный на основании входящего сообщения, и тип диспетчера авторизации, принявшего решение о предоставлении доступа.  
  
## Пример  
  
```  
<system.serviceModel>  
   <serviceBehaviors>  
      <behavior name="NewBehavior">  
         <serviceSecurityAudit auditLogLocation="Application"   
             suppressAuditFailure="true"  
             serviceAuthorizationAuditLevel="Success"   
             messageAuthenticationAuditLevel="Success" />  
      </behavior>  
   </serviceBehaviors>  
</behaviors>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>   
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>   
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Аудит](../../../../../docs/framework/wcf/feature-details/auditing-security-events.md)   
 [Практическое руководство. Аудит событий безопасности](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)   
 [Поведение аудита службы](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md)