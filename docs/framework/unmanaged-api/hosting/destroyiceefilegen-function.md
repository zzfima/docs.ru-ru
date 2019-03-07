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
ms.openlocfilehash: 50bfe38bc4c4843ac0954a6c816e5dc06b5e0fed
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501959"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="25dde-102">Функция DestroyICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="25dde-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="25dde-103">Уничтожает [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="25dde-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="25dde-104">Эта функция устарели в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="25dde-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25dde-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="25dde-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25dde-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="25dde-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="25dde-107">[in] `ICeeFileGen` Уничтожаемый объект.</span><span class="sxs-lookup"><span data-stu-id="25dde-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25dde-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="25dde-108">Return Value</span></span>  
 <span data-ttu-id="25dde-109">Этот метод возвращает стандартные коды ошибок COM.</span><span class="sxs-lookup"><span data-stu-id="25dde-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25dde-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="25dde-110">Remarks</span></span>  
 <span data-ttu-id="25dde-111">`DestroyICeeFileGen` Уничтожает `ICeeFileGen` объект, созданный [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="25dde-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25dde-112">Требования</span><span class="sxs-lookup"><span data-stu-id="25dde-112">Requirements</span></span>  
 <span data-ttu-id="25dde-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25dde-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25dde-114">**Заголовок.** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="25dde-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="25dde-115">**Библиотека:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="25dde-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="25dde-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25dde-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25dde-117">См. также</span><span class="sxs-lookup"><span data-stu-id="25dde-117">See also</span></span>
- [<span data-ttu-id="25dde-118">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="25dde-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
