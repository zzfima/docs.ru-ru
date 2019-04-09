---
title: Функция DestroyICeeFileGen
ms.date: 03/30/2017
api_name:
- DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- DestroyICeeFileGen
helpviewer_keywords:
- DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37ff40e1c009b8e1e0509a4a3333d5a2a70bbfd2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159891"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="bdcda-102">Функция DestroyICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="bdcda-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="bdcda-103">Уничтожает [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="bdcda-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="bdcda-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bdcda-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdcda-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdcda-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdcda-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bdcda-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="bdcda-107">[in] `ICeeFileGen` Уничтожаемый объект.</span><span class="sxs-lookup"><span data-stu-id="bdcda-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bdcda-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bdcda-108">Return Value</span></span>  
 <span data-ttu-id="bdcda-109">Этот метод возвращает стандартные коды ошибок COM.</span><span class="sxs-lookup"><span data-stu-id="bdcda-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdcda-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="bdcda-110">Remarks</span></span>  
 `DestroyICeeFileGen` <span data-ttu-id="bdcda-111">Уничтожает `ICeeFileGen` объект, созданный [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="bdcda-111">destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdcda-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bdcda-112">Requirements</span></span>  
 <span data-ttu-id="bdcda-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdcda-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdcda-114">**Заголовок.** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="bdcda-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="bdcda-115">**Библиотека:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="bdcda-115">**Library:** MSCorPE.dll</span></span>  
  
 **<span data-ttu-id="bdcda-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bdcda-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bdcda-117">См. также</span><span class="sxs-lookup"><span data-stu-id="bdcda-117">See also</span></span>

- [<span data-ttu-id="bdcda-118">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="bdcda-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
