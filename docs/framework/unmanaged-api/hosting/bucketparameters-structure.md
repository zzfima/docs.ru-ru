---
title: Структура BucketParameters
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5998ce684726b2386d8f1e05eb7eaeccf455747c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110460"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="f7dd6-102">Структура BucketParameters</span><span class="sxs-lookup"><span data-stu-id="f7dd6-102">BucketParameters Structure</span></span>
<span data-ttu-id="f7dd6-103">Хранит имя типа события и параметры для текущего исключения, связанного с событием.</span><span class="sxs-lookup"><span data-stu-id="f7dd6-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7dd6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7dd6-104">Syntax</span></span>  
  
```  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="f7dd6-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f7dd6-105">Members</span></span>  
  
|<span data-ttu-id="f7dd6-106">Член</span><span class="sxs-lookup"><span data-stu-id="f7dd6-106">Member</span></span>|<span data-ttu-id="f7dd6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f7dd6-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="f7dd6-108">`true`, если остальная часть этой структуры является допустимым; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="f7dd6-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="f7dd6-109">Имя типа события.</span><span class="sxs-lookup"><span data-stu-id="f7dd6-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="f7dd6-110">Массив строк, каждая из которых задает параметр для текущего исключения, связанного с событием.</span><span class="sxs-lookup"><span data-stu-id="f7dd6-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f7dd6-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f7dd6-111">Requirements</span></span>  
 <span data-ttu-id="f7dd6-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7dd6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7dd6-113">**Заголовок.** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="f7dd6-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="f7dd6-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7dd6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7dd6-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f7dd6-115">See also</span></span>

- [<span data-ttu-id="f7dd6-116">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="f7dd6-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
