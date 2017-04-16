---
title: "Практическое руководство. Аудит событий безопасности Windows Communication Foundation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "безопасность [WCF], аудит событий"
ms.assetid: e71e9587-3336-46a2-9a9e-d72a1743ecec
caps.latest.revision: 19
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 19
---
# Практическое руководство. Аудит событий безопасности Windows Communication Foundation
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] позволяет регистрировать события безопасности в журнале событий Windows, которые можно просматривать с помощью средства "Просмотр событий" Windows.  В этом разделе описано, как настроить приложение, чтобы события безопасности регистрировались в журнале.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] аудите см. в разделе [Аудит](../../../../docs/framework/wcf/feature-details/auditing-security-events.md).  
  
### Аудит событий безопасности в коде  
  
1.  Укажите расположение журнала аудита.  Для этого присвойте свойству <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A> класса <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> одно из значений перечисления <xref:System.ServiceModel.AuditLogLocation>, как показано в следующем примере кода.  
  
     [!code-csharp[AuditingSecurityEvents#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#2)]
     [!code-vb[AuditingSecurityEvents#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#2)]  
  
     У перечисления <xref:System.ServiceModel.AuditLogLocation> имеется три значения: `Application`, `Security` и `Default`.  Эти значения определяют один журналов, доступных в средстве "Просмотр событий" \- журнал безопасности или журнал приложения.  Если установлено значение `Default`, выбор журнала будет зависеть от параметров операционной системы, в которой выполняется приложение.  Если аудит включен, а расположение журнала аудита не задано, по умолчанию для платформ, поддерживающих ведение журнала безопасности, используется значение `Security`; в противном случае используется значение `Application`.  Только операционные системы [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] и [!INCLUDE[wv](../../../../includes/wv-md.md)] по умолчанию поддерживают ведение журнала безопасности.  
  
2.  Настройте типы событий для аудита.  Возможен одновременный аудит событий уровня службы и событий авторизации уровня сообщений.  Для этого присвойте свойству <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.ServiceAuthorizationAuditLevel%2A> или свойству <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.MessageAuthenticationAuditLevel%2A> одно из значений перечисления <xref:System.ServiceModel.AuditLevel>, как показано в следующем примере кода.  
  
     [!code-csharp[AuditingSecurityEvents#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#3)]
     [!code-vb[AuditingSecurityEvents#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#3)]  
  
3.  Укажите, нужно ли подавлять сбои приложения, связанные с событиями аудита.  Задайте для свойства <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> значение `true` или `false`, как показано в следующем примере кода.  
  
     [!code-csharp[AuditingSecurityEvents#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#4)]
     [!code-vb[AuditingSecurityEvents#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#4)]  
  
     По умолчанию свойство `SuppressAuditFailure` имеет значение `true`, т. е. сбои аудита не отражаются на приложении.  В противном случае создается исключение.  В случае успешного аудита записывается подробная трассировка.  В случае неудачного аудита трассировка записывается на уровне ошибки.  
  
4.  Удалите существующий объект <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> из коллекции поведений в описании <xref:System.ServiceModel.ServiceHost>.  Коллекция поведений доступна по свойству <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>, которое в свою очередь доступно по свойству <xref:System.ServiceModel.ServiceHostBase.Description%2A>.  После этого добавьте новое поведение <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> в ту же коллекцию, как показано в следующем примере кода.  
  
     [!code-csharp[AuditingSecurityEvents#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#5)]
     [!code-vb[AuditingSecurityEvents#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#5)]  
  
### Настройка аудита в файле конфигурации  
  
1.  Чтобы настроить аудит в файле конфигурации, добавьте элемент [\<поведение\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) в раздел [\<поведения\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) файла web.config.  После этого добавьте элемент [\<serviceSecurityAudit\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md) и задайте атрибуты, как показано в следующем примере.  
  
    ```  
    <behaviors>  
       <behavior name="myAuditBehavior">  
          <serviceSecurityAudit auditLogLocation="Application"  
                suppressAuditFailure="false"   
                serviceAuthorizationAuditLevel="None"   
                messageAuthenticationAuditLevel="SuccessOrFailure" />  
          </behavior>  
    </behaviors>  
    ```  
  
2.  Необходимо задать поведение службы, как показано в следующем примере.  
  
    ```  
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
  
## Пример  
 В следующем примере кода показано, как создать экземпляр класса <xref:System.ServiceModel.ServiceHost> и добавить новый <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> в его коллекцию поведений.  
  
 [!code-csharp[AuditingSecurityEvents#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/auditingsecurityevents/cs/auditingsecurityevents.cs#1)]
 [!code-vb[AuditingSecurityEvents#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/auditingsecurityevents/vb/auditingsecurityevents.vb#1)]  
  
## Безопасность платформы .NET Framework  
 Если для свойства <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.SuppressAuditFailure%2A> задать значение `true`, все неудачные попытки создания аудита безопасности будут подавляться \(если задано значение `false`, будет создаваться исключение\).  Если же включить следующее свойство Windows **Параметр локальной безопасности**, сбой создания событий вызовет немедленное завершение работы Windows:  
  
 **Аудит: немедленное отключение системы, если невозможно внести в журнал записи об аудите безопасности**  
  
 Чтобы задать это свойство, откройте диалоговое окно **Локальные параметры безопасности**.  В разделе **Параметры безопасности** выберите **Локальные политики**.  Затем щелкните **Параметры безопасности**.  
  
 Если свойство <xref:System.ServiceModel.AuditLogLocation> имеет значение <xref:System.ServiceModel.AuditLogLocation>, а для параметра **Аудит доступа к объектам** не задано значение **Локальная политика безопасности**, события аудита не будут регистрироваться в журнале безопасности.  Обратите внимание, что ошибка не возвращается, а события аудита не регистрируются в журнале безопасности.  
  
## См. также  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior.AuditLogLocation%2A>   
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>   
 <xref:System.ServiceModel.AuditLogLocation>   
 [Аудит](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)