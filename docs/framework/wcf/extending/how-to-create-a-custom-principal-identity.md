---
title: "Практическое руководство. Создание пользовательского идентификатора участника | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IAuthorizationPolicy"
  - "IPrincipal"
  - "PrincipalPermissionAttribute"
  - "PrincipalPermissionMode"
ms.assetid: c4845fca-0ed9-4adf-bbdc-10812be69b61
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Практическое руководство. Создание пользовательского идентификатора участника
<xref:System.Security.Permissions.PrincipalPermissionAttribute> является декларативным средством управления доступом к методам службы.  При использовании данного атрибута перечисление <xref:System.ServiceModel.Description.PrincipalPermissionMode> указывает режим выполнения проверки авторизации.  Если данный режим установлен как <xref:System.ServiceModel.Description.PrincipalPermissionMode>, пользователь может указать пользовательский класс <xref:System.Security.Principal.IPrincipal>, возвращаемый свойством <xref:System.Threading.Thread.CurrentPrincipal%2A>.  В данном разделе описан сценарий, в котором <xref:System.ServiceModel.Description.PrincipalPermissionMode> используется совместно с пользовательской политикой авторизации и пользовательским участником.  
  
 Дополнительные сведения об использовании <xref:System.Security.Permissions.PrincipalPermissionAttribute> см. в разделе [Как ограничить доступ с использованием класса PrincipalPermissionAttribute](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).  
  
## Пример  
 [!code-csharp[PrincipalPermissionMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/principalpermissionmode/cs/source.cs#8)]
 [!code-vb[PrincipalPermissionMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/principalpermissionmode/vb/source.vb#8)]  
  
## Компиляция кода  
 Для компиляции кода необходимы ссылки на следующие пространства имен.  
  
-   <xref:System>  
  
-   <xref:System.Collections.Generic>  
  
-   <xref:System.Security.Permissions>  
  
-   <xref:System.Security.Principal>  
  
-   <xref:System.Threading>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.ServiceModel.Channels>  
  
-   <xref:System.ServiceModel.Description>  
  
-   <xref:System.IdentityModel.Claims>  
  
-   <xref:System.IdentityModel.Policy>  
  
## См. также  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>   
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>   
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>   
 [Как использовать поставщик ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)   
 [Как ограничить доступ с использованием класса PrincipalPermissionAttribute](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)