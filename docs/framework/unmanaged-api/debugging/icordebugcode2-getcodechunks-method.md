---
title: Метод ICorDebugCode2::GetCodeChunks
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84ab475ecb538dcf5bd24c750dfe9c993ea5a0ee
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470904"
---
# <a name="icordebugcode2getcodechunks-method"></a>Метод ICorDebugCode2::GetCodeChunks
Возвращает фрагменты кода, который представляет собой этого кода объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cbufSize`  
 [in] Размер `chunks` массива.  
  
 `pcnumChunks`  
 [out] Число блоков данных, возвращаемых в `chunks` массива.  
  
 `chunks`  
 [out] Массив структур «CodeChunkInfo», каждый из которых представляет отдельный блок кода. Если значение `cbufSize` равно 0, этот параметр может иметь значение null.  
  
## <a name="remarks"></a>Примечания  
 Блоки кода никогда не перекрываются, и они будет учитываться порядок, в котором они будут были объединения [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md). Объект кода промежуточного языка MSIL Microsoft в .NET Framework версии 2.0 будет состоять из одного блока кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

