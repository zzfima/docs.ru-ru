---
title: Метод IDebugAutoAttach::AutoAttach
ms.date: 03/30/2017
api_name:
- IDebugAutoAttach.AutoAttach
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IDebugAutoAttach::AutoAttach
helpviewer_keywords:
- AutoAttach method [.NET Framework debugging]
- IDebugAutoAttach::AutoAttach method [.NET Framework debugging]
ms.assetid: 3cf3bd9c-7d88-4afa-a476-94cdc7609aa6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16ccc56579a1ebe45ada61a9565cc8ade335333d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469682"
---
# <a name="idebugautoattachautoattach-method"></a>Метод IDebugAutoAttach::AutoAttach
Выполняет отладчика, вызываемого сервером автоматического присоединения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT AutoAttach  
(  
    [in]  REFGUID   guidPort,  
    [in]  DWORD     dwPid,  
    [in]  AUTOATTACH_PROGRAM_TYPE dwProgramType,  
    [in]  DWORD     dwProgramId,  
    [in]  LPCWSTR   pszSessionId  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `guidPort`  
 [in] Всегда значение `GUID_NULL`.  
  
 `dwPid`  
 [in] Идентификатор процесса, как правило, извлекается с `GetCurrentProcessId` функции.  
  
 `dwProgramType`  
 [in] Тип программы: `AUTOATTACH_PROGRAM_WIN32`, `AUTOATTACH_PROGRAM_COMPLUS`, или `AUTOATTACH_PROGRAM_UNKNOWN`.  
  
 `dwProgramId`  
 [in] Идентификатор программы.  
  
 `pszSessionId`  
 [in] Строка, переданная команду debug.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если метод выполнен успешно.  
  
## <a name="requirements"></a>Требования  
 **Заголовок.** DbgAutoAttach.h  
  
## <a name="see-also"></a>См. также
- [Интерфейс IDebugAutoAttach](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)
