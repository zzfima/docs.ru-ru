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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 56734a9971759b78a835917c4914cf55edaa47a4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103289"
---
# <a name="corprfcodeinfo-structure"></a><span data-ttu-id="7c069-102">Структура COR_PRF_CODE_INFO</span><span class="sxs-lookup"><span data-stu-id="7c069-102">COR_PRF_CODE_INFO Structure</span></span>
<span data-ttu-id="7c069-103">Представляет один непрерывный блок машинного кода, хранящийся в памяти.</span><span class="sxs-lookup"><span data-stu-id="7c069-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c069-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7c069-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="7c069-105">Участники</span><span class="sxs-lookup"><span data-stu-id="7c069-105">Members</span></span>  
  
|<span data-ttu-id="7c069-106">Член</span><span class="sxs-lookup"><span data-stu-id="7c069-106">Member</span></span>|<span data-ttu-id="7c069-107">Описание</span><span class="sxs-lookup"><span data-stu-id="7c069-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="7c069-108">Начальный адрес непрерывного блока кода.</span><span class="sxs-lookup"><span data-stu-id="7c069-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="7c069-109">Размер блока.</span><span class="sxs-lookup"><span data-stu-id="7c069-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7c069-110">Требования</span><span class="sxs-lookup"><span data-stu-id="7c069-110">Requirements</span></span>  
 <span data-ttu-id="7c069-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c069-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c069-112">**Заголовок.** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="7c069-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="7c069-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c069-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c069-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c069-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c069-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7c069-115">See also</span></span>

- [<span data-ttu-id="7c069-116">Структуры профилирования</span><span class="sxs-lookup"><span data-stu-id="7c069-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
