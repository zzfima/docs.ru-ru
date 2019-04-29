---
title: Метод ICorDebugRemoteTarget::GetHostName
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ca7aee79b5b8c3d58b4beb8f1ff886a7d55afab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782711"
---
# <a name="icordebugremotetargetgethostname-method"></a>Метод ICorDebugRemoteTarget::GetHostName
Возвращает полное доменное имя или IPv4-адрес удаленной отладки целевой машины. IPv6 не поддерживается в настоящее время.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a>Параметры  
 `cchHostName`  
 [in] Размер в символах, из `szHostName` буфера. Если этот параметр равен 0 (ноль), `szHostName` должен иметь значение null.  
  
 `pcchHostName`  
 [out] Число символов, включая завершающий нуль-символ, имя узла или IP-адрес. Этот параметр может быть нулевым.  
  
 `szHostName`  
 [out] Буфер, содержащий имя узла или IP-адрес.  
  
## <a name="return-value"></a>Возвращаемое значение  
 S_OK  
 Имя узла или IP-адрес был успешно возвращен.  
  
 E_FAIL (или другие коды возврата E_)  
 Не удалось получить имя узла или IP-адрес.  
  
## <a name="remarks"></a>Примечания  
 Этот метод реализуется модулем записи отладчика. Он должен соответствовать несколько парадигма вызова: При первом вызове, вызывающий объект передает null в оба `cchHostName` и `szHostName`, и `pcchHostName` возвращает размер буфера. При втором вызове, переданный размер, который был ранее возвращен `cchHostName`, и переданный буфера `szHostName`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugRemoteTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [Интерфейс ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
