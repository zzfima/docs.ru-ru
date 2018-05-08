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
ms.openlocfilehash: e06c98067fea9368ac8f750d9187636d2ca9a8c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugvariablehomegetregister-method"></a>Метод ICorDebugVariableHome::GetRegister
Возвращает регистра, который содержит переменную с типом расположения `VLT_REGISTER`и базовым регистром для переменной с типом расположения `VLT_REGISTER_RELATIVE`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pRegister`  
 [out] CorDebugRegister значение перечисления, указывающее register для переменной с типом расположения `VLT_REGISTER`и базовым регистром для переменной с типом расположения `VLT_REGISTER_RELATIVE`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Метод возвращает следующие значения:  
  
|Значение|Описание|  
|-----------|-----------------|  
|`S_OK`|Переменная находится в регистре, обозначенном `pRegister` аргумент.|  
|`E_FAIL`|Переменная не находится в регистрах или расположение относительно регистра.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Перечисление VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)  
 [Интерфейс ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
