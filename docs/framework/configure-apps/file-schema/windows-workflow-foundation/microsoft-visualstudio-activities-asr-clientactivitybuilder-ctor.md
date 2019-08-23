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
ms.openlocfilehash: 99f2eb9447bdf43cb57cfe86f35d2c09044ed470
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947619"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a>Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
Создает экземпляр класса [Microsoft. VisualStudio. activitys. ASR. клиентактивитибуилдер](microsoft-visualstudio-activities-asr-clientactivitybuilder.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
## <a name="parameters"></a>Параметры  
  
## <a name="parameter-values"></a>Значения параметров  
 *operationDescription*  
  
 описывает операцию, выполняемую в создаваемом действии рабочего процесса. Содержит имя операции, тип возвращаемого значения и сведения о параметрах. Значение этого параметра не должно быть **равно NULL**. Он должен описывать синхронную операцию, в которой используется данный контракт сообщений и принимается аргумент с одним сообщением. Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.  
  
 *Указав*  
  
 указывает имя конфигурации конечной точки. Значение этого параметра не должно быть **null** или пустым. Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.  
  
 *проксинамеспаце*  
  
 указывает пространство имен службы для операции. Значение этого параметра не должно быть **null** или пустым. Если эти условия не выполняются, то во время выполнения результаты использования конструктора и других методов этого класса будут неопределенными.  
  
## <a name="see-also"></a>См. также

- [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
