---
title: "Developing Windows Service Applications | Microsoft Docs"
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
  - "ServiceInstaller class, Windows Service applications"
  - "Service class, Windows Service applications"
  - "Windows Service applications"
  - "Windows NT services"
  - "ServiceProcessInstaller class, Windows Service applications"
  - "services"
  - ".NET applications, Windows applications"
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
caps.latest.revision: 18
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 18
---
# Developing Windows Service Applications
Используя [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] или пакет Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, можно создавать службы, разрабатывая приложения, которые устанавливаются как службы.  Такие приложения называются службами Windows.  Используя компоненты платформы, можно создавать и устанавливать службы, а также управлять ими.  
  
> [!WARNING]
>  Шаблон службы Windows для C\+\+ не был включен в Visual Studio 2010.  Чтобы создать службу Windows, можно создать службу в управляемом коде на visual C\# или Visual Basic, которое может взаимодействовать с существующим кодом C\+\+, если это требуется или можно создать службу Windows в собственном C\+\+ с помощью [мастер проектов ATL](../Topic/ATL%20Project%20Wizard.md).  
  
## В этом подразделе  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 Обзор служб Windows, время существования службы, и как приложения службы, отличаются от других стандартных типов проектов.  
  
 [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 Пример создания службы в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] и Visual C\#.  
  
 [Service Application Programming Architecture](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 Описание элементов языка, используемых при создании служб.  
  
 [How to: Create Windows Services](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 Описывает процесс создания и настройки службы Windows с помощью шаблона проекта службы Windows.  
  
## Связанные подразделы  
 <xref:System.ServiceProcess.ServiceBase>  
 Описание основных возможностей класса <xref:System.ServiceProcess.ServiceBase>, используемого для создания служб.  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 Описание возможностей класса <xref:System.ServiceProcess.ServiceProcessInstaller>, используемого совместно с классом <xref:System.ServiceProcess.ServiceInstaller> для установки и удаления служб.  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 Описание возможностей класса <xref:System.ServiceProcess.ServiceInstaller>, используемого совместно с классом <xref:System.ServiceProcess.ServiceProcessInstaller> для установки и удаления служб.  
  
 [Создание проектов с помощью шаблонов](http://msdn.microsoft.com/ru-ru/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 Описание типов проектов, используемых в данном разделе, и различий между ними.