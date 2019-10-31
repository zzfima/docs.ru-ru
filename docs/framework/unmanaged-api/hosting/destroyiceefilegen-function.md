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
ms.openlocfilehash: 4eb878b61b72378bc6870af7f2cd09f0b6943b13
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136506"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="4a740-102">Функция DestroyICeeFileGen</span><span class="sxs-lookup"><span data-stu-id="4a740-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="4a740-103">Уничтожает объект [ицеефилежен](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) .</span><span class="sxs-lookup"><span data-stu-id="4a740-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="4a740-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4a740-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a740-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a740-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a740-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4a740-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="4a740-107">окне Объект `ICeeFileGen` для уничтожения.</span><span class="sxs-lookup"><span data-stu-id="4a740-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a740-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4a740-108">Return Value</span></span>  
 <span data-ttu-id="4a740-109">Этот метод возвращает стандартные коды ошибок COM.</span><span class="sxs-lookup"><span data-stu-id="4a740-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a740-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="4a740-110">Remarks</span></span>  
 <span data-ttu-id="4a740-111">`DestroyICeeFileGen` уничтожает объект `ICeeFileGen`, созданный функцией [креатеицеефилежен](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) .</span><span class="sxs-lookup"><span data-stu-id="4a740-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a740-112">Требования</span><span class="sxs-lookup"><span data-stu-id="4a740-112">Requirements</span></span>  
 <span data-ttu-id="4a740-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a740-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a740-114">**Заголовок:** Ицеефилежен. h</span><span class="sxs-lookup"><span data-stu-id="4a740-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="4a740-115">**Библиотека:** Мскорпе. dll</span><span class="sxs-lookup"><span data-stu-id="4a740-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="4a740-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a740-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a740-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4a740-117">See also</span></span>

- [<span data-ttu-id="4a740-118">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="4a740-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
