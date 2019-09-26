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
ms.openlocfilehash: 4528ccd77fed2ea2a9b2d08243ffa1535bfad1ae
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274087"
---
# <a name="clr_debugging_version-structure"></a><span data-ttu-id="81b21-102">Структура CLR_DEBUGGING_VERSION</span><span class="sxs-lookup"><span data-stu-id="81b21-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="81b21-103">Определяет версию продукта среды CLR, предназначенную для отладки.</span><span class="sxs-lookup"><span data-stu-id="81b21-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81b21-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81b21-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="81b21-105">Участники</span><span class="sxs-lookup"><span data-stu-id="81b21-105">Members</span></span>  
  
|<span data-ttu-id="81b21-106">Член</span><span class="sxs-lookup"><span data-stu-id="81b21-106">Member</span></span>|<span data-ttu-id="81b21-107">Описание</span><span class="sxs-lookup"><span data-stu-id="81b21-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="81b21-108">Номер версии структуры</span><span class="sxs-lookup"><span data-stu-id="81b21-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="81b21-109">Основной номер версии.</span><span class="sxs-lookup"><span data-stu-id="81b21-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="81b21-110">Дополнительный номер версии.</span><span class="sxs-lookup"><span data-stu-id="81b21-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="81b21-111">Номер сборки.</span><span class="sxs-lookup"><span data-stu-id="81b21-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="81b21-112">Номер редакции.</span><span class="sxs-lookup"><span data-stu-id="81b21-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81b21-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="81b21-113">Remarks</span></span>  
 <span data-ttu-id="81b21-114">Структура аналогична структуре COR_VERSION, однако `CLR_DEBUGGING_VERSION` структура предоставляет дополнительное поле версии структуры (`wStructVersion`). `CLR_DEBUGGING_VERSION`</span><span class="sxs-lookup"><span data-stu-id="81b21-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="81b21-115">В настоящее время для этого поля необходимо задать значение 0.</span><span class="sxs-lookup"><span data-stu-id="81b21-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81b21-116">Требования</span><span class="sxs-lookup"><span data-stu-id="81b21-116">Requirements</span></span>  
 <span data-ttu-id="81b21-117">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81b21-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81b21-118">**Заголовок.** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="81b21-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="81b21-119">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="81b21-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81b21-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81b21-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81b21-121">См. также</span><span class="sxs-lookup"><span data-stu-id="81b21-121">See also</span></span>

- [<span data-ttu-id="81b21-122">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="81b21-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="81b21-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="81b21-123">Debugging</span></span>](index.md)
