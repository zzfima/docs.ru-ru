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
ms.openlocfilehash: 0708a3b501a99b5f71be5ba4c6cc4ea2b754d12a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191345"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="71087-102">Метод IDebuggerInfo::IsDebuggerAttached</span><span class="sxs-lookup"><span data-stu-id="71087-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="71087-103">Получает значение, указывающее, присоединен ли управляемый отладчик к этому процессу.</span><span class="sxs-lookup"><span data-stu-id="71087-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71087-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71087-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71087-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="71087-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="71087-106">[out] Указатель на значение, являющееся `true` Если управляемый отладчик присоединен к процессу; в противном случае — значение `false`.</span><span class="sxs-lookup"><span data-stu-id="71087-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71087-107">Требования</span><span class="sxs-lookup"><span data-stu-id="71087-107">Requirements</span></span>  
 <span data-ttu-id="71087-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71087-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71087-109">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="71087-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71087-110">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="71087-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="71087-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="71087-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="71087-112">См. также</span><span class="sxs-lookup"><span data-stu-id="71087-112">See also</span></span>

- [<span data-ttu-id="71087-113">Интерфейс IDebuggerInfo</span><span class="sxs-lookup"><span data-stu-id="71087-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
