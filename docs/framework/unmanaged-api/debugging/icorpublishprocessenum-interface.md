---
title: Интерфейс ICorPublishProcessEnum
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd71a2bd4a52da8fa77592363e2eb7c8f5101fd3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423989"
---
# <a name="icorpublishprocessenum-interface"></a>Интерфейс ICorPublishProcessEnum
Подкласс [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) интерфейс, предоставляющий методы для обхода коллекцию [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) объектов.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Next](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|Возвращает заданное число `ICorPublishProcess` экземпляров из коллекции, начиная с текущей позиции.|  
  
## <a name="remarks"></a>Примечания  
 `ICorPublishProcessEnum` Интерфейс реализует методы интерфейса абстрактным, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).  
  
 `ICorPublishProcessEnum` Создан экземпляр [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) метод. Обход коллекции `ICorPublishProcess` объектов зависит от условия фильтрации, предоставленных во время `ICorPublishProcessEnum` был создан экземпляр.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorPub.idl, CorPub.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Кокласс CorpubPublish](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
