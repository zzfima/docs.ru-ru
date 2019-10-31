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
ms.openlocfilehash: 5f0dd814ad5adfa1b0dd7199530a3f993634a548
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121795"
---
# <a name="icorpublishenumprocesses-method"></a>Метод ICorPublish::EnumProcesses
Возвращает перечислитель для управляемых процессов, выполняющихся на этом компьютере.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `Type`  
 Значение перечисления [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) , указывающее тип получаемого процесса. В текущей версии допускается только COR_PUB_MANAGEDONLY.  
  
 `ppIEnum`  
 Указатель на адрес экземпляра [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) , который является перечислителем процессов.  
  
## <a name="remarks"></a>Заметки  
 Коллекция процессов перечислителя основана на моментальном снимке процессов, выполняемых при вызове метода `EnumProcesses`. Перечислитель не будет включать процессы, которые завершаются до или после вызова `EnumProcesses`.  
  
 Метод `EnumProcesses` может быть вызван более одного раза в этом экземпляре [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) для создания новой актуальной коллекции процессов. Последующие вызовы метода `EnumProcesses` не будут затронуты существующими коллекциями.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
