---
title: Метод ICorDebugAppDomain3::GetCachedWinRTTypes
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type:
- apiref
ms.openlocfilehash: 55d0b40bbdb5628f60090d9d70f7dccbebe9d58f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784998"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a>Метод ICorDebugAppDomain3::GetCachedWinRTTypes
Возвращает перечислитель для всех кэшированных среда выполнения Windowsных типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a>Параметры  
 `ppGuidToTypeEnum`  
 заполняет Указатель на объект интерфейса [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md) , который может перечислить управляемые представления среда выполнения Windows типов, загруженных в домен приложения в данный момент.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** среда выполнения Windows  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugAppDomain3](icordebugappdomain3-interface.md)
