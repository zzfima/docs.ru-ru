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
ms.openlocfilehash: 651b916a0e3ca178432094428611f9bcc8f0fd17
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132418"
---
# <a name="clr_debugging_version-structure"></a><span data-ttu-id="909f2-102">Структура CLR_DEBUGGING_VERSION</span><span class="sxs-lookup"><span data-stu-id="909f2-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="909f2-103">Определяет версию продукта среды CLR, предназначенную для отладки.</span><span class="sxs-lookup"><span data-stu-id="909f2-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="909f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="909f2-104">Syntax</span></span>  
  
```cpp  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a><span data-ttu-id="909f2-105">Члены</span><span class="sxs-lookup"><span data-stu-id="909f2-105">Members</span></span>  
  
|<span data-ttu-id="909f2-106">Член</span><span class="sxs-lookup"><span data-stu-id="909f2-106">Member</span></span>|<span data-ttu-id="909f2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="909f2-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="909f2-108">Номер версии структуры</span><span class="sxs-lookup"><span data-stu-id="909f2-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="909f2-109">Основной номер версии.</span><span class="sxs-lookup"><span data-stu-id="909f2-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="909f2-110">Дополнительный номер версии.</span><span class="sxs-lookup"><span data-stu-id="909f2-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="909f2-111">Номер сборки.</span><span class="sxs-lookup"><span data-stu-id="909f2-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="909f2-112">Номер редакции.</span><span class="sxs-lookup"><span data-stu-id="909f2-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="909f2-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="909f2-113">Remarks</span></span>  
 <span data-ttu-id="909f2-114">Структура `CLR_DEBUGGING_VERSION` та же, что и структура COR_VERSION, однако структура `CLR_DEBUGGING_VERSION` предоставляет дополнительное поле версии структуры (`wStructVersion`).</span><span class="sxs-lookup"><span data-stu-id="909f2-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="909f2-115">В настоящее время для этого поля необходимо задать значение 0.</span><span class="sxs-lookup"><span data-stu-id="909f2-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="909f2-116">Требования</span><span class="sxs-lookup"><span data-stu-id="909f2-116">Requirements</span></span>  
 <span data-ttu-id="909f2-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="909f2-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="909f2-118">**Заголовок:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="909f2-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="909f2-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="909f2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="909f2-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="909f2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="909f2-121">См. также</span><span class="sxs-lookup"><span data-stu-id="909f2-121">See also</span></span>

- [<span data-ttu-id="909f2-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="909f2-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="909f2-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="909f2-123">Debugging</span></span>](index.md)
