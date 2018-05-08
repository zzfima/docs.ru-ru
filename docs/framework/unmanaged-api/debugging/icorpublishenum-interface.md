---
title: Интерфейс ICorPublishEnum
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b3536184fa7798ac8eabe851221ec692c126460b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icorpublishenum-interface"></a>Интерфейс ICorPublishEnum
Служит абстрактным базовым интерфейсом для перечислителей, которые используются в публикации сведений о процессах и доменах приложения.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|Создает копию объекта `ICorPublishEnum` объекта.|  
|[Метод GetCount](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|Получает число элементов в перечислении.|  
|[Метод Reset](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|Перемещает курсор в начало перечисления.|  
|[Метод Skip](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|Перемещение курсора вперед в перечислении указанное число элементов.|  
  
## <a name="remarks"></a>Примечания  
 Следующие перечислители являются производными от `ICorPublishEnum`:  
  
-   [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorPub.idl, CorPub.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Кокласс CorpubPublish](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
