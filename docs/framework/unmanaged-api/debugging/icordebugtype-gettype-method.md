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
ms.openlocfilehash: d881a1fe3965b6e1d89e6172c887061434cd52ff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418722"
---
# <a name="icordebugtypegettype-method"></a>Метод ICorDebugType::GetType
Возвращает значение CorElementType, которое описывает собственный тип общеязыковой среды выполнения (CLR) <xref:System.Type> представленный ICorDebugType.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ty`  
 [out] Указатель на значение `CorElementType` перечисление, указывающее, среда CLR <xref:System.Type> этим `ICorDebugType` представляет.  
  
## <a name="remarks"></a>Примечания  
 Если значение `ty` ELEMENT_TYPE_CLASS или ELEMENT_TYPE_VALUETYPE, [ICorDebugType::GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) метод можно вызвать для получения типа без экземпляров универсального типа; в противном случае не следует вызывать `ICorDebugType::GetClass`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
