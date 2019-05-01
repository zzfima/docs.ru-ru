---
title: Метод ICorDebugType::GetType
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f6b36c524921a4fecf8bc5ddcbace62af6450b6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993906"
---
# <a name="icordebugtypegettype-method"></a>Метод ICorDebugType::GetType
Получает значение CorElementType, описывающее в собственный тип общеязыковой среды выполнения (CLR) <xref:System.Type> представленный ICorDebugType.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ty`  
 [out] Указатель на значение `CorElementType` перечисление, указывающее, среда CLR <xref:System.Type> этим `ICorDebugType` представляет.  
  
## <a name="remarks"></a>Примечания  
 Если значение `ty` ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) метод может вызываться для получения типа без экземпляров универсального типа; в противном случае не вызывайте `ICorDebugType::GetClass`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
