---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
api_name: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location: Microsoft.VisualStudio.Activities.dll
api_type: Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7b73274a09ae748cdf1ee33c885de86b1f52c105
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a>Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
Создает экземпляр [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a>Параметры  
  
## <a name="parameter-values"></a>Значения параметров  
 *operationDescription*  
  
 описывает операцию, выполняемую в создаваемом действии рабочего процесса. Содержит имя операции, тип возвращаемого значения и сведения о параметрах. Значение этого параметра не должно быть **null**. Он должен описывать синхронную операцию, в которой используется данный контракт сообщений и принимается аргумент с одним сообщением. Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.  
  
 *configurationName*  
  
 указывает имя конфигурации конечной точки. Значение этого параметра не должно быть либо **null** или пустым. Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.  
  
 *proxyNamespace*  
  
 указывает пространство имен службы для операции. Значение этого параметра не должно быть либо **null** или пустым. Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.  
  
## <a name="see-also"></a>См. также  
 [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
