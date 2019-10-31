---
title: Перечисление COR_PUB_ENUMPROCESS
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
ms.openlocfilehash: f789105751ae2d498740ab60f326f9c0597483b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099200"
---
# <a name="cor_pub_enumprocess-enumeration"></a><span data-ttu-id="d9135-102">Перечисление COR_PUB_ENUMPROCESS</span><span class="sxs-lookup"><span data-stu-id="d9135-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="d9135-103">Идентифицирует тип процесса для перечисления.</span><span class="sxs-lookup"><span data-stu-id="d9135-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9135-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9135-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="d9135-105">Члены</span><span class="sxs-lookup"><span data-stu-id="d9135-105">Members</span></span>  
  
|<span data-ttu-id="d9135-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="d9135-106">Member name</span></span>|<span data-ttu-id="d9135-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d9135-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="d9135-108">Управляемый процесс.</span><span class="sxs-lookup"><span data-stu-id="d9135-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9135-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="d9135-109">Remarks</span></span>  
 <span data-ttu-id="d9135-110">Текущая версия неуправляемого API отладки перечисляет только управляемые процессы.</span><span class="sxs-lookup"><span data-stu-id="d9135-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9135-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d9135-111">Requirements</span></span>  
 <span data-ttu-id="d9135-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9135-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9135-113">**Заголовок:** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="d9135-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="d9135-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9135-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9135-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9135-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9135-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d9135-116">See also</span></span>

- [<span data-ttu-id="d9135-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="d9135-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
