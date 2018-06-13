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
ms.openlocfilehash: 66976b99b5686c62ad31c8a0365ce14f1bf33f85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439909"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="4f83b-102">Метод ITypeName::GetModifiers</span><span class="sxs-lookup"><span data-stu-id="4f83b-102">ITypeName::GetModifiers Method</span></span>
<span data-ttu-id="4f83b-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="4f83b-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f83b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f83b-104">Syntax</span></span>  
  
```  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="4f83b-105">Требования</span><span class="sxs-lookup"><span data-stu-id="4f83b-105">Requirements</span></span>  
 <span data-ttu-id="4f83b-106">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f83b-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f83b-107">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4f83b-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f83b-108">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4f83b-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f83b-109">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f83b-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f83b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="4f83b-110">See Also</span></span>  
 [<span data-ttu-id="4f83b-111">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="4f83b-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
