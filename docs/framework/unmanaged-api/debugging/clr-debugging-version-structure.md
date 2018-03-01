---
title: "Структура CLR_DEBUGGING_VERSION"
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
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 092024f3f4e6fc1bc923ae2a299c5d9c21f1b1b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="clrdebuggingversion-structure"></a><span data-ttu-id="9953e-102">Структура CLR_DEBUGGING_VERSION</span><span class="sxs-lookup"><span data-stu-id="9953e-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="9953e-103">Определяет версию продукта среды CLR, предназначенную для отладки.</span><span class="sxs-lookup"><span data-stu-id="9953e-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9953e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9953e-104">Syntax</span></span>  
  
```  
Typedef struct _CLR_DEBUGGING_VERSION  
{  
WORD wStructVersion;  
WORD wMajor;   
WORD wMinor;  
WORD wBuild;  
WORD wRevision;  
}  CLR_DEBUGGING_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="9953e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="9953e-105">Members</span></span>  
  
|<span data-ttu-id="9953e-106">Член</span><span class="sxs-lookup"><span data-stu-id="9953e-106">Member</span></span>|<span data-ttu-id="9953e-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="9953e-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="9953e-108">Номер версии структуры.</span><span class="sxs-lookup"><span data-stu-id="9953e-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="9953e-109">Основной номер версии.</span><span class="sxs-lookup"><span data-stu-id="9953e-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="9953e-110">Дополнительный номер версии.</span><span class="sxs-lookup"><span data-stu-id="9953e-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="9953e-111">Номер сборки.</span><span class="sxs-lookup"><span data-stu-id="9953e-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="9953e-112">Номер редакции.</span><span class="sxs-lookup"><span data-stu-id="9953e-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9953e-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="9953e-113">Remarks</span></span>  
 <span data-ttu-id="9953e-114">`CLR_DEBUGGING_VERSION` Структура совпадает со структурой COR_VERSION, тем не менее, `CLR_DEBUGGING_VERSION` структура предоставляет дополнительное поле версии структуры (`wStructVersion`).</span><span class="sxs-lookup"><span data-stu-id="9953e-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="9953e-115">В настоящее время это поле должен быть равен нулю.</span><span class="sxs-lookup"><span data-stu-id="9953e-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9953e-116">Требования</span><span class="sxs-lookup"><span data-stu-id="9953e-116">Requirements</span></span>  
 <span data-ttu-id="9953e-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9953e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9953e-118">**Заголовок:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="9953e-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="9953e-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9953e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9953e-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9953e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9953e-121">См. также</span><span class="sxs-lookup"><span data-stu-id="9953e-121">See Also</span></span>  
 [<span data-ttu-id="9953e-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="9953e-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="9953e-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="9953e-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
