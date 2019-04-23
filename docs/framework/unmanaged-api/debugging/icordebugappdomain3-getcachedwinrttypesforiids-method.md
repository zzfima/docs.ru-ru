---
title: Метод ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed1d7ad95b7c8474121994d0f54557c1c36cb531
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59095130"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>Метод ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
Получает перечислитель для кэшированных [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типов в домене приложения, по их идентификаторам интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cReqTypes`  
 [in] Количество требуемых типов.  
  
 `iidsToResolve`  
 [in] Указатель на массив, содержащий идентификаторы интерфейса, соответствующие управляемые представления [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типы должны быть получены.  
  
 `ppTypesEnum`  
 [out] Указатель на адрес объекта интерфейса «ICorDebugTypeEnum», который позволяет использовать кэшированный перечисления управляемых представлений [!INCLUDE[wrt](../../../../includes/wrt-md.md)] типы, полученные на основе идентификаторов интерфейса в `iidsToResolve`.  
  
## <a name="remarks"></a>Примечания  
 При сбое метода для получения сведений для определенного интерфейса идентификатора, соответствующая запись в коллекции «ICorDebugTypeEnum» будет иметь тип `ELEMENT_TYPE_END` ошибок из-за проблем извлечения данных, или `ELEMENT_TYPE_VOID` для Неизвестный интерфейс идентификаторы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugAppDomain3](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
