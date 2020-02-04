---
title: Метод ICorDebugLoadedModule::GetName
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
ms.openlocfilehash: 628f85f3045533ead7ace47b11573a0b1a46df46
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782051"
---
# <a name="icordebugloadedmodulegetname-method"></a>Метод ICorDebugLoadedModule::GetName
Получает имя загруженного модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cchName`  
 [in] Число символов в буфере `szName`.  
  
 `pcchName`  
 [out] Указатель на число символов, фактически записанных в буфер `szName`.  
  
 `szName`  
 [out] Массив символов, содержащий имя загруженного модуля.  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugLoadedModule](icordebugloadedmodule-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
