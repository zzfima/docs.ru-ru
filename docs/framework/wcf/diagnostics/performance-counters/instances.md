---
title: "Экземпляры | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Экземпляры
Имя счетчика: Instances.  
  
## Описание  
 Число контекстов экземпляра, которое в настоящий момент содержит служба.  
  
 В большинстве случаев число контекстов экземпляра идентично числу экземпляров.  Однако приведенные ниже сценарии являются исключением из этого правила.  
  
-   Метод службы явным образом вызывает метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>.  
  
-   <xref:System.ServiceModel.ReleaseInstanceMode> применяется к экземпляру <xref:System.ServiceModel.OperationBehaviorAttribute>.  
  
## См. также  
 <xref:System.ServiceModel.OperationBehaviorAttribute>