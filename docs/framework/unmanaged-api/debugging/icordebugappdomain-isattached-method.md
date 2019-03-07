---
title: Метод ICorDebugAppDomain::IsAttached
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa9576f568ef1f6da3eef812abb9674aa0d81dfb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496382"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="22dda-102">Метод ICorDebugAppDomain::IsAttached</span><span class="sxs-lookup"><span data-stu-id="22dda-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="22dda-103">Получает значение, указывающее, присоединен ли отладчик в домен приложения.</span><span class="sxs-lookup"><span data-stu-id="22dda-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22dda-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22dda-104">Syntax</span></span>  
  
```  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22dda-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="22dda-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="22dda-106">[out] `true` Если отладчик присоединен в домен приложения; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="22dda-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22dda-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="22dda-107">Remarks</span></span>  
 <span data-ttu-id="22dda-108">ICorDebugController методы нельзя использовать до подключения отладчика к домену приложения.</span><span class="sxs-lookup"><span data-stu-id="22dda-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22dda-109">Требования</span><span class="sxs-lookup"><span data-stu-id="22dda-109">Requirements</span></span>  
 <span data-ttu-id="22dda-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22dda-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22dda-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22dda-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22dda-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22dda-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22dda-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22dda-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
