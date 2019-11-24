---
title: Структура COR_PRF_CODE_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_CODE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODE_INFO
helpviewer_keywords:
- COR_PRF_CODE_INFO structure [.NET Framework profiling]
ms.assetid: cf30e27c-1f7e-43a2-ba1e-01e4137301db
topic_type:
- apiref
ms.openlocfilehash: 643c9d7104c374d9141a604083f3fdcd540156c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428384"
---
# <a name="cor_prf_code_info-structure"></a><span data-ttu-id="1bbfa-102">Структура COR_PRF_CODE_INFO</span><span class="sxs-lookup"><span data-stu-id="1bbfa-102">COR_PRF_CODE_INFO Structure</span></span>
<span data-ttu-id="1bbfa-103">Представляет один непрерывный блок машинного кода, хранящийся в памяти.</span><span class="sxs-lookup"><span data-stu-id="1bbfa-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bbfa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bbfa-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="1bbfa-105">Члены</span><span class="sxs-lookup"><span data-stu-id="1bbfa-105">Members</span></span>  
  
|<span data-ttu-id="1bbfa-106">Член</span><span class="sxs-lookup"><span data-stu-id="1bbfa-106">Member</span></span>|<span data-ttu-id="1bbfa-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1bbfa-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="1bbfa-108">The starting address of the contiguous block of code.</span><span class="sxs-lookup"><span data-stu-id="1bbfa-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="1bbfa-109">The size of the block.</span><span class="sxs-lookup"><span data-stu-id="1bbfa-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1bbfa-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1bbfa-110">Requirements</span></span>  
 <span data-ttu-id="1bbfa-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bbfa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bbfa-112">**Header:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="1bbfa-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="1bbfa-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bbfa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bbfa-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bbfa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bbfa-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1bbfa-115">See also</span></span>

- [<span data-ttu-id="1bbfa-116">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="1bbfa-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
