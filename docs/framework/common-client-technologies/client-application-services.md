---
title: "Службы клиентских приложений | Microsoft Docs"
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
  - "параметры приложения, службы клиентских приложений"
  - "службы ASP.NET, службы клиентских приложений"
  - "проверка подлинности [ASP.NET], службы клиентских приложений"
  - "службы клиентских приложений"
  - "службы клиентских приложений, сведения о службах клиентских приложений"
  - "клиентские приложения, службы ASP.NET"
  - "учетные данные [платформа .NET Framework]"
  - "входы [службы клиентских приложений]"
  - "профили [ASP.NET], службы клиентских приложений"
  - "безопасность на основе ролей [платформа .NET Framework], службы клиентских приложений"
  - "роли [платформа .NET Framework], службы клиентских приложений"
  - "совместное использование информации и функциональность [службы клиентских приложений]"
  - "веб-параметры [службы клиентских приложений]"
  - "приложения Windows, службы клиентских приложений"
ms.assetid: 1487d8df-089e-4f21-abfb-a791a652b58e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Службы клиентских приложений
Службы клиентских приложений позволяют легко создавать приложения Windows, использующие службы входа, ролей, профилей [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)], которые включены в расширения Microsoft ASP.NET 2.0 AJAX.  Эти службы позволяют нескольким веб\-приложениям и приложениям Windows использовать сведения о пользователе и функции управления пользователями с одного сервера.  Например, эти службы можно использовать для решения следующих задач.  
  
-   Проверка подлинности.  Для проверки удостоверения пользователя можно использовать службу проверки подлинности.  
  
-   Определение роли или ролей выполнившего проверку подлинности пользователя.  Изменить пользовательский интерфейс приложения в соответствии с ролью пользователя можно с помощью службы ролей.  Например, можно предоставить дополнительные функции для пользователей с ролью администратора.  
  
-   Хранение параметров пользовательских приложений на сервере и доступ к ним.  Вы можете использовать веб\-службу параметров \(другое название — служба профилей\) для разделения параметров между несколькими приложениями и расположениями.  
  
 Службы клиентских приложений используют преимущество модели расширяемости веб\-служб через поставщиков клиентских служб, которых можно указать в файлах конфигурации приложения.  Эти поставщики служб предоставляют автономную функциональность, использующую локальный кэш для проверки подлинности, хранения данных о ролях и параметрах, если сетевое подключение недоступно.  
  
 Дополнительные сведения о службах приложений [!INCLUDE[ajax_current_short](../../../includes/ajax-current-short-md.md)] см. в разделе [ASP.NET Application Services Overview](../Topic/ASP.NET%20Application%20Services%20Overview.md).  
  
## В этом подразделе  
 [Общие сведения о службах клиентских приложений](../../../docs/framework/common-client-technologies/client-application-services-overview.md)  
 Описание функций, доступных через поставщиков служб клиентских приложений.  
  
 [Практическое руководство. Настройка служб клиентских приложений](../../../docs/framework/common-client-technologies/how-to-configure-client-application-services.md)  
 Описание использования конструктора проектов [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] для включения и настройки служб клиентских приложений,  а также описание соответствующих изменений в файле App.config.  
  
 [Практическое руководство. Реализация входа пользователя с помощью служб клиентских приложений](../../../docs/framework/common-client-technologies/how-to-implement-user-login-with-client-application-services.md)  
 Описание процедуры проверки пользователя, если в приложении настроено использование поставщика службы проверки подлинности клиента.  
  
 [Пошаговое руководство. Использование служб клиентских приложений](../../../docs/framework/common-client-technologies/walkthrough-using-client-application-services.md)  
 Описание совмещения всех функций службы клиентских приложений в одном приложении.  Это пошаговое руководство содержит подробные инструкции.  Например, в него входят инструкции по созданию приложения веб\-службы ASP.NET, которое можно использовать для тестирования служб клиентских приложений.  
  
## Ссылка  
 <xref:System.Web.ClientServices.ClientFormsIdentity>  
 <xref:System.Web.ClientServices.ClientRolePrincipal>  
 <xref:System.Web.ClientServices.ConnectivityStatus>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationCredentials>  
 <xref:System.Web.ClientServices.Providers.IClientFormsAuthenticationCredentialsProvider>  
 <xref:System.Web.ClientServices.Providers.ClientFormsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientWindowsAuthenticationMembershipProvider>  
 <xref:System.Web.ClientServices.Providers.ClientRoleProvider>  
 <xref:System.Web.ClientServices.Providers.ClientSettingsProvider>  
 <xref:System.Web.ClientServices.Providers.SettingsSavedEventArgs>  
 <xref:System.Web.ClientServices.Providers.UserValidatedEventArgs>  
  
## См. также  
 [ASP.NET Application Services Overview](../Topic/ASP.NET%20Application%20Services%20Overview.md)   
 [Using Forms Authentication with Microsoft Ajax](../Topic/Using%20Forms%20Authentication%20with%20Microsoft%20Ajax.md)   
 [Using Roles Information with Microsoft Ajax](../Topic/Using%20Roles%20Information%20with%20Microsoft%20Ajax.md)   
 [Using Profile Information with Microsoft Ajax](../Topic/Using%20Profile%20Information%20with%20Microsoft%20Ajax.md)   
 [ASP.NET Authentication](../Topic/ASP.NET%20Authentication.md)   
 [Managing Authorization Using Roles](../Topic/Managing%20Authorization%20Using%20Roles.md)   
 [OLD NIB: Managing Application Settings](http://msdn.microsoft.com/ru-ru/7de3c3bd-e0dc-4e75-a1aa-7b0ecfaac4fc)   
 [Общие сведения о параметрах приложений](../../../docs/framework/winforms/advanced/application-settings-overview.md)