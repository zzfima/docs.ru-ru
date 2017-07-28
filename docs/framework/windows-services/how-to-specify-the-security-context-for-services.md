---
title: "How to: Specify the Security Context for Services | Microsoft Docs"
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
  - "Windows Service applications, security"
  - "security [Visual Studio], contexts"
  - "contexts, Visual Studio security"
  - "security [Visual Studio], service applications"
  - "ServiceProcessInstaller class, security context"
  - "services, security"
  - "ServiceInstaller class, security context"
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 10
---
# How to: Specify the Security Context for Services
По умолчанию службы Windows выполняются в отдельном контексте безопасности, отличном от контекста безопасности вошедшего пользователя.  Службы запускаются в контексте системной учетной записи по умолчанию, называемой `LocalSystem`, что дает им права доступа к системным ресурсам, отличающиеся от прав доступа для пользователя.  Чтобы это изменить, можно указать учетную запись пользователя, от имени которой будет запускаться служба.  
  
 Контекст безопасности задается путем изменения значения свойства <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> процесса, в котором выполняется служба.  Это свойство позволяет запускать службу от имени четырех типов учетных записей:  
  
-   `User` — при установке службы система запрашивает имя и пароль существующего пользователя. Служба будет запускаться от имени учетной записи этого пользователя.  
  
-   `LocalService` — служба выполняется в контексте учетной записи, аналогичной учетной записи непривилегированного пользователя текущего компьютера. Удаленным серверам при этом передаются учетные данные анонимного пользователя.  
  
-   `LocalSystem`, который выполняется в контексте учетной записи, которая предоставляет широкие локальные привилегии и представляет учетные данные компьютера к любому удаленному серверу;  
  
-   `NetworkService` — служба выполняется в контексте учетной записи, аналогичной учетной записи непривилегированного пользователя текущего компьютера. Удаленным серверам при этом передаются учетные данные этого компьютера.  
  
 Дополнительные сведения см. в разделе <xref:System.ServiceProcess.ServiceAccount>.  
  
### Чтобы указать контекст безопасности для службы, выполните следующие действия:  
  
1.  После создания службы добавьте в нее необходимые установщики.  Дополнительные сведения см. в разделе [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
2.  Выберите в конструкторе класс службы `ProjectInstaller` и щелкните установщик процессов службы.  
  
    > [!NOTE]
    >  У любого приложения службы класс `ProjectInstaller` содержит по меньшей мере два установочных компонента — компонент, устанавливающий процессы для всех служб в проекте, и установщик для каждой службы, содержащейся в приложении.  В этом случае следует выбрать <xref:System.ServiceProcess.ServiceProcessInstaller>.  
  
3.  В окне **Свойства** задайте соответствующее значение свойства <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A>.  
  
## См. также  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)   
 [How to: Create Windows Services](../../../docs/framework/windows-services/how-to-create-windows-services.md)