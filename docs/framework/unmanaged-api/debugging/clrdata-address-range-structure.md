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
ms.openlocfilehash: 8eb841b4c4f06a3932805ae6222bdd693def5ea0
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274302"
---
# <a name="clrdata_address_range-structure"></a><span data-ttu-id="53861-102">Структура CLRDATA_ADDRESS_RANGE</span><span class="sxs-lookup"><span data-stu-id="53861-102">CLRDATA_ADDRESS_RANGE Structure</span></span>

<span data-ttu-id="53861-103">Определяет диапазон адресов.</span><span class="sxs-lookup"><span data-stu-id="53861-103">Defines an address range.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="53861-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53861-104">Syntax</span></span>

```cpp
typedef struct
{
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
} CLRDATA_ADDRESS_RANGE;
```

## <a name="members"></a><span data-ttu-id="53861-105">Участники</span><span class="sxs-lookup"><span data-stu-id="53861-105">Members</span></span>

| <span data-ttu-id="53861-106">Член</span><span class="sxs-lookup"><span data-stu-id="53861-106">Member</span></span>         | <span data-ttu-id="53861-107">Описание</span><span class="sxs-lookup"><span data-stu-id="53861-107">Description</span></span>                     |
| -------------- | ------------------------------- |
| `startAddress` | <span data-ttu-id="53861-108">Начальный адрес диапазона.</span><span class="sxs-lookup"><span data-stu-id="53861-108">The start address of the range.</span></span> |
| `endAddress`   | <span data-ttu-id="53861-109">Конечный адрес диапазона.</span><span class="sxs-lookup"><span data-stu-id="53861-109">The end address of the range.</span></span>   |

## <a name="remarks"></a><span data-ttu-id="53861-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="53861-110">Remarks</span></span>

<span data-ttu-id="53861-111">Эта структура находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="53861-111">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="53861-112">Чтобы использовать его, определите структуру, как указано выше, где `CLRDATA_ADDRESS` — это 64-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="53861-112">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="53861-113">Требования</span><span class="sxs-lookup"><span data-stu-id="53861-113">Requirements</span></span>

<span data-ttu-id="53861-114">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53861-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="53861-115">**Заголовок.** Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="53861-115">**Header:** None</span></span>  
<span data-ttu-id="53861-116">**Библиотечная** Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="53861-116">**Library:** None</span></span>  
<span data-ttu-id="53861-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="53861-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="53861-118">См. также</span><span class="sxs-lookup"><span data-stu-id="53861-118">See also</span></span>

- [<span data-ttu-id="53861-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="53861-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="53861-120">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="53861-120">Debugging Structures</span></span>](debugging-structures.md)
