---
title: "Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: 
  - "Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor"
apilocation: 
  - "Microsoft.VisualStudio.Activities.dll"
apitype: "Assembly"
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
Создает экземпляр класса [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md).  
  
## Синтаксис  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
  
```  
  
#### Параметры  
  
## Значения параметров  
 *operationDescription*  
  
 описывает операцию, выполняемую в создаваемом действии рабочего процесса. Содержит имя операции, тип возвращаемого значения и сведения о параметрах.  Значение этого параметра не должно быть равно **null**.  Он должен описывать синхронную операцию, в которой используется данный контракт сообщений и принимается аргумент с одним сообщением.  Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.  
  
 *configurationName*  
  
 указывает имя конфигурации конечной точки.  Значение этого параметра не должно быть равно **null** или быть пустым.  Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.  
  
 *proxyNamespace*  
  
 указывает пространство имен службы для операции.  Значение этого параметра не должно быть равно **null** или быть пустым.  Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.  
  
## См. также  
 [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)