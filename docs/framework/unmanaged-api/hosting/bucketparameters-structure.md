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
ms.openlocfilehash: 80623bdec939b0ae5fc13008c1c4001c613ac435
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195960"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="62595-102">Структура BucketParameters</span><span class="sxs-lookup"><span data-stu-id="62595-102">BucketParameters Structure</span></span>
<span data-ttu-id="62595-103">Хранит имя типа события и параметры для текущего исключения, связанного с событием.</span><span class="sxs-lookup"><span data-stu-id="62595-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62595-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62595-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="62595-105">Члены</span><span class="sxs-lookup"><span data-stu-id="62595-105">Members</span></span>  
  
|<span data-ttu-id="62595-106">Член</span><span class="sxs-lookup"><span data-stu-id="62595-106">Member</span></span>|<span data-ttu-id="62595-107">Описание</span><span class="sxs-lookup"><span data-stu-id="62595-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="62595-108">`true`, если оставшаяся часть этой структуры является допустимой; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="62595-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="62595-109">Имя типа события.</span><span class="sxs-lookup"><span data-stu-id="62595-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="62595-110">Массив строк, каждый из которых задает параметр для текущего исключения, связанного с событием.</span><span class="sxs-lookup"><span data-stu-id="62595-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="62595-111">Требования</span><span class="sxs-lookup"><span data-stu-id="62595-111">Requirements</span></span>  
 <span data-ttu-id="62595-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62595-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62595-113">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="62595-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="62595-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62595-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62595-115">См. также</span><span class="sxs-lookup"><span data-stu-id="62595-115">See also</span></span>

- [<span data-ttu-id="62595-116">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="62595-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
