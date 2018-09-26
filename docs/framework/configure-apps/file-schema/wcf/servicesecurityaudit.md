---
title: '&lt;serviceSecurityAudit&gt;'
ms.date: 03/30/2017
ms.assetid: ba517369-a034-4f8e-a2c4-66517716062b
author: BrucePerlerMS
ms.openlocfilehash: 3cdadedd3c9fda3874409ecad9a0f63ac34f2497
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47196191"
---
# <a name="ltservicesecurityauditgt"></a>&lt;serviceSecurityAudit&gt;
Задает параметры, позволяющие проводить аудит событий безопасности во время обслуживания.  
  
 \<система. ServiceModel >  
\<варианты поведения >  
\<serviceBehaviors >  
\<поведение >  
\<serviceSecurityAudit >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<serviceSecurityAudit   
   auditLogLocation="Default/Application/Security"  
   messageAuthenticationAuditLevel= None/Success/Failure/SuccessOrFailure"   serviceAuthorizationAuditLevel="None/Success/Failure/SuccessOrFailure"  
   suppressAuditFailure="Boolean"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|auditLogLocation|Задает местоположение журнала аудита. Допустимы следующие значения:<br /><br /> -По умолчанию: События безопасности записываются в журнал приложений в Windows XP и в журнал событий в Windows Server 2003 и Windows Vista.<br />-Application: События аудита записываются в журнал событий приложений.<br />-Безопасность: События аудита записываются в журнал событий безопасности.<br /><br /> Значением по умолчанию является Default. Для получения дополнительной информации см. <xref:System.ServiceModel.AuditLogLocation>.|  
|suppressAuditFailure|Логическое значение, задающее поведение для подавления ошибок записи в журнал аудита.<br /><br /> Приложения должны уведомляться об ошибках записи в журнал аудита. Если в приложении не предусмотрена обработка ошибок аудита, необходимо использовать этот атрибут для подавления ошибок записи в журнал аудита.<br /><br /> Если этот атрибут имеет значение `true`, исключения, кроме OutOfMemoryException, StackOverFlowException, ThreadAbortException и ArgumentException, которые являются результатом попыток записи событий аудита, обрабатываются системой и не распространяются на приложение. Если значением этого атрибута является `false`, все исключения, которые являются результатом попыток записи событий аудита, пропускаются в приложение.<br /><br /> Значение по умолчанию — `true`.|  
|serviceAuthorizationAuditLevel|Задает типы событий авторизации, записываемых в журнал аудита. Допустимы следующие значения:<br /><br /> -None: Аудит событий авторизации службы не выполняется.<br />— Успешное завершение: Подлежат аудиту только событий успешной авторизации службы.<br />-Ошибка: Подлежат аудиту только событий неудачной авторизации службы.<br />-SuccessOrFailure: Оба аудита успешных и неудачных событий авторизации службы.<br /><br /> По умолчанию используется значение None. Для получения дополнительной информации см. <xref:System.ServiceModel.AuditLevel>.|  
|messageAuthenticationAuditLevel|Задает тип событий аудита проверки подлинности сообщений, заносимых в журнал. Допустимы следующие значения:<br /><br /> -None: События аудита не создается.<br />— Успешное завершение: Регистрируются только события безопасности завершается успешно (полная проверка, включая проверку сигнатуры сообщения, шифрования и проверки маркеров).<br />-Ошибка: Регистрируются только ошибки.<br />-SuccessOrFailure: Оба успешных и неудачных событий.<br /><br /> По умолчанию используется значение None. Дополнительные сведения см. в разделе <xref:System.ServiceModel.AuditLevel>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<поведение >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент конфигурации используется для аудита событий проверки подлинности Windows Communication Foundation (WCF). При включенном аудите может выполняться аудит либо успешных, либо неудачных попыток проверки подлинности (или попыток обоих видов). События записываются в один из трех журналов событий: журнал приложения, журнал безопасности или журнал, используемый по умолчанию в данной версии операционной системы. Все журналы событий можно просматривать при помощи средства просмотра событий Windows.  
  
 Подробный пример использования этого элемента конфигурации, см. в разделе [поведение аудита службы](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md).  
  
 По умолчанию в Windows XP события аудита отображаются в журнале приложений, а в операционных системах Windows Server 2003 и Windows Vista события аудита можно просмотреть в журнале безопасности. Местоположение событий аудита можно задать, присвоив атрибуту `auditLogLocation` значение "Application" или "Security". Дополнительные сведения см. в разделе [как: события аудита безопасности](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md). Если события записываются в журнал безопасности, то для «Success» и «Failure» необходимо выбрать параметр LocalSecurityPolicy-> Enable Object Access.  
  
 При просмотре журнала событий источником событий аудита является "ServiceModel Audit 3.0.0.0". Записи аудита проверки подлинности сообщений относятся к категории "MessageAuthentication", а записи аудита авторизации служб - к категории "ServiceAuthorization".  
  
 События аудита проверки подлинности сообщений указывают, не было ли сообщение подделано, не истек ли срок сообщения, а также может ли клиент пройти проверку подлинности при подключении к службе. Они предоставляют следующие сведения: результат проверки подлинности, идентификационные данные клиента и конечной точки, в которую было отправлено сообщение, а также действие, связанное с сообщением.  
  
 К событиям аудита авторизации службы относится решение об авторизации, принятое диспетчером авторизации служб. Они предоставляют сведения о ли авторизация пользователя завершена успешно или идентификационные клиента, конечная точка сообщение было отправлено, действие, связанное с сообщением, идентификатор контекста авторизации, который был создан из входящие сообщения и тип диспетчера авторизации, принявшего решение о предоставлении доступа.  
  
## <a name="example"></a>Пример  
  
```xml  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.ServiceSecurityAuditElement>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>  
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Аудит](../../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
 [Практическое руководство. Аудит событий безопасности](../../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md)  
 [Поведение аудита службы](../../../../../docs/framework/wcf/samples/service-auditing-behavior.md)
