---
title: Перечисление CLRDataSourceType
ms.date: 01/16/2019
api.name:
- CLRDataSourceType Enumeration
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDataSourceType Enumeration
helpviewer.keywords:
- CLRDataSourceType Enumeration [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: d26cf45a0243d61757af5d9d0c00cf135ae15bdf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740869"
---
# <a name="clrdatasourcetype-enumeration"></a><span data-ttu-id="18902-102">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="18902-102">CLRDataSourceType Enumeration</span></span>

<span data-ttu-id="18902-103">Предоставляет значения, которые используются в структуре CLRDATA_IL_ADDRESS_MAP.</span><span class="sxs-lookup"><span data-stu-id="18902-103">Provides values that are used by the CLRDATA_IL_ADDRESS_MAP structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="18902-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18902-104">Syntax</span></span>

```cpp
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a><span data-ttu-id="18902-105">Участники</span><span class="sxs-lookup"><span data-stu-id="18902-105">Members</span></span>

| <span data-ttu-id="18902-106">Член</span><span class="sxs-lookup"><span data-stu-id="18902-106">Member</span></span>                        | <span data-ttu-id="18902-107">Описание</span><span class="sxs-lookup"><span data-stu-id="18902-107">Description</span></span>                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | <span data-ttu-id="18902-108">Чтобы указать, что ничего применяется</span><span class="sxs-lookup"><span data-stu-id="18902-108">To indicate that nothing else applies</span></span> |

## <a name="remarks"></a><span data-ttu-id="18902-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="18902-109">Remarks</span></span>

<span data-ttu-id="18902-110">Это перечисление находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="18902-110">This enumeration lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="18902-111">Чтобы использовать его, определите перечисление, как указано выше, в коде.</span><span class="sxs-lookup"><span data-stu-id="18902-111">To use it, define an enumeration as defined above in your code.</span></span> <span data-ttu-id="18902-112">Это также псевдонимом `CLRDATA_ENUM` как уже упоминалось в [общие типы данных](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="18902-112">This is also aliased to `CLRDATA_ENUM` as mentioned in [Common Data Types](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="18902-113">Требования</span><span class="sxs-lookup"><span data-stu-id="18902-113">Requirements</span></span>

<span data-ttu-id="18902-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18902-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="18902-115">**Заголовок.** None</span><span class="sxs-lookup"><span data-stu-id="18902-115">**Header:** None</span></span>  
<span data-ttu-id="18902-116">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="18902-116">**Library:** None</span></span>  
<span data-ttu-id="18902-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="18902-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="18902-118">См. также</span><span class="sxs-lookup"><span data-stu-id="18902-118">See also</span></span>

- [<span data-ttu-id="18902-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="18902-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="18902-120">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="18902-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
