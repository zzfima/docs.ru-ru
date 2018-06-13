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
ms.openlocfilehash: 8e108dd925432b8ec193863de4cb085dad50cdd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429077"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="d0aab-102">Функция DestroyICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="d0aab-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="d0aab-103">Уничтожает [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="d0aab-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="d0aab-104">Эта функция рекомендуется к использованию в [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d0aab-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0aab-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0aab-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0aab-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d0aab-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="d0aab-107">[in] `ICeeFileGen` Объект должен быть уничтожен.</span><span class="sxs-lookup"><span data-stu-id="d0aab-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0aab-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d0aab-108">Return Value</span></span>  
 <span data-ttu-id="d0aab-109">Этот метод возвращает стандартные коды ошибок COM.</span><span class="sxs-lookup"><span data-stu-id="d0aab-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0aab-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="d0aab-110">Remarks</span></span>  
 <span data-ttu-id="d0aab-111">`DestroyICeeFileGen` Уничтожает `ICeeFileGen` объект, созданный [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) функции.</span><span class="sxs-lookup"><span data-stu-id="d0aab-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0aab-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d0aab-112">Requirements</span></span>  
 <span data-ttu-id="d0aab-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0aab-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0aab-114">**Заголовок:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="d0aab-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="d0aab-115">**Библиотека:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="d0aab-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="d0aab-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0aab-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0aab-117">См. также</span><span class="sxs-lookup"><span data-stu-id="d0aab-117">See Also</span></span>  
 [<span data-ttu-id="d0aab-118">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="d0aab-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
