---
title: "Безопасность поведений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 19710ae3-f197-4d28-ba9d-52e465006819
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# Безопасность поведений
В этом разделе приведены образцы, демонстрирующие настройку безопасности для поведения служб.  
  
## В этом подразделе  
 [Поведение аудита службы](../../../../docs/framework/wcf/samples/service-auditing-behavior.md)  
 Этот образец демонстрирует, как использовать <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> для включения аудита событий безопасности во время выполнения операций службы.  
  
 [Поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 В этом образце показано, как служба может с помощью поставщиков членства и ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] выполнять проверку подлинности и авторизацию клиентов.  
  
 [Авторизация доступа к операциям службы](../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 В этом примере показано, как использовать [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md), чтобы включить использование атрибута <xref:System.Security.Permissions.PrincipalPermissionAttribute> для авторизации доступа к операциям службы.  
  
 [Олицетворение клиента](../../../../docs/framework/wcf/samples/impersonating-the-client.md)  
 В этом образце показано, как олицетворять приложение абонента в службе таким образом, чтобы служба могла получить доступ к ресурсам системы от лица абонента.