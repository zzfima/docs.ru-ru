---
title: Метод ITypeName::GetModifiers
ms.date: 03/30/2017
api_name:
- ITypeName.GetModifiers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetModifiers
helpviewer_keywords:
- ITypeName::GetModifiers method [.NET Framework hosting]
- GetModifiers method [.NET Framework hosting]
ms.assetid: 75508c55-3e09-4135-80da-cc811003fa82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b1702c49fd88efff263121dd4b05c392dcb92f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496108"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="a52aa-102">Метод ITypeName::GetModifiers</span><span class="sxs-lookup"><span data-stu-id="a52aa-102">ITypeName::GetModifiers Method</span></span>
<span data-ttu-id="a52aa-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="a52aa-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a52aa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a52aa-104">Syntax</span></span>  
  
```  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a52aa-105">Требования</span><span class="sxs-lookup"><span data-stu-id="a52aa-105">Requirements</span></span>  
 <span data-ttu-id="a52aa-106">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a52aa-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a52aa-107">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a52aa-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a52aa-108">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a52aa-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a52aa-109">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a52aa-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a52aa-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a52aa-110">See also</span></span>
- [<span data-ttu-id="a52aa-111">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="a52aa-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
