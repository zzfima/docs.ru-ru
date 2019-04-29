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
ms.openlocfilehash: 484ca79483fc4a5d8f0d1cf2cd5a961c297249e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61961321"
---
# <a name="clrdataaddressrange-structure"></a><span data-ttu-id="9c24e-102">Структура CLRDATA_ADDRESS_RANGE</span><span class="sxs-lookup"><span data-stu-id="9c24e-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="9c24e-103">Определяет диапазон адресов.</span><span class="sxs-lookup"><span data-stu-id="9c24e-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9c24e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c24e-104">Syntax</span></span>

```
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="9c24e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="9c24e-105">Members</span></span>

| <span data-ttu-id="9c24e-106">Член</span><span class="sxs-lookup"><span data-stu-id="9c24e-106">Member</span></span>         | <span data-ttu-id="9c24e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9c24e-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="9c24e-108">Начальный адрес диапазона.</span><span class="sxs-lookup"><span data-stu-id="9c24e-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="9c24e-109">Конечный адрес диапазона.</span><span class="sxs-lookup"><span data-stu-id="9c24e-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="9c24e-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="9c24e-110">Remarks</span></span>

<span data-ttu-id="9c24e-111">Эта структура находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="9c24e-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="9c24e-112">Чтобы использовать его, определить структуру как указано выше, где `CLRDATA_ADDRESS` является 64-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="9c24e-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="9c24e-113">Требования</span><span class="sxs-lookup"><span data-stu-id="9c24e-113">Requirements</span></span>

<span data-ttu-id="9c24e-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c24e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9c24e-115">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="9c24e-115">**Header:** None</span></span>  
<span data-ttu-id="9c24e-116">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="9c24e-116">**Library:** None</span></span>  
<span data-ttu-id="9c24e-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9c24e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9c24e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="9c24e-118">See also</span></span>

- [<span data-ttu-id="9c24e-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="9c24e-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="9c24e-120">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="9c24e-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
