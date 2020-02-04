---
title: Метод ICorDebugDataTarget3::GetLoadedModules
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
ms.openlocfilehash: d4c22146422085daa4dc9d90ae5b3735a12500c2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793555"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a>Метод ICorDebugDataTarget3::GetLoadedModules
Возвращает список модулей, загруженных на данный момент.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cRequestedModules`  
 [in] Число модулей, для которых запрашиваются сведения.  
  
 `pcFetchedModules`  
 [out] Указатель на число модулей, о которых возвращаются сведения.  
  
 `pLoadedModules`  
 заполняет Указатель на массив объектов [икордебуглоадедмодуле](icordebugloadedmodule-interface.md) , которые предоставляют сведения о загруженных модулях.  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugDataTarget3](icordebugdatatarget3-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
