---
title: Структура DacpGetModuleAddress
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
ms.openlocfilehash: cbea6c0562c68ae5d18247dc97bc53eb9dfbfd7e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965949"
---
# <a name="dacpgetmoduleaddress-structure"></a><span data-ttu-id="b4334-102">Структура DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="b4334-102">DacpGetModuleAddress Structure</span></span>

<span data-ttu-id="b4334-103">Определяет контейнер для запроса адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="b4334-103">Defines the container for a module address request.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b4334-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4334-104">Syntax</span></span>

```
struct DacpGetModuleAddress
{
    CLRDATA_ADDRESS ModulePtr;
};
```

## <a name="members"></a><span data-ttu-id="b4334-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b4334-105">Members</span></span>

| <span data-ttu-id="b4334-106">Член</span><span class="sxs-lookup"><span data-stu-id="b4334-106">Member</span></span>      | <span data-ttu-id="b4334-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b4334-107">Description</span></span>                |
| ----------- | -------------------------- |
| `ModulePtr` | <span data-ttu-id="b4334-108">Указатель на модуль.</span><span class="sxs-lookup"><span data-stu-id="b4334-108">The pointer to the module.</span></span> |

## <a name="methods"></a><span data-ttu-id="b4334-109">Методы</span><span class="sxs-lookup"><span data-stu-id="b4334-109">Methods</span></span>

| <span data-ttu-id="b4334-110">Метод</span><span class="sxs-lookup"><span data-stu-id="b4334-110">Method</span></span>                                                                                               | <span data-ttu-id="b4334-111">Описание</span><span class="sxs-lookup"><span data-stu-id="b4334-111">Description</span></span>                                                                    |
| ---------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| [<span data-ttu-id="b4334-112">Запрос</span><span class="sxs-lookup"><span data-stu-id="b4334-112">Request</span></span>](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-request-method.md) | <span data-ttu-id="b4334-113">Выполняет запрос для заполнения структуры из структуры данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b4334-113">Performs a request to populate the structure from the given runtime structure.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b4334-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="b4334-114">Remarks</span></span>

<span data-ttu-id="b4334-115">Эта структура находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="b4334-115">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="b4334-116">Чтобы использовать его, определить структуру как указано выше, где `CLRDATA_ADDRESS` является 64-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="b4334-116">To use it, define the structure as specified above, where `CLRDATA_ADDRESS` is a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="b4334-117">Требования</span><span class="sxs-lookup"><span data-stu-id="b4334-117">Requirements</span></span>
<span data-ttu-id="b4334-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4334-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b4334-119">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="b4334-119">**Header:** None</span></span>  
<span data-ttu-id="b4334-120">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="b4334-120">**Library:** None</span></span>  
<span data-ttu-id="b4334-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b4334-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b4334-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b4334-122">See also</span></span>

- [<span data-ttu-id="b4334-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="b4334-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="b4334-124">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="b4334-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
