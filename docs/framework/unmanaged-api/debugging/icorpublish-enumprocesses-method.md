---
title: Метод ICorPublish::EnumProcesses
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb4096b0ae083e0b6c0598ea18cc8b33c2fdfe3e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116299"
---
# <a name="icorpublishenumprocesses-method"></a>Метод ICorPublish::EnumProcesses
Возвращает перечислитель для управляемых процессов, запущенных на этом компьютере.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `Type`  
 Значение [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) перечисление, указывающее тип процесса требуется получить. В текущей версии только COR_PUB_MANAGEDONLY является допустимым.  
  
 `ppIEnum`  
 Указатель на адрес [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) экземпляр, который является перечислителем процессов.  
  
## <a name="remarks"></a>Примечания  
 Перечислитель коллекции процессов основан на моментальный снимок процессов, которые выполняются при `EnumProcesses` вызывается метод. Перечислитель не будет включать все процессы, прежде чем или запустить после `EnumProcesses` вызывается.  
  
 `EnumProcesses` Метод может вызываться несколько раз на этом [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) экземпляра для создания новой актуальной коллекции процессов. Существующие коллекции не будут затронуты, последующие вызовы `EnumProcesses` метод.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorPub.idl, CorPub.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
