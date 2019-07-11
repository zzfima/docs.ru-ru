---
title: Структура CLRDATA_IL_ADDRESS_MAP
ms.date: 01/16/2019
api.name:
- CLRDATA_IL_ADDRESS_MAP Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure
helpviewer.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 2f34ae3e6687027aeb75e7ea169487fc8cbda466
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741032"
---
# <a name="clrdatailaddressmap-structure"></a><span data-ttu-id="765f0-102">Структура CLRDATA_IL_ADDRESS_MAP</span><span class="sxs-lookup"><span data-stu-id="765f0-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="765f0-103">Определяет сопоставление адресов IL.</span><span class="sxs-lookup"><span data-stu-id="765f0-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="765f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="765f0-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="765f0-105">Участники</span><span class="sxs-lookup"><span data-stu-id="765f0-105">Members</span></span>

| <span data-ttu-id="765f0-106">Член</span><span class="sxs-lookup"><span data-stu-id="765f0-106">Member</span></span>         | <span data-ttu-id="765f0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="765f0-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="765f0-108">Смещение на промежуточном Языке автономной диапазона</span><span class="sxs-lookup"><span data-stu-id="765f0-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="765f0-109">Начальный адрес диапазона.</span><span class="sxs-lookup"><span data-stu-id="765f0-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="765f0-110">Конечный адрес диапазона.</span><span class="sxs-lookup"><span data-stu-id="765f0-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="765f0-111">Тип данных.</span><span class="sxs-lookup"><span data-stu-id="765f0-111">The type of the data.</span></span> <span data-ttu-id="765f0-112">Это значение в настоящее время не используется</span><span class="sxs-lookup"><span data-stu-id="765f0-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="765f0-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="765f0-113">Remarks</span></span>

<span data-ttu-id="765f0-114">Эта структура находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="765f0-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="765f0-115">Чтобы использовать его, определить структуру как указано выше, где `CLRDATA_ADDRESS` является 64-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="765f0-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="765f0-116">Требования</span><span class="sxs-lookup"><span data-stu-id="765f0-116">Requirements</span></span>

<span data-ttu-id="765f0-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="765f0-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="765f0-118">**Заголовок.** None</span><span class="sxs-lookup"><span data-stu-id="765f0-118">**Header:** None</span></span>  
<span data-ttu-id="765f0-119">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="765f0-119">**Library:** None</span></span>   
<span data-ttu-id="765f0-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="765f0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="765f0-121">См. также</span><span class="sxs-lookup"><span data-stu-id="765f0-121">See also</span></span>

- [<span data-ttu-id="765f0-122">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="765f0-122">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="765f0-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="765f0-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="765f0-124">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="765f0-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
