---
title: Метод ICorDebugModule2::ResolveAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ResolveAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44a6596807b98e6c8b8624b5df18f78dbf8d0711
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417782"
---
# <a name="icordebugmodule2resolveassembly-method"></a>Метод ICorDebugModule2::ResolveAssembly
Разрешает сборку ссылается указанный токен метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT ResolveAssembly (  
    [in]  mdToken             tkAssemblyRef,  
    [out] ICorDebugAssembly   **ppAssembly  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `tkAsemblyRef`  
 [in] `mdToken` Значение, которое ссылается на сборку.  
  
 `ppAssembly`  
 [out] Указатель на адрес объекта ICorDebugAssembly, представляющий сборку.  
  
## <a name="remarks"></a>Примечания  
 Если сборка еще не загружен при `ResolveAssembly` вызывается HRESULT будет возвращено значение CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
