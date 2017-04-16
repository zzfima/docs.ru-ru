---
title: "Troubleshooting: Service Application Won&#39;t Install | Microsoft Docs"
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
  - "troubleshooting service applications"
  - "services, troubleshooting"
  - "services, debugging"
  - "Windows NT services, troubleshooting"
  - "troubleshooting NT services"
  - "Windows Service applications, troubleshooting"
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 8
---
# Troubleshooting: Service Application Won&#39;t Install
Если приложение службы не устанавливается должным образом, следует убедиться, что свойству <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> класса службы присвоено то же самое значение, которое указано в установщике этой службы.  Для правильной установки службы необходимо, чтобы это значение было одинаковым в обоих случаях.  
  
> [!NOTE]
>  Для получения сведений о ходе процесса установки можно также просмотреть журналы установки.  
  
 Необходимо также проверить, не установлена ли уже другая служба с таким же именем.  Имена служб должны быть уникальными.  
  
## См. также  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)