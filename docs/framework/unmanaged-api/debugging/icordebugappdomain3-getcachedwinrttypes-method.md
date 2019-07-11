---
title: Метод ICorDebugAppDomain3::GetCachedWinRTTypes
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ba981d86f90af449820ce13aa847169ca877429
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737771"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="78f97-102">Метод ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="78f97-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="78f97-103">Получает перечислитель для всех кэшированных типов среды выполнения Windows.</span><span class="sxs-lookup"><span data-stu-id="78f97-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78f97-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78f97-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="78f97-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="78f97-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="78f97-106">[out] Указатель на [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) объект интерфейса, который можно перечислить представления управляемых типов среды выполнения Windows в настоящее время загружен в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="78f97-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78f97-107">Требования</span><span class="sxs-lookup"><span data-stu-id="78f97-107">Requirements</span></span>  
 <span data-ttu-id="78f97-108">**Платформы:** Среда выполнения Windows</span><span class="sxs-lookup"><span data-stu-id="78f97-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="78f97-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78f97-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78f97-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78f97-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78f97-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78f97-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78f97-112">См. также</span><span class="sxs-lookup"><span data-stu-id="78f97-112">See also</span></span>

- [<span data-ttu-id="78f97-113">Интерфейс ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="78f97-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
