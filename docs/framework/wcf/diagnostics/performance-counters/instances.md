---
title: Экземпляры
ms.date: 03/30/2017
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
ms.openlocfilehash: e0be9c93b5efe17235dbccd426cdd73fbb739361
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651837"
---
# <a name="instances"></a>Экземпляры
Имя счетчика: экземпляры.  
  
## <a name="description"></a>Описание  
 Число контекстов экземпляра, которое в настоящий момент содержит служба.  
  
 В большинстве случаев число контекстов экземпляра идентично числу экземпляров. Однако приведенные ниже сценарии являются исключением из этого правила.  
  
- Метод службы явным образом вызывает метод <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>.  
  
- <xref:System.ServiceModel.ReleaseInstanceMode> применяется к экземпляру <xref:System.ServiceModel.OperationBehaviorAttribute>.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.OperationBehaviorAttribute>
