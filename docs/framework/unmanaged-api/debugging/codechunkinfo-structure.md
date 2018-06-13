---
title: CodeChunkInfo Structure1
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
ms.openlocfilehash: 6e3d138700ef06da7b40a88a768a41f3ffcb38eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403244"
---
# <a name="codechunkinfo-structure1"></a><span data-ttu-id="99089-102">CodeChunkInfo Structure1</span><span class="sxs-lookup"><span data-stu-id="99089-102">CodeChunkInfo Structure1</span></span>
<span data-ttu-id="99089-103">Представляет одинарный блок кода в памяти.</span><span class="sxs-lookup"><span data-stu-id="99089-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99089-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99089-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="99089-105">Участники</span><span class="sxs-lookup"><span data-stu-id="99089-105">Members</span></span>  
  
|<span data-ttu-id="99089-106">Член</span><span class="sxs-lookup"><span data-stu-id="99089-106">Member</span></span>|<span data-ttu-id="99089-107">Описание</span><span class="sxs-lookup"><span data-stu-id="99089-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="99089-108">Объект `CORDB_ADDRESS` значение, которое определяет начальный адрес фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="99089-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="99089-109">Размер в байтах блока.</span><span class="sxs-lookup"><span data-stu-id="99089-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99089-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="99089-110">Remarks</span></span>  
 <span data-ttu-id="99089-111">Одинарный блок кода — это область машинного кода, который является частью объекта кода, например, функция.</span><span class="sxs-lookup"><span data-stu-id="99089-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99089-112">Требования</span><span class="sxs-lookup"><span data-stu-id="99089-112">Requirements</span></span>  
 <span data-ttu-id="99089-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99089-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99089-114">**Заголовок:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="99089-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="99089-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99089-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99089-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99089-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99089-117">См. также</span><span class="sxs-lookup"><span data-stu-id="99089-117">See Also</span></span>  
 [<span data-ttu-id="99089-118">Метод GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="99089-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 [<span data-ttu-id="99089-119">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="99089-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="99089-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="99089-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
