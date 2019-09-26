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
ms.openlocfilehash: 3f6928832d822422177ebd7def142422953468a0
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274293"
---
# <a name="clrdata_il_address_map-structure"></a><span data-ttu-id="21564-102">Структура CLRDATA_IL_ADDRESS_MAP</span><span class="sxs-lookup"><span data-stu-id="21564-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="21564-103">Определяет IL для сопоставления адресов.</span><span class="sxs-lookup"><span data-stu-id="21564-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="21564-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21564-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="21564-105">Участники</span><span class="sxs-lookup"><span data-stu-id="21564-105">Members</span></span>

| <span data-ttu-id="21564-106">Член</span><span class="sxs-lookup"><span data-stu-id="21564-106">Member</span></span>         | <span data-ttu-id="21564-107">Описание</span><span class="sxs-lookup"><span data-stu-id="21564-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="21564-108">Смещение IL для диапазона входящих адресов</span><span class="sxs-lookup"><span data-stu-id="21564-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="21564-109">Начальный адрес диапазона.</span><span class="sxs-lookup"><span data-stu-id="21564-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="21564-110">Конечный адрес диапазона.</span><span class="sxs-lookup"><span data-stu-id="21564-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="21564-111">Тип данных.</span><span class="sxs-lookup"><span data-stu-id="21564-111">The type of the data.</span></span> <span data-ttu-id="21564-112">Это значение в настоящее время не используется</span><span class="sxs-lookup"><span data-stu-id="21564-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="21564-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="21564-113">Remarks</span></span>

<span data-ttu-id="21564-114">Эта структура находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="21564-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="21564-115">Чтобы использовать его, определите структуру, как указано выше, где `CLRDATA_ADDRESS` — это 64-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="21564-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="21564-116">Требования</span><span class="sxs-lookup"><span data-stu-id="21564-116">Requirements</span></span>

<span data-ttu-id="21564-117">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21564-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="21564-118">**Заголовок.** Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="21564-118">**Header:** None</span></span>  
<span data-ttu-id="21564-119">**Библиотечная** Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="21564-119">**Library:** None</span></span>   
<span data-ttu-id="21564-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="21564-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="21564-121">См. также</span><span class="sxs-lookup"><span data-stu-id="21564-121">See also</span></span>

- [<span data-ttu-id="21564-122">Перечисление Клрдатасаурцетипе</span><span class="sxs-lookup"><span data-stu-id="21564-122">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="21564-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="21564-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="21564-124">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="21564-124">Debugging Structures</span></span>](debugging-structures.md)
