---
title: "Метод ICorDebugAppDomain::IsAttached"
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
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a1af550de7198041a885a788d6b36349c8e1c091
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="93204-102">Метод ICorDebugAppDomain::IsAttached</span><span class="sxs-lookup"><span data-stu-id="93204-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="93204-103">Возвращает значение, показывающее, присоединен ли отладчик в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="93204-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93204-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93204-104">Syntax</span></span>  
  
```  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="93204-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="93204-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="93204-106">[out] `true` Если отладчик присоединен к домену приложения; в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="93204-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93204-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="93204-107">Remarks</span></span>  
 <span data-ttu-id="93204-108">Методы ICorDebugController нельзя, пока отладчик подключается к домену приложения.</span><span class="sxs-lookup"><span data-stu-id="93204-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93204-109">Требования</span><span class="sxs-lookup"><span data-stu-id="93204-109">Requirements</span></span>  
 <span data-ttu-id="93204-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93204-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93204-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93204-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93204-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93204-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93204-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93204-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
