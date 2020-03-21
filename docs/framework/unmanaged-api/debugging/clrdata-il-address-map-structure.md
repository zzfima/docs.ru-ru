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
ms.openlocfilehash: e680a7a0dc3209d1988f6c84be0864572a74b3a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179379"
---
# <a name="clrdata_il_address_map-structure"></a><span data-ttu-id="3679e-102">Структура CLRDATA_IL_ADDRESS_MAP</span><span class="sxs-lookup"><span data-stu-id="3679e-102">CLRDATA_IL_ADDRESS_MAP Structure</span></span>

<span data-ttu-id="3679e-103">Определяет ИЛ для решения картографирования.</span><span class="sxs-lookup"><span data-stu-id="3679e-103">Defines an IL to address mapping.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3679e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3679e-104">Syntax</span></span>

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a><span data-ttu-id="3679e-105">Члены</span><span class="sxs-lookup"><span data-stu-id="3679e-105">Members</span></span>

| <span data-ttu-id="3679e-106">Участник</span><span class="sxs-lookup"><span data-stu-id="3679e-106">Member</span></span>         | <span data-ttu-id="3679e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3679e-107">Description</span></span>                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | <span data-ttu-id="3679e-108">IL смещение для содержащегося диапазона адресов</span><span class="sxs-lookup"><span data-stu-id="3679e-108">IL offset for the contained address range</span></span>              |
| `startAddress` | <span data-ttu-id="3679e-109">Стартовый адрес диапазона.</span><span class="sxs-lookup"><span data-stu-id="3679e-109">The start address of the range.</span></span>                        |
| `endAddress`   | <span data-ttu-id="3679e-110">Конечный адрес диапазона.</span><span class="sxs-lookup"><span data-stu-id="3679e-110">The end address of the range.</span></span>                          |
| `type`         | <span data-ttu-id="3679e-111">Тип данных.</span><span class="sxs-lookup"><span data-stu-id="3679e-111">The type of the data.</span></span> <span data-ttu-id="3679e-112">Это значение в настоящее время не используется</span><span class="sxs-lookup"><span data-stu-id="3679e-112">This value is currently not used</span></span> |

## <a name="remarks"></a><span data-ttu-id="3679e-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="3679e-113">Remarks</span></span>

<span data-ttu-id="3679e-114">Эта структура живет в времени выполнения и не подвергается воздействию каких-либо заголовков или файлов библиотек.</span><span class="sxs-lookup"><span data-stu-id="3679e-114">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="3679e-115">Чтобы использовать его, определите структуру, указанную выше, где `CLRDATA_ADDRESS` находится 64-битный неподписанный целый ряд.</span><span class="sxs-lookup"><span data-stu-id="3679e-115">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="3679e-116">Требования</span><span class="sxs-lookup"><span data-stu-id="3679e-116">Requirements</span></span>

<span data-ttu-id="3679e-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3679e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3679e-118">**Заголовок:** Ни один</span><span class="sxs-lookup"><span data-stu-id="3679e-118">**Header:** None</span></span>  
<span data-ttu-id="3679e-119">**Библиотека:** Нет **рамочных версий .NET:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3679e-119">**Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3679e-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3679e-120">See also</span></span>

- [<span data-ttu-id="3679e-121">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="3679e-121">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="3679e-122">Отладки</span><span class="sxs-lookup"><span data-stu-id="3679e-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="3679e-123">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="3679e-123">Debugging Structures</span></span>](debugging-structures.md)
