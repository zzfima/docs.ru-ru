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
ms.openlocfilehash: 36afee8af3de046683c55215a677a529b0837c77
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274259"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="f00f7-102">Структура CodeChunkInfo</span><span class="sxs-lookup"><span data-stu-id="f00f7-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="f00f7-103">Представляет одинарный блок кода в памяти.</span><span class="sxs-lookup"><span data-stu-id="f00f7-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f00f7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f00f7-104">Syntax</span></span>  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="f00f7-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f00f7-105">Members</span></span>  
  
|<span data-ttu-id="f00f7-106">Член</span><span class="sxs-lookup"><span data-stu-id="f00f7-106">Member</span></span>|<span data-ttu-id="f00f7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f00f7-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="f00f7-108">`CORDB_ADDRESS` Значение, указывающее начальный адрес фрагмента.</span><span class="sxs-lookup"><span data-stu-id="f00f7-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="f00f7-109">Размер блока в байтах.</span><span class="sxs-lookup"><span data-stu-id="f00f7-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f00f7-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="f00f7-110">Remarks</span></span>  
 <span data-ttu-id="f00f7-111">Единственный фрагмент кода — это область машинного кода, которая является частью объекта кода, например функции.</span><span class="sxs-lookup"><span data-stu-id="f00f7-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f00f7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f00f7-112">Requirements</span></span>  
 <span data-ttu-id="f00f7-113">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f00f7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f00f7-114">**Заголовок.** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="f00f7-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="f00f7-115">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="f00f7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f00f7-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f00f7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f00f7-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f00f7-117">See also</span></span>

- [<span data-ttu-id="f00f7-118">Метод GetCodeChunks</span><span class="sxs-lookup"><span data-stu-id="f00f7-118">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="f00f7-119">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="f00f7-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="f00f7-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="f00f7-120">Debugging</span></span>](index.md)
