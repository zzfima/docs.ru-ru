---
title: Структура CodeChunkInfo
ms.date: 03/30/2017
api_name:
- CodeChunkInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CodeChunkInfo
helpviewer_keywords:
- CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58c9d4c66af0bb9f4e66d17b18ac78ef8271bc31
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072666"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="ab6cf-102">Структура CodeChunkInfo</span><span class="sxs-lookup"><span data-stu-id="ab6cf-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="ab6cf-103">Представляет одинарный блок кода в памяти.</span><span class="sxs-lookup"><span data-stu-id="ab6cf-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab6cf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab6cf-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="ab6cf-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ab6cf-105">Members</span></span>  
  
|<span data-ttu-id="ab6cf-106">Член</span><span class="sxs-lookup"><span data-stu-id="ab6cf-106">Member</span></span>|<span data-ttu-id="ab6cf-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ab6cf-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="ab6cf-108">Объект `CORDB_ADDRESS` значение, указывающее начальный адрес фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="ab6cf-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="ab6cf-109">Размер в байтах блока.</span><span class="sxs-lookup"><span data-stu-id="ab6cf-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab6cf-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ab6cf-110">Remarks</span></span>  
 <span data-ttu-id="ab6cf-111">Отдельный блок кода — это область машинного кода, который является частью объекта кода, например, функция.</span><span class="sxs-lookup"><span data-stu-id="ab6cf-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab6cf-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ab6cf-112">Requirements</span></span>  
 <span data-ttu-id="ab6cf-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab6cf-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab6cf-114">**Заголовок.** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="ab6cf-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="ab6cf-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab6cf-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ab6cf-116">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ab6cf-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ab6cf-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ab6cf-117">See also</span></span>

- [<span data-ttu-id="ab6cf-118">Метод GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="ab6cf-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="ab6cf-119">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="ab6cf-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="ab6cf-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="ab6cf-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
