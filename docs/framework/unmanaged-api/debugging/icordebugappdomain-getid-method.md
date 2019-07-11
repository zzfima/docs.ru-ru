---
title: Метод ICorDebugAppDomain::GetId
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetId
helpviewer_keywords:
- GetId method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetId method [.NET Framework debugging]
ms.assetid: 32c27576-71fa-42ee-8230-67b92913ea08
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb8917fa401db9424cff168fe0b06ad84065827c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737939"
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="d76e4-102">Метод ICorDebugAppDomain::GetId</span><span class="sxs-lookup"><span data-stu-id="d76e4-102">ICorDebugAppDomain::GetId Method</span></span>
<span data-ttu-id="d76e4-103">Получает уникальный идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="d76e4-103">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d76e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d76e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d76e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d76e4-105">Parameters</span></span>  
 `pId`  
 <span data-ttu-id="d76e4-106">[out] Уникальный идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="d76e4-106">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d76e4-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="d76e4-107">Remarks</span></span>  
 <span data-ttu-id="d76e4-108">Идентификатор домена приложения уникален в пределах содержащего его процесса.</span><span class="sxs-lookup"><span data-stu-id="d76e4-108">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d76e4-109">Требования</span><span class="sxs-lookup"><span data-stu-id="d76e4-109">Requirements</span></span>  
 <span data-ttu-id="d76e4-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d76e4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d76e4-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d76e4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d76e4-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d76e4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d76e4-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d76e4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
