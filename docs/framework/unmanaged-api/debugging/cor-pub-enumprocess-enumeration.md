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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eab5fc13b74d8af4f0baaa3953c5c73ea255bfe6
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274024"
---
# <a name="cor_pub_enumprocess-enumeration"></a><span data-ttu-id="b1d5e-102">Перечисление COR_PUB_ENUMPROCESS</span><span class="sxs-lookup"><span data-stu-id="b1d5e-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="b1d5e-103">Идентифицирует тип процесса для перечисления.</span><span class="sxs-lookup"><span data-stu-id="b1d5e-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1d5e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1d5e-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="b1d5e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b1d5e-105">Members</span></span>  
  
|<span data-ttu-id="b1d5e-106">Имя члена</span><span class="sxs-lookup"><span data-stu-id="b1d5e-106">Member name</span></span>|<span data-ttu-id="b1d5e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b1d5e-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="b1d5e-108">Управляемый процесс.</span><span class="sxs-lookup"><span data-stu-id="b1d5e-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1d5e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b1d5e-109">Remarks</span></span>  
 <span data-ttu-id="b1d5e-110">Текущая версия неуправляемого API отладки перечисляет только управляемые процессы.</span><span class="sxs-lookup"><span data-stu-id="b1d5e-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1d5e-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b1d5e-111">Requirements</span></span>  
 <span data-ttu-id="b1d5e-112">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1d5e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1d5e-113">**Заголовок.** Корпуб. idl, Корпуб. h</span><span class="sxs-lookup"><span data-stu-id="b1d5e-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="b1d5e-114">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="b1d5e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1d5e-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1d5e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1d5e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b1d5e-116">See also</span></span>

- [<span data-ttu-id="b1d5e-117">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="b1d5e-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
