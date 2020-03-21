---
title: Практическое руководство. Аудит событий безопасности Windows Communication Foundation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], auditing events
ms.assetid: e71e9587-3336-46a2-9a9e-d72a1743ecec
ms.openlocfilehash: 62d26b24b5d46427c1871fccf48b063c45781beb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185114"
---
# <a name="how-to-audit-windows-communication-foundation-security-events"></a>Практическое руководство. Аудит событий безопасности Windows Communication Foundation
Фонд связи Windows (WCF) позволяет регистрировать события безопасности в журнале событий Windows, который можно просматривать с помощью Windows Event Viewer. В этом разделе описано, как настроить приложение, чтобы события безопасности регистрировались в журнале. Для получения дополнительной информации о [Auditing](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)аудите WCF см.  
  
### <a name="to-audit-security-events-in-code"></a>Аудит событий безопасности в коде  
  
1. Укажите расположение журнала аудита. Для этого присвойте свойству <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> класса <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> одно из значений перечисления <xref:System.ServiceModel.AuditLogLocation>, как показано в следующем примере кода.  
  
     [!code-csharp[AuditingSecurityEvents#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#2)]
     [!code-vb[AuditingSecurityEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#2)]  
  
     Перечисление <xref:System.ServiceModel.AuditLogLocation> имеет три значения: `Application` `Security`, `Default`или . Эти значения определяют один журналов, доступных в средстве "Просмотр событий" - журнал безопасности или журнал приложения. Если установлено значение `Default`, выбор журнала будет зависеть от параметров операционной системы, в которой выполняется приложение. Если аудит включен, а расположение журнала аудита не задано, по умолчанию для платформ, поддерживающих ведение журнала безопасности, используется значение `Security`; в противном случае используется значение `Application`. Только Windows Server 2003 и Windows Vista поддерживают запись в журнал безопасности по умолчанию.  
  
2. Настройте типы событий для аудита. Возможен одновременный аудит событий уровня службы и событий авторизации уровня сообщений. Для этого присвойте свойству <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> или свойству <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> одно из значений перечисления <xref:System.ServiceModel.AuditLevel>, как показано в следующем примере кода.  
  
     [!code-csharp[AuditingSecurityEvents#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#3)]
     [!code-vb[AuditingSecurityEvents#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#3)]  
  
3. Укажите, нужно ли подавлять сбои приложения, связанные с событиями аудита. Задайте для свойства <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> значение `true` или `false`, как показано в следующем примере кода.  
  
     [!code-csharp[AuditingSecurityEvents#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#4)]
     [!code-vb[AuditingSecurityEvents#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#4)]  
  
     По умолчанию свойство `SuppressAuditFailure` имеет значение `true`, т. е. сбои аудита не отражаются на приложении. В противном случае создается исключение. В случае успешного аудита записывается подробная трассировка. В случае неудачного аудита трассировка записывается на уровне ошибки.  
  
4. Удалите существующий объект <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> из коллекции поведений в описании <xref:System.ServiceModel.ServiceHost>. Коллекция поведений доступна по свойству <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>, которое в свою очередь доступно по свойству <xref:System.ServiceModel.ServiceHostBase.Description%2A>. После этого добавьте новое поведение <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> в ту же коллекцию, как показано в следующем примере кода.  
  
     [!code-csharp[AuditingSecurityEvents#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#5)]
     [!code-vb[AuditingSecurityEvents#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#5)]  
  
### <a name="to-set-up-auditing-in-configuration"></a>Настройка аудита в файле конфигурации  
  
1. Чтобы настроить аудит в конфигурации, добавьте [ \<элемент поведения>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) в [ \<>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) раздела web.config. Затем добавьте [ \<>элемент serviceSecurityAudit](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) и установите различные атрибуты, как показано в следующем примере.  
  
    ```xml  
    <behaviors>  
       <behavior name="myAuditBehavior">  
          <serviceSecurityAudit auditLogLocation="Application"  
                suppressAuditFailure="false"
                serviceAuthorizationAuditLevel="None"
                messageAuthenticationAuditLevel="SuccessOrFailure" />  
          </behavior>  
    </behaviors>  
    ```  
  
2. Необходимо задать поведение службы, как показано в следующем примере.  
  
    ```xml  
    <services>  
        <service type="WCS.Samples.Service.Echo"
        behaviorConfiguration=" myAuditBehavior">  
           <endpoint address=""  
                    binding="wsHttpBinding"  
                    bindingConfiguration="CertificateDefault"
                    contract="WCS.Samples.Service.IEcho" />  
        </service>  
    </services>  
    ```  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как создать экземпляр класса <xref:System.ServiceModel.ServiceHost> и добавить новый <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> в его коллекцию поведений.  
  
 [!code-csharp[AuditingSecurityEvents#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#1)]
 [!code-vb[AuditingSecurityEvents#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#1)]  
  
## <a name="net-framework-security"></a>Безопасность .NET Framework  
 Если для свойства <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> задать значение `true`, все неудачные попытки создания аудита безопасности будут подавляться (если задано значение `false`, будет создаваться исключение). Однако при впуске следующего свойства **локальной настройки безопасности** Windows сбой в генерации событий аудита приведет к немедленному отключению Windows:  
  
 **Аудит: немедленное отключение системы, если невозможно внести в журнал записи об аудите безопасности.**  
  
 Чтобы установить свойство, откройте поле для диалога **«Настройки безопасности».** В **настройках безопасности**нажмите **локальные политики.** Затем нажмите **Параметры безопасности**.  
  
 Если <xref:System.ServiceModel.AuditLogLocation> свойство настроено на <xref:System.ServiceModel.AuditLogLocation.Security> объект и **доступ к объекту аудита** не установлен в **локальной политике безопасности,** события аудита не будут записаны в журнал безопасности. Обратите внимание, что ошибка не возвращается, а события аудита не регистрируются в журнале безопасности.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
- <xref:System.ServiceModel.AuditLogLocation>
- [Аудита](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
