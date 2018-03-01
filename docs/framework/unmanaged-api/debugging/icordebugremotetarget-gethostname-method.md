---
title: "Метод ICorDebugRemoteTarget::GetHostName"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 45fa4afebda00cb2549a5c18ba81c6bb4e8210e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugremotetargetgethostname-method"></a>Метод ICorDebugRemoteTarget::GetHostName
Возвращает полное доменное имя или IPv4-адрес удаленной отладки конечного компьютера. IPv6 не поддерживается в настоящее время.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
#### <a name="parameters"></a>Параметры  
 `cchHostName`  
 [in] Размер (в символах) для `szHostName` буфера. Если этот параметр равен 0 (нуль), `szHostName` должен иметь значение null.  
  
 `pcchHostName`  
 [out] Число символов, включая знак завершения null, имя узла или IP-адрес. Этот параметр может быть нулевым.  
  
 `szHostName`  
 [out] Буфер, содержащий имя узла или IP-адрес.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Имя узла или IP-адрес был успешно возвращен.  
  
 E_FAIL (или другие коды возврата E_)  
 Не удалось вернуть имя узла или IP-адрес.  
  
## <a name="remarks"></a>Примечания  
 Этот метод реализуется модулем записи отладчика. Он должен соответствовать несколько вызовов парадигма: при первом вызове вызывающий объект передает значение null как `cchHostName` и `szHostName`, и `pcchHostName` возвращает размер буфера. При втором вызове переданный размер, который ранее был возвращен `cchHostName`, и переданный буфер соответствующего размера `szHostName`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** 3.5 SP1  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
