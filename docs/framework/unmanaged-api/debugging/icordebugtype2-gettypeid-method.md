---
title: Метод ICorDebugType2::GetTypeID
ms.date: 03/30/2017
api_name:
- ICorDebugType2.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bc1407f8444b78154981619742bd0da188c4335
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422075"
---
# <a name="icordebugtype2gettypeid-method"></a>Метод ICorDebugType2::GetTypeID
Возвращает [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) для этого типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `id`  
 [out] Указатель на [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) для ICorDebugType.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое. `HRESULT` Коды включают следующее:  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|`S_OK`|Метод успешно выполнен. Метод извлеченные является допустимым [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).|  
|`CORDBG_E_CLASS_NOT_LOADED`|Тип не был загружен.|  
|`CORDBG_E_UNSUPPORTED`|Тип не поддерживается.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод обеспечивает сопоставление из ICorDebugType, который представляет тип, который может быть или могут не быть загружены в среду выполнения с [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), который служит непрозрачный дескриптор, определяет тип, загружена в среду выполнения.  
  
 Если тип, представляющий ICorDebugType еще не были загружены, этот метод возвращает `CORDBG_E_CLASS_NOT_LOADED`.  Если тип не поддерживается, возвращается `CORDBG_E_UNSUPPORTED`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugType2](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)
