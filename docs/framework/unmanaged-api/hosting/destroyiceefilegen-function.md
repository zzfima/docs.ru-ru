---
title: "Функция DestroyICeeFileGen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type: COM
f1_keywords: DestroyICeeFileGen
helpviewer_keywords: DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 11f0bd03532668196f85713459fe103f9120c82e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="ab70d-102">Функция DestroyICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="ab70d-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="ab70d-103">Уничтожает [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="ab70d-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="ab70d-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ab70d-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab70d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab70d-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab70d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ab70d-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="ab70d-107">[in] `ICeeFileGen` Объект должен быть уничтожен.</span><span class="sxs-lookup"><span data-stu-id="ab70d-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab70d-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ab70d-108">Return Value</span></span>  
 <span data-ttu-id="ab70d-109">Этот метод возвращает стандартные коды ошибок COM.</span><span class="sxs-lookup"><span data-stu-id="ab70d-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab70d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ab70d-110">Remarks</span></span>  
 <span data-ttu-id="ab70d-111">`DestroyICeeFileGen`Уничтожает `ICeeFileGen` объект, созданный [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="ab70d-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab70d-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ab70d-112">Requirements</span></span>  
 <span data-ttu-id="ab70d-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab70d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab70d-114">**Заголовок:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="ab70d-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="ab70d-115">**Библиотека:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="ab70d-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="ab70d-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab70d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab70d-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ab70d-117">See Also</span></span>  
 [<span data-ttu-id="ab70d-118">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="ab70d-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
