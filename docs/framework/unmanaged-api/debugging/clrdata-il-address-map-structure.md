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
ms.openlocfilehash: 94ebef007cf2893b63383aa4657d382728d3c759
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416537"
---
# <a name="clrdatailaddressmap-structure"></a><span data-ttu-id="b9fc8-102">Структура CLRDATA_IL_ADDRESS_MAP</span><span class="sxs-lookup"><span data-stu-id="b9fc8-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="b9fc8-103">Определяет сопоставление адресов IL.</span><span class="sxs-lookup"><span data-stu-id="b9fc8-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b9fc8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9fc8-104">Syntax</span></span>

```
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="b9fc8-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b9fc8-105">Members</span></span>

| <span data-ttu-id="b9fc8-106">Член</span><span class="sxs-lookup"><span data-stu-id="b9fc8-106">Member</span></span>         | <span data-ttu-id="b9fc8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b9fc8-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="b9fc8-108">Смещение на промежуточном Языке автономной диапазона</span><span class="sxs-lookup"><span data-stu-id="b9fc8-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="b9fc8-109">Начальный адрес диапазона.</span><span class="sxs-lookup"><span data-stu-id="b9fc8-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="b9fc8-110">Конечный адрес диапазона.</span><span class="sxs-lookup"><span data-stu-id="b9fc8-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="b9fc8-111">Тип данных.</span><span class="sxs-lookup"><span data-stu-id="b9fc8-111">The type of the data.</span></span> <span data-ttu-id="b9fc8-112">Это значение в настоящее время не используется</span><span class="sxs-lookup"><span data-stu-id="b9fc8-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="b9fc8-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="b9fc8-113">Remarks</span></span>

<span data-ttu-id="b9fc8-114">Эта структура находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="b9fc8-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="b9fc8-115">Чтобы использовать его, определить структуру как указано выше, где `CLRDATA_ADDRESS` является 64-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="b9fc8-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="b9fc8-116">Требования</span><span class="sxs-lookup"><span data-stu-id="b9fc8-116">Requirements</span></span>

<span data-ttu-id="b9fc8-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9fc8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b9fc8-118">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="b9fc8-118">**Header:** None</span></span>  
<span data-ttu-id="b9fc8-119">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="b9fc8-119">**Library:** None</span></span>   
<span data-ttu-id="b9fc8-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b9fc8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b9fc8-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b9fc8-121">See Also</span></span>

- [<span data-ttu-id="b9fc8-122">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="b9fc8-122">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="b9fc8-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="b9fc8-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="b9fc8-124">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="b9fc8-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
