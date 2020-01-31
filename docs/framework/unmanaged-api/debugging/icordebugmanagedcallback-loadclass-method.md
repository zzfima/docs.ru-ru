---
title: Метод ICorDebugManagedCallback::LoadClass
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
ms.openlocfilehash: cc5a2e1de79d6ba04ff3bf2bf86e0cb7ce9a5c0b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788378"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a>Метод ICorDebugManagedCallback::LoadClass
Уведомляет отладчик о том, что класс был загружен.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pAppDomain`  
 окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в который был загружен класс.  
  
 `c`  
 окне Указатель на объект ICorDebugClass, представляющий класс.  
  
## <a name="remarks"></a>Заметки  
 Этот обратный вызов происходит, только если для модуля, содержащего класс, была включена загрузка класса. Загрузка класса всегда включена для динамических модулей.  
  
 Обратный вызов `LoadClass` предоставляет соответствующее время для привязки точек останова к вновь созданным классам в динамических модулях.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Метод UnloadClass](icordebugmanagedcallback-unloadclass-method.md)
- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
