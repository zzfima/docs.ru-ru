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
ms.openlocfilehash: a5509dd07bbb6c812a7ea2797c46002aaa161c46
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619962"
---
# <a name="icorpublishenum-interface"></a>Интерфейс ICorPublishEnum
Служит абстрактным базовым интерфейсом для перечислителей, которые используются в публикации сведений о процессах и доменов приложений.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|Создает копию данного объекта `ICorPublishEnum` объекта.|  
|[Метод GetCount](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|Получает число элементов в перечислении.|  
|[Метод Reset](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|Перемещает курсор в начало перечисления.|  
|[Метод Skip](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|Перемещение курсора вперед в перечислении на указанное число элементов.|  
  
## <a name="remarks"></a>Примечания  
 Следующие перечислители являются производными от `ICorPublishEnum`:  
  
- [ICorPublishAppDomainEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
- [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorPub.idl, CorPub.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Кокласс CorpubPublish](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
