---
title: Экземпляры
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: 668cfb3026b9ab7259665f5e53873a512b1e2238
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118993"
---
# <a name="instances"></a>Экземпляры
Имя счетчика: экземпляры.  
  
## <a name="description"></a>Описание  
 Число контекстов экземпляра, которое в настоящий момент содержит служба.  
  
 В большинстве случаев число контекстов экземпляра идентично числу экземпляров. Однако приведенные ниже сценарии являются исключением из этого правила.  
  
-   Метод службы явным образом вызывает метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>.  
  
-   <xref:System.ServiceModel.ReleaseInstanceMode> применяется к экземпляру <xref:System.ServiceModel.OperationBehaviorAttribute>.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.OperationBehaviorAttribute>
