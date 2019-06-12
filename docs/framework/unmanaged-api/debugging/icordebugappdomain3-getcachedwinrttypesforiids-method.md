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
ms.openlocfilehash: 95c84f7f40db0096b26ec448f8f229cdbfe3afb1
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025904"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>Метод ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
Возвращает перечислитель для кэшированных типов среды выполнения Windows в домене приложения, на основе их идентификаторов интерфейса.  
  
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
 [in] Указатель на массив, содержащий идентификаторы интерфейса, соответствующие управляемые представления типов среды выполнения Windows требуется получить.  
  
 `ppTypesEnum`  
 [out] Получить указатель на адрес объекта интерфейса «ICorDebugTypeEnum», который позволяет использовать перечисления кэшированного представления управляемых типов среды выполнения Windows, на основе идентификаторов интерфейса в `iidsToResolve`.  
  
## <a name="remarks"></a>Примечания  
 При сбое метода для получения сведений для определенного интерфейса идентификатора, соответствующая запись в коллекции «ICorDebugTypeEnum» будет иметь тип `ELEMENT_TYPE_END` ошибок из-за проблем извлечения данных, или `ELEMENT_TYPE_VOID` для Неизвестный интерфейс идентификаторы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** Среда выполнения Windows  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugAppDomain3](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
