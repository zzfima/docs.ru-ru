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
ms.openlocfilehash: eaab5b7faeac3dd0fb64f0a387f437af44e7bc12
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867312"
---
# <a name="cor_prf_code_info-structure"></a><span data-ttu-id="b2635-102">Структура COR_PRF_CODE_INFO</span><span class="sxs-lookup"><span data-stu-id="b2635-102">COR_PRF_CODE_INFO Structure</span></span>
<span data-ttu-id="b2635-103">Представляет один непрерывный блок машинного кода, хранящийся в памяти.</span><span class="sxs-lookup"><span data-stu-id="b2635-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2635-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2635-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="b2635-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b2635-105">Members</span></span>  
  
|<span data-ttu-id="b2635-106">Член</span><span class="sxs-lookup"><span data-stu-id="b2635-106">Member</span></span>|<span data-ttu-id="b2635-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b2635-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="b2635-108">Начальный адрес непрерывного блока кода.</span><span class="sxs-lookup"><span data-stu-id="b2635-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="b2635-109">Размер блока.</span><span class="sxs-lookup"><span data-stu-id="b2635-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2635-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b2635-110">Requirements</span></span>  
 <span data-ttu-id="b2635-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2635-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2635-112">**Заголовок:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="b2635-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="b2635-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2635-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2635-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2635-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2635-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="b2635-115">See also</span></span>

- [<span data-ttu-id="b2635-116">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="b2635-116">Profiling Structures</span></span>](profiling-structures.md)
