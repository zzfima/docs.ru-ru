---
title: "Метод ICorDebugAppDomain::GetId"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8b151d5b0774576e98da5845e5c7afc24ada0001
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="7edd6-102">Метод ICorDebugAppDomain::GetId</span><span class="sxs-lookup"><span data-stu-id="7edd6-102">ICorDebugAppDomain::GetId Method</span></span>
<span data-ttu-id="7edd6-103">Возвращает уникальный идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="7edd6-103">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7edd6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7edd6-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7edd6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7edd6-105">Parameters</span></span>  
 `pId`  
 <span data-ttu-id="7edd6-106">[out] Уникальный идентификатор домена приложения.</span><span class="sxs-lookup"><span data-stu-id="7edd6-106">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7edd6-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="7edd6-107">Remarks</span></span>  
 <span data-ttu-id="7edd6-108">Идентификатор домена приложения уникален в пределах содержащего его процесса.</span><span class="sxs-lookup"><span data-stu-id="7edd6-108">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7edd6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7edd6-109">Requirements</span></span>  
 <span data-ttu-id="7edd6-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7edd6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7edd6-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7edd6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7edd6-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7edd6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7edd6-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7edd6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
