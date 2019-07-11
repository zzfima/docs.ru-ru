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
ms.openlocfilehash: 1804a14c1197148afbffb5ec2cb4f29cb9ff019e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774556"
---
# <a name="icorpublishenumprocesses-method"></a>Метод ICorPublish::EnumProcesses
Возвращает перечислитель для управляемых процессов, запущенных на этом компьютере.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
