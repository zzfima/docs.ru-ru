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
ms.openlocfilehash: 2b19efdedc21f66e4692ce1850eb3947f856e436
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083755"
---
# <a name="icordebugtype2gettypeid-method"></a>Метод ICorDebugType2::GetTypeID
Получает [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) для этого типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `id`  
 [out] Указатель на [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) для ICorDebugType.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое. `HRESULT` Коды включают следующее:  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|`S_OK`|Метод успешно выполнен. Метод получил допустимый [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).|  
|`CORDBG_E_CLASS_NOT_LOADED`|Тип не был загружен.|  
|`CORDBG_E_UNSUPPORTED`|Тип не поддерживается.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод обеспечивает сопоставление ICorDebugType, который представляет тип, который может или может не были загружены в среду выполнения до [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), который служит непрозрачным обработки, который определяет тип, загруженной в среду.  
  
 Если тип, представляющий ICorDebugType еще не загружена, этот метод возвращает `CORDBG_E_CLASS_NOT_LOADED`.  Если тип не поддерживается, возвращается `CORDBG_E_UNSUPPORTED`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugType2](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)
