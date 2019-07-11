---
title: Метод ICorDebugVariableHome::GetRegister
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4b3b80546095b79dc5b551a9c5e92ec15c0dddb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771786"
---
# <a name="icordebugvariablehomegetregister-method"></a>Метод ICorDebugVariableHome::GetRegister
Получает регистр, который содержит переменную с типом расположения `VLT_REGISTER`и базовым регистром для переменной с типом расположения `VLT_REGISTER_RELATIVE`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pRegister`  
 [out] CorDebugRegister значение перечисления, указывающее регистра для переменной с типом расположения `VLT_REGISTER`и базовым регистром для переменной с типом расположения `VLT_REGISTER_RELATIVE`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Метод возвращает следующие значения:  
  
|Значение|Описание|  
|-----------|-----------------|  
|`S_OK`|Переменная находится в регистре, обозначается `pRegister` аргумент.|  
|`E_FAIL`|Переменная не в регистр или в папку, зависящий от регистра.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
- [Интерфейс ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
