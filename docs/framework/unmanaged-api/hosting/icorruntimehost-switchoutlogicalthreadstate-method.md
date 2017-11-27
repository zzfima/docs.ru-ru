---
title: "Метод ICorRuntimeHost::SwitchOutLogicalThreadState"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.SwitchOutLogicalThreadState
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::SwitchOutLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState method [.NET Framework hosting]
- SwitchOutLogicalThreadState method [.NET Framework hosting]
ms.assetid: e1968f0b-2675-4dc2-8507-46164e1df154
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9eed11dd0a5ebd30952946f640957e9960485524
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="a9d44-102">Метод ICorRuntimeHost::SwitchOutLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="a9d44-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="a9d44-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="a9d44-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9d44-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9d44-104">Syntax</span></span>  
  
```  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9d44-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a9d44-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="a9d44-106">[out] Файл cookie, указывающее, была отключена, волокна.</span><span class="sxs-lookup"><span data-stu-id="a9d44-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9d44-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a9d44-107">Requirements</span></span>  
 <span data-ttu-id="a9d44-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9d44-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9d44-109">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a9d44-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9d44-110">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9d44-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9d44-111">**Версия платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="a9d44-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9d44-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a9d44-112">See Also</span></span>  
 [<span data-ttu-id="a9d44-113">ICorRuntimeHost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="a9d44-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
