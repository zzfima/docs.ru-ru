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
ms.openlocfilehash: d33c8b31473e389e07fb24076dc32272e9dde387
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132389"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="ca2e8-102">Структура CodeChunkInfo</span><span class="sxs-lookup"><span data-stu-id="ca2e8-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="ca2e8-103">Представляет одинарный блок кода в памяти.</span><span class="sxs-lookup"><span data-stu-id="ca2e8-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca2e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca2e8-104">Syntax</span></span>  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="ca2e8-105">Члены</span><span class="sxs-lookup"><span data-stu-id="ca2e8-105">Members</span></span>  
  
|<span data-ttu-id="ca2e8-106">Член</span><span class="sxs-lookup"><span data-stu-id="ca2e8-106">Member</span></span>|<span data-ttu-id="ca2e8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ca2e8-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="ca2e8-108">Значение `CORDB_ADDRESS`, указывающее начальный адрес фрагмента.</span><span class="sxs-lookup"><span data-stu-id="ca2e8-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="ca2e8-109">Размер блока в байтах.</span><span class="sxs-lookup"><span data-stu-id="ca2e8-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca2e8-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="ca2e8-110">Remarks</span></span>  
 <span data-ttu-id="ca2e8-111">Единственный фрагмент кода — это область машинного кода, которая является частью объекта кода, например функции.</span><span class="sxs-lookup"><span data-stu-id="ca2e8-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca2e8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ca2e8-112">Requirements</span></span>  
 <span data-ttu-id="ca2e8-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca2e8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca2e8-114">**Заголовок:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="ca2e8-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="ca2e8-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca2e8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca2e8-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca2e8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca2e8-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ca2e8-117">See also</span></span>

- [<span data-ttu-id="ca2e8-118">Метод GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="ca2e8-118">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="ca2e8-119">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="ca2e8-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="ca2e8-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="ca2e8-120">Debugging</span></span>](index.md)
