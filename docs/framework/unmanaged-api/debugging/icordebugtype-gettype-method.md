---
title: "Метод ICorDebugType::GetType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 20e2a1415d5dda9c4097d984af46942ebcf2365a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
