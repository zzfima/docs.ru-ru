---
title: "Функция GetCORRequiredVersion"
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
- GetCORRequiredVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetCORRequiredVersion
helpviewer_keywords:
- GetCORRequiredVersion function [.NET Framework hosting]
ms.assetid: 1588fe7b-c378-4f4b-9c4b-48647f1119cc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 65505243d7d1691f0458d614fd878b054916f113
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="69a23-102">Функция GetCORRequiredVersion</span><span class="sxs-lookup"><span data-stu-id="69a23-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="69a23-103">Возвращает номером необходимые версии среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="69a23-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="69a23-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69a23-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69a23-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69a23-105">Syntax</span></span>  
  
```  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69a23-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="69a23-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="69a23-107">[out] Буфер, содержащий строку, номер версии.</span><span class="sxs-lookup"><span data-stu-id="69a23-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="69a23-108">[in] Размер в байтах буфера.</span><span class="sxs-lookup"><span data-stu-id="69a23-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="69a23-109">[out] Число байтов, возвращенных в буфере.</span><span class="sxs-lookup"><span data-stu-id="69a23-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69a23-110">Требования</span><span class="sxs-lookup"><span data-stu-id="69a23-110">Requirements</span></span>  
 <span data-ttu-id="69a23-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69a23-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69a23-112">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="69a23-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="69a23-113">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="69a23-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="69a23-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69a23-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69a23-115">См. также</span><span class="sxs-lookup"><span data-stu-id="69a23-115">See Also</span></span>  
 [<span data-ttu-id="69a23-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="69a23-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
