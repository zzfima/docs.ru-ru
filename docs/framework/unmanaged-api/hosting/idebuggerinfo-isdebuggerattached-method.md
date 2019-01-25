---
title: Метод IDebuggerInfo::IsDebuggerAttached
ms.date: 03/30/2017
api_name:
- IDebuggerInfo.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IsDebuggerAttached
helpviewer_keywords:
- IDebuggerInfo::IsDebuggerAttached method [.NET Framework hosting]
- IsDebuggerAttached method, IDebuggerInfo interface [.NET Framework hosting]
ms.assetid: 6e21872f-602f-411a-a423-bff5cdf27000
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d471ac13061cfb3a0320801445fb5c931718691
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562933"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="9fdfb-102">Метод IDebuggerInfo::IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="9fdfb-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="9fdfb-103">Получает значение, указывающее, присоединен ли управляемый отладчик к этому процессу.</span><span class="sxs-lookup"><span data-stu-id="9fdfb-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fdfb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9fdfb-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9fdfb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9fdfb-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="9fdfb-106">[out] Указатель на значение, являющееся `true` Если управляемый отладчик присоединен к процессу; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="9fdfb-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fdfb-107">Требования</span><span class="sxs-lookup"><span data-stu-id="9fdfb-107">Requirements</span></span>  
 <span data-ttu-id="9fdfb-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fdfb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fdfb-109">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9fdfb-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9fdfb-110">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9fdfb-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9fdfb-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fdfb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fdfb-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9fdfb-112">See also</span></span>
- [<span data-ttu-id="9fdfb-113">Интерфейс IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="9fdfb-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
