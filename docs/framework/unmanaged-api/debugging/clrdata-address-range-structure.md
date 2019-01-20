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
ms.openlocfilehash: 3a8832a0eb173da00715bd0441b7efd337eae932
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416544"
---
# <a name="clrdataaddressrange-structure"></a><span data-ttu-id="29c27-102">Структура CLRDATA_ADDRESS_RANGE</span><span class="sxs-lookup"><span data-stu-id="29c27-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="29c27-103">Определяет диапазон адресов.</span><span class="sxs-lookup"><span data-stu-id="29c27-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="29c27-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29c27-104">Syntax</span></span>

```
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="29c27-105">Участники</span><span class="sxs-lookup"><span data-stu-id="29c27-105">Members</span></span>

| <span data-ttu-id="29c27-106">Член</span><span class="sxs-lookup"><span data-stu-id="29c27-106">Member</span></span>         | <span data-ttu-id="29c27-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="29c27-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="29c27-108">Начальный адрес диапазона.</span><span class="sxs-lookup"><span data-stu-id="29c27-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="29c27-109">Конечный адрес диапазона.</span><span class="sxs-lookup"><span data-stu-id="29c27-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="29c27-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="29c27-110">Remarks</span></span>

<span data-ttu-id="29c27-111">Эта структура находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="29c27-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="29c27-112">Чтобы использовать его, определить структуру как указано выше, где `CLRDATA_ADDRESS` является 64-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="29c27-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="29c27-113">Требования</span><span class="sxs-lookup"><span data-stu-id="29c27-113">Requirements</span></span>

<span data-ttu-id="29c27-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29c27-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="29c27-115">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="29c27-115">**Header:** None</span></span>  
<span data-ttu-id="29c27-116">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="29c27-116">**Library:** None</span></span>  
<span data-ttu-id="29c27-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="29c27-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="29c27-118">См. также</span><span class="sxs-lookup"><span data-stu-id="29c27-118">See Also</span></span>

- [<span data-ttu-id="29c27-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="29c27-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="29c27-120">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="29c27-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
