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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aca83a66520531074f376a47a7f2994cda237f9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423238"
---
# <a name="icordebugregisterset2getregisters-method"></a>Метод ICorDebugRegisterSet2::GetRegisters
Получает значение каждого регистра (для платформы, на котором в данный момент выполняется код), указанное данной битовой маской.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `maskCount`  
 [in] Размер в байтах для `mask` массива.  
  
 `mask`  
 [in] Массив байтов, из которых каждый бит соответствует регистру. Если бит равен 1, будет получен соответствующего регистра.  
  
 `regCount`  
 [in] Количество значений регистра требуется получить.  
  
 `regBuffer`  
 [out] Массив `CORDB_REGISTER` объектов, каждый из которых получает значение регистра.  
  
## <a name="remarks"></a>Примечания  
 `GetRegisters` Метод возвращает массив значений из регистров, указанных маской. Массив не содержит значения, регистров, маска которых не задано. Таким образом, размер `regBuffer` массива должен быть равен количеству 1 в маске. Если значение `regCount` слишком мал для число регистрами, указанными в маске значения регистры с более будут отброшены из набора. Если `regCount` слишком велико, неиспользуемые `regBuffer` элементы будут изменены.  
  
 Если недоступный регистр указывается маской, для данного регистра возвращается неопределенное значение.  
  
 `ICorDebugRegisterSet2::GetRegisters` Метод необходим для платформ, имеющих более 64 регистров. Например IA64 имеет 128 регистров общего назначения и 128 регистров с плавающей запятой, поэтому необходимо больше 64 бита в битовой маске.  
  
 Если у вас более 64 регистров, как в случае на платформах, например x86, `GetRegisters` метод фактически переводит байты в `mask` массив байтов, в `ULONG64` , а затем вызывает [ICorDebugRegisterSet:: GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) метод, который принимает `ULONG64` маски.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugRegisterSet2](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [Интерфейс ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
