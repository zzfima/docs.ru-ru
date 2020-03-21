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
ms.openlocfilehash: 4d9de489bdeb0ab506f56ff08f4afb4cf6d0ab4f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178277"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="9aa03-102">Структура BucketParameters</span><span class="sxs-lookup"><span data-stu-id="9aa03-102">BucketParameters Structure</span></span>
<span data-ttu-id="9aa03-103">Хранит имя типа события и параметры текущего исключения, связанного с событием.</span><span class="sxs-lookup"><span data-stu-id="9aa03-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9aa03-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9aa03-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="9aa03-105">Члены</span><span class="sxs-lookup"><span data-stu-id="9aa03-105">Members</span></span>  
  
|<span data-ttu-id="9aa03-106">Участник</span><span class="sxs-lookup"><span data-stu-id="9aa03-106">Member</span></span>|<span data-ttu-id="9aa03-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9aa03-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="9aa03-108">`true`, если остальная часть этой структуры действительна; в `false`противном случае, .</span><span class="sxs-lookup"><span data-stu-id="9aa03-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="9aa03-109">Название типа события.</span><span class="sxs-lookup"><span data-stu-id="9aa03-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="9aa03-110">Массив строк, каждая из которых определяет параметр для текущего исключения, связанного с событием.</span><span class="sxs-lookup"><span data-stu-id="9aa03-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9aa03-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9aa03-111">Requirements</span></span>  
 <span data-ttu-id="9aa03-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9aa03-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9aa03-113">**Заголовок:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="9aa03-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="9aa03-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9aa03-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aa03-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9aa03-115">See also</span></span>

- [<span data-ttu-id="9aa03-116">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="9aa03-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
