---
title: Структура Дакпжетмодулеаддресс
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress Structure
helpviewer.keywords:
- DacpGetModuleAddress Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1e3a62de3259c012438c64ece26e696682ec96e6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789207"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="5b697-102">Структура Дакпжетмодулеаддресс</span><span class="sxs-lookup"><span data-stu-id="5b697-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="5b697-103">Определяет контейнер для запроса адреса модуля.</span><span class="sxs-lookup"><span data-stu-id="5b697-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5b697-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b697-104">Syntax</span></span>

```cpp
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="5b697-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5b697-105">Members</span></span>

| <span data-ttu-id="5b697-106">Член</span><span class="sxs-lookup"><span data-stu-id="5b697-106">Member</span></span>      | <span data-ttu-id="5b697-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5b697-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="5b697-108">Указатель на модуль.</span><span class="sxs-lookup"><span data-stu-id="5b697-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="5b697-109">Методы</span><span class="sxs-lookup"><span data-stu-id="5b697-109">Methods</span></span>

| <span data-ttu-id="5b697-110">Метод</span><span class="sxs-lookup"><span data-stu-id="5b697-110">Method</span></span>                                                                                               | <span data-ttu-id="5b697-111">Описание</span><span class="sxs-lookup"><span data-stu-id="5b697-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="5b697-112">Запрос</span><span class="sxs-lookup"><span data-stu-id="5b697-112">Request</span></span>](dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="5b697-113">Выполняет запрос на заполнение структуры из заданной структуры среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="5b697-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="5b697-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="5b697-114">Remarks</span></span>

<span data-ttu-id="5b697-115">Эта структура находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="5b697-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="5b697-116">Чтобы использовать его, определите структуру, как указано выше, где `CLRDATA_ADDRESS` представляет собой 64-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="5b697-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="5b697-117">Требования</span><span class="sxs-lookup"><span data-stu-id="5b697-117">Requirements</span></span>
<span data-ttu-id="5b697-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b697-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5b697-119">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="5b697-119">**Header:** None</span></span>  
<span data-ttu-id="5b697-120">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="5b697-120">**Library:** None</span></span>  
<span data-ttu-id="5b697-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5b697-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5b697-122">См. также:</span><span class="sxs-lookup"><span data-stu-id="5b697-122">See also</span></span>

- [<span data-ttu-id="5b697-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="5b697-123">Debugging</span></span>](index.md)
- [<span data-ttu-id="5b697-124">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="5b697-124">Debugging Structures</span></span>](debugging-structures.md)
