---
title: Структура CLR_DEBUGGING_VERSION
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87f938a7119abe4a88da65bd779a5f4a02499516
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117122"
---
# <a name="clrdebuggingversion-structure"></a><span data-ttu-id="49d0a-102">Структура CLR_DEBUGGING_VERSION</span><span class="sxs-lookup"><span data-stu-id="49d0a-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="49d0a-103">Определяет версию продукта среды CLR, предназначенную для отладки.</span><span class="sxs-lookup"><span data-stu-id="49d0a-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49d0a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49d0a-104">Syntax</span></span>  
  
```  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a><span data-ttu-id="49d0a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="49d0a-105">Members</span></span>  
  
|<span data-ttu-id="49d0a-106">Член</span><span class="sxs-lookup"><span data-stu-id="49d0a-106">Member</span></span>|<span data-ttu-id="49d0a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="49d0a-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="49d0a-108">Номер версии структуры.</span><span class="sxs-lookup"><span data-stu-id="49d0a-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="49d0a-109">Основной номер версии.</span><span class="sxs-lookup"><span data-stu-id="49d0a-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="49d0a-110">Дополнительный номер версии.</span><span class="sxs-lookup"><span data-stu-id="49d0a-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="49d0a-111">Номер сборки.</span><span class="sxs-lookup"><span data-stu-id="49d0a-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="49d0a-112">Номер редакции.</span><span class="sxs-lookup"><span data-stu-id="49d0a-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49d0a-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="49d0a-113">Remarks</span></span>  
 <span data-ttu-id="49d0a-114">`CLR_DEBUGGING_VERSION` Структура является таким же, как структура COR_VERSION, тем не менее, `CLR_DEBUGGING_VERSION` структура предоставляет дополнительное поле версии структуры (`wStructVersion`).</span><span class="sxs-lookup"><span data-stu-id="49d0a-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="49d0a-115">В настоящее время это поле должен быть равным нулю.</span><span class="sxs-lookup"><span data-stu-id="49d0a-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49d0a-116">Требования</span><span class="sxs-lookup"><span data-stu-id="49d0a-116">Requirements</span></span>  
 <span data-ttu-id="49d0a-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49d0a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49d0a-118">**Заголовок.** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="49d0a-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="49d0a-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49d0a-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="49d0a-120">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="49d0a-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="49d0a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="49d0a-121">See also</span></span>

- [<span data-ttu-id="49d0a-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="49d0a-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="49d0a-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="49d0a-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
