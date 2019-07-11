---
title: Структура CLRDATA_ADDRESS_RANGE
ms.date: 01/16/2019
api.name:
- CLRDATA_ADDRESS_RANGE Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_ADDRESS_RANGE Structure
helpviewer.keywords:
- CLRDATA_ADDRESS_RANGE Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: afcb4e642c9b54107423f7474771fdc28cde709e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741026"
---
# <a name="clrdataaddressrange-structure"></a><span data-ttu-id="93bbb-102">Структура CLRDATA_ADDRESS_RANGE</span><span class="sxs-lookup"><span data-stu-id="93bbb-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="93bbb-103">Определяет диапазон адресов.</span><span class="sxs-lookup"><span data-stu-id="93bbb-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="93bbb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93bbb-104">Syntax</span></span>

```cpp
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="93bbb-105">Участники</span><span class="sxs-lookup"><span data-stu-id="93bbb-105">Members</span></span>

| <span data-ttu-id="93bbb-106">Член</span><span class="sxs-lookup"><span data-stu-id="93bbb-106">Member</span></span>         | <span data-ttu-id="93bbb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="93bbb-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="93bbb-108">Начальный адрес диапазона.</span><span class="sxs-lookup"><span data-stu-id="93bbb-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="93bbb-109">Конечный адрес диапазона.</span><span class="sxs-lookup"><span data-stu-id="93bbb-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="93bbb-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="93bbb-110">Remarks</span></span>

<span data-ttu-id="93bbb-111">Эта структура находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="93bbb-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="93bbb-112">Чтобы использовать его, определить структуру как указано выше, где `CLRDATA_ADDRESS` является 64-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="93bbb-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="93bbb-113">Требования</span><span class="sxs-lookup"><span data-stu-id="93bbb-113">Requirements</span></span>

<span data-ttu-id="93bbb-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93bbb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="93bbb-115">**Заголовок.** None</span><span class="sxs-lookup"><span data-stu-id="93bbb-115">**Header:** None</span></span>  
<span data-ttu-id="93bbb-116">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="93bbb-116">**Library:** None</span></span>  
<span data-ttu-id="93bbb-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="93bbb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="93bbb-118">См. также</span><span class="sxs-lookup"><span data-stu-id="93bbb-118">See also</span></span>

- [<span data-ttu-id="93bbb-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="93bbb-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="93bbb-120">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="93bbb-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
