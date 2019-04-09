---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.date: 03/30/2017
ms.topic: reference
api_name:
- Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location:
- Microsoft.VisualStudio.Activities.dll
api_type:
- Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
ms.openlocfilehash: 0ce9be30182f9181bcb6449529d9b9796aadbc2b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133540"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a>Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
Создает экземпляр класса [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
## <a name="parameters"></a>Параметры  
  
## <a name="parameter-values"></a>Значения параметров  
 *operationDescription*  
  
 описывает операцию, выполняемую в создаваемом действии рабочего процесса. Содержит имя операции, тип возвращаемого значения и сведения о параметрах. Значение этого параметра не должно быть **null**. Он должен описывать синхронную операцию, в которой используется данный контракт сообщений и принимается аргумент с одним сообщением. Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.  
  
 *configurationName*  
  
 указывает имя конфигурации конечной точки. Значение этого параметра не должно быть либо **null** или пустым. Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.  
  
 *proxyNamespace*  
  
 указывает пространство имен службы для операции. Значение этого параметра не должно быть либо **null** или пустым. Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.  
  
## <a name="see-also"></a>См. также

- [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
