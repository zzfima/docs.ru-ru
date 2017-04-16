---
title: "Настройка приложения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a2f995b0-669d-4721-b00f-4561ec7eb6a4
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Настройка приложения
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] использует систему конфигурации .NET и позволяет настраивать службы и на компьютере, и в области приложений.  
  
 Параметры конфигурации, определяемые [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], находятся в группе разделов `<system.serviceModel>`.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о том, как настроить службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], см. в следующих разделах:  
  
-   [Настройка служб](../../../../docs/framework/wcf/configuring-services.md)  
  
-   [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)  
  
 Определяемые приложением параметры конфигурации определяются в группе разделов `<appSettings>`.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о параметрах приложения в файлах конфигурации .NET см. в разделе [\<appSettings\>](http://go.microsoft.com/fwlink/?LinkId=95159).  
  
## Использование редактора конфигураций  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] [Средство редактирования конфигурации \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) позволяет администраторам и разработчикам создавать и изменять параметры конфигурации служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], используя графический интерфейс пользователя.С помощью этого средства можно управлять параметрами привязок, поведений, служб и диагностики [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] без непосредственного изменения XML\-файлов конфигурации.  
  
## Изменение файлов конфигурации в Visual Studio  
 Чтобы изменить файл конфигурации проекта службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], щелкните по нему правой кнопкой мыши в **Обозревателе решений** и выберите в контекстном меню пункт **Изменить конфигурацию WCF**.Запустится [Средство редактирования конфигурации \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
> [!NOTE]
>  При изменении файла конфигурации проекта веб\-службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] путем нажатия по нему правой кнопкой мыши в **Обозревателе решений** обратите внимание, что в контекстном меню отсутствует пункт **Изменить конфигурацию WCF**.Чтобы обойти эту проблему, в меню **Средства** выберите **Редактор конфигураций служб WCF**.Затем щелкните правой кнопкой мыши файл конфигурации и выберите в контекстном меню пункт **Изменить конфигурацию WCF**.  
  
## См. также  
 [Средство редактирования конфигурации \(SvcConfigEditor.exe\)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md)   
 [Настройка служб](../../../../docs/framework/wcf/configuring-services.md)   
 [\<system.serviceModel\>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)