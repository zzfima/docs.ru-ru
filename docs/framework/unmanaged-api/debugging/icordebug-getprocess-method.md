---
title: Метод ICorDebug::GetProcess
ms.date: 03/30/2017
api_name:
- ICorDebug.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::GetProcess method [.NET Framework debugging]
ms.assetid: 10a40ba0-1b65-4721-bd11-cf12d57b280d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dcb869bed71be05e0450580b50dfa9f2a0fca525
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169797"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="c792b-102">Метод ICorDebug::GetProcess</span><span class="sxs-lookup"><span data-stu-id="c792b-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="c792b-103">Получает указатель на экземпляр «ICorDebugProcess» для указанного процесса.</span><span class="sxs-lookup"><span data-stu-id="c792b-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c792b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c792b-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c792b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c792b-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="c792b-106">[in] Идентификатор процесса.</span><span class="sxs-lookup"><span data-stu-id="c792b-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="c792b-107">[out] Указатель на адрес `ICorDebugProcess` экземпляра для указанного процесса.</span><span class="sxs-lookup"><span data-stu-id="c792b-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c792b-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c792b-108">Requirements</span></span>  
 <span data-ttu-id="c792b-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c792b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c792b-110">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c792b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c792b-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c792b-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c792b-112">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c792b-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c792b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c792b-113">See also</span></span>

- [<span data-ttu-id="c792b-114">Интерфейс ICorDebug</span><span class="sxs-lookup"><span data-stu-id="c792b-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
