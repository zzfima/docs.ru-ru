---
title: Интерфейс ISOSDacInterface
ms.date: 01/16/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5e037cf6fb88fff4886733ff4152dca0a827e0a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491032"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="33d82-102">Интерфейс ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="33d82-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="33d82-103">Предоставляет вспомогательные методы для доступа к данным из `SOS`.</span><span class="sxs-lookup"><span data-stu-id="33d82-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="33d82-104">Методы</span><span class="sxs-lookup"><span data-stu-id="33d82-104">Methods</span></span>

| <span data-ttu-id="33d82-105">Метод</span><span class="sxs-lookup"><span data-stu-id="33d82-105">Method</span></span>                                                                                                               | <span data-ttu-id="33d82-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="33d82-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="33d82-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="33d82-107">GetMethodDescData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="33d82-108">Получает данные для заданного [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="33d82-108">Gets the data for the given [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span> |

## <a name="remarks"></a><span data-ttu-id="33d82-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="33d82-109">Remarks</span></span>

<span data-ttu-id="33d82-110">Этот интерфейс находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="33d82-110">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="33d82-111">Однако это COM-интерфейс, наследуемый от `IUnknown` с идентификатором GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` , можно получить с помощью обычных механизмов COM.</span><span class="sxs-lookup"><span data-stu-id="33d82-111">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="33d82-112">Требования</span><span class="sxs-lookup"><span data-stu-id="33d82-112">Requirements</span></span>

<span data-ttu-id="33d82-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33d82-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="33d82-114">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="33d82-114">**Header:** None</span></span>  
<span data-ttu-id="33d82-115">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="33d82-115">**Library:** None</span></span>  
<span data-ttu-id="33d82-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="33d82-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="33d82-117">См. также</span><span class="sxs-lookup"><span data-stu-id="33d82-117">See also</span></span>

- [<span data-ttu-id="33d82-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="33d82-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="33d82-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="33d82-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
