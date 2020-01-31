---
title: Метод ICorDebugRegisterSet2::GetRegisters
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type:
- apiref
ms.openlocfilehash: 54a5fb50a0177fe9886582c112f16ce871ea9df4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792063"
---
# <a name="icordebugregisterset2getregisters-method"></a>Метод ICorDebugRegisterSet2::GetRegisters
Возвращает значение каждого регистра (для платформы, в которой код выполняется в данный момент), заданный заданной битовой маской.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `maskCount`  
 окне Размер массива `mask` в байтах.  
  
 `mask`  
 окне Массив байтов, каждый бит которого соответствует регистру. Если бит равен 1, будет получено соответствующее значение регистра.  
  
 `regCount`  
 окне Число возвращаемых значений регистров.  
  
 `regBuffer`  
 заполняет Массив объектов `CORDB_REGISTER`, каждый из которых получает значение регистра.  
  
## <a name="remarks"></a>Заметки  
 Метод `GetRegisters` возвращает массив значений из регистров, заданных маской. Массив не содержит значений регистров, бит маски которых не задан. Таким же размером массив `regBuffer` должен быть равен количеству 1 в маске. Если значение `regCount` слишком мало для количества регистров, указанных маской, значения более высоких регистров будут обрезаны из набора. Если `regCount` слишком большой, неиспользуемые элементы `regBuffer` будут неизменными.  
  
 Если недоступная ККМ обозначается маской, для этой регистрации будет возвращено неопределенное значение.  
  
 Метод `ICorDebugRegisterSet2::GetRegisters` необходим для платформ, имеющих более 64 регистров. Например, IA64 имеет 128 регистров общего назначения и 128 регистров с плавающей запятой, поэтому в битовой маске требуется более 64 бит.  
  
 Если у вас больше 64 регистров, как в случае с такими платформами, как x86, метод `GetRegisters` фактически просто преобразует байты в `mask` массиве байтов в `ULONG64`, а затем вызывает метод [ICorDebugRegisterSet::](icordebugregisterset-getregisters-method.md) GetBytes, который принимает маску `ULONG64`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugRegisterSet2](icordebugregisterset2-interface.md)
- [Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)
