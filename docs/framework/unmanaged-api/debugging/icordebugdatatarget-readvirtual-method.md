---
title: Метод ICorDebugDataTarget::ReadVirtual
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.ReadVirtual Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::ReadVirtual
helpviewer_keywords:
- ICorDebugDataTarget::ReadVirtual method [.NET Framework debugging]
- ReadVirtual method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: 55e57640-b3d2-413d-b4f4-fbc27fb8e37c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d9e619e4176633074242521133d42f191f140ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugdatatargetreadvirtual-method"></a>Метод ICorDebugDataTarget::ReadVirtual
Получает блок непрерывной памяти, начиная с указанного адреса и возвращает его в указанный буфер.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ReadVirtual(  
    [in] CORDB_ADDRESS   address,  
    [out, size_is(bytesRequested), length_is(*pBytesRead)]  
          BYTE *     pBuffer,  
    [in]  ULONG32    bytesRequested,  
    [out] ULONG32 *  pBytesRead);  
```  
  
#### <a name="parameters"></a>Параметры  
 `address`  
 [in] Начальный адрес запрошенный объем памяти.  
  
 `pbuffer`  
 [out] Буфер, где будет храниться в памяти.  
  
 `bytesRequested`  
 [in] Число байтов для получения из целевой адрес.  
  
 `pBytesRead`  
 [out] Число фактически считанных байтов из целевой адрес. Это может быть меньше, чем `bytesRequested`.  
  
## <a name="remarks"></a>Примечания  
 Если можно прочитать первый байт (по указанному начальному адресу), вызов возвращает успешный результат (для поддержки эффективного чтения структур данных с самоописанием длину, например строки с завершающим нулем).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
