---
title: Функция GetCORRequiredVersion
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8597b68b75d2b5f77f68fc13c3fb78bfdae46178
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736287"
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="95fdf-102">Функция GetCORRequiredVersion</span><span class="sxs-lookup"><span data-stu-id="95fdf-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="95fdf-103">Получает номер необходимые версии среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="95fdf-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="95fdf-104">Эта функция является устаревшим в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="95fdf-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95fdf-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95fdf-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95fdf-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="95fdf-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="95fdf-107">[out] Буфер, содержащий строку, которая указывает номер версии.</span><span class="sxs-lookup"><span data-stu-id="95fdf-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="95fdf-108">[in] Размер в байтах буфера.</span><span class="sxs-lookup"><span data-stu-id="95fdf-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="95fdf-109">[out] Число возвращаемых байтов в буфере.</span><span class="sxs-lookup"><span data-stu-id="95fdf-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95fdf-110">Требования</span><span class="sxs-lookup"><span data-stu-id="95fdf-110">Requirements</span></span>  
 <span data-ttu-id="95fdf-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95fdf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95fdf-112">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="95fdf-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="95fdf-113">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="95fdf-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95fdf-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95fdf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95fdf-115">См. также</span><span class="sxs-lookup"><span data-stu-id="95fdf-115">See also</span></span>

- [<span data-ttu-id="95fdf-116">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="95fdf-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
