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
ms.openlocfilehash: f8e92ec4f813e8810273a1514298d0739a3d2406
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179062"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a>Метод ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
Получает регистратор для кэшированных типов Windows Runtime в домене приложения на основе идентификаторов интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cReqTypes`  
 (в) Количество требуемых типов.  
  
 `iidsToResolve`  
 (в) Указатель массива, содержащего идентификаторы интерфейса, соответствующие управляемым представлениям типов Windows Runtime, которые должны быть извлечены.  
  
 `ppTypesEnum`  
 (ваут) Указатель на адрес объекта интерфейса "ICorDebugTypeEnum", позволяющий перечислять извлеченные кэшированные управляемые представления извлеченных типов Windows `iidsToResolve`Runtime на основе идентификаторов интерфейса.  
  
## <a name="remarks"></a>Remarks  
 Если метод не может получить информацию для конкретного идентификатора интерфейса, соответствующая запись в `ELEMENT_TYPE_END` коллекции "ICorDebugTypeEnum" будет иметь тип для ошибок из-за проблем с поиском данных или `ELEMENT_TYPE_VOID` для неизвестных идентификаторов интерфейса.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** Время выполнения Windows  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugAppDomain3](icordebugappdomain3-interface.md)
