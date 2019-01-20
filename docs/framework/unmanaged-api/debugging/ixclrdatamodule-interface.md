---
title: Интерфейс IXCLRDataModule
ms.date: 01/16/2019
api.name:
- IXCLRDataModule Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule Interface
helpviewer.keywords:
- IXCLRDataModule Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: e306834166051ae48fd283d51f18d9458091578f
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416664"
---
# <a name="ixclrdatamodule-interface"></a><span data-ttu-id="823dd-102">Интерфейс IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="823dd-102">IXCLRDataModule Interface</span></span>

<span data-ttu-id="823dd-103">Предоставляет методы для запроса на получение сведений о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="823dd-103">Provides methods for querying information about a loaded module.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="823dd-104">Методы</span><span class="sxs-lookup"><span data-stu-id="823dd-104">Methods</span></span>

| <span data-ttu-id="823dd-105">Метод</span><span class="sxs-lookup"><span data-stu-id="823dd-105">Method</span></span>                                                                                                                                | <span data-ttu-id="823dd-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="823dd-106">Description</span></span>                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="823dd-107">GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="823dd-107">GetMethodDefinitionByToken</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-getmethoddefinitionbytoken-method.md) | <span data-ttu-id="823dd-108">Возвращает определение метода, соответствующей токену метаданных.</span><span class="sxs-lookup"><span data-stu-id="823dd-108">Gets the method definition corresponding to a given metadata token.</span></span> |
| [<span data-ttu-id="823dd-109">Запрос</span><span class="sxs-lookup"><span data-stu-id="823dd-109">Request</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-request-method.md)                                       | <span data-ttu-id="823dd-110">Запросы, чтобы заполнить буфер с данными модуля.</span><span class="sxs-lookup"><span data-stu-id="823dd-110">Requests to populate the buffer given with the module's data.</span></span>       |
| [<span data-ttu-id="823dd-111">GetVersionId</span><span class="sxs-lookup"><span data-stu-id="823dd-111">GetVersionId</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-getversionid-method.md)                             | <span data-ttu-id="823dd-112">Получает идентификатор версии модуля.</span><span class="sxs-lookup"><span data-stu-id="823dd-112">Gets the module's version ID.</span></span>                                       |

## <a name="remarks"></a><span data-ttu-id="823dd-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="823dd-113">Remarks</span></span>

<span data-ttu-id="823dd-114">Этот интерфейс находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="823dd-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="823dd-115">Однако это COM-интерфейс, наследуемый от `IUnknown` с идентификатором GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` , можно получить с помощью обычных механизмов COM.</span><span class="sxs-lookup"><span data-stu-id="823dd-115">However, it's a COM interface that derives from `IUnknown` with GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="823dd-116">Требования</span><span class="sxs-lookup"><span data-stu-id="823dd-116">Requirements</span></span>

<span data-ttu-id="823dd-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="823dd-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="823dd-118">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="823dd-118">**Header:** None</span></span>  
<span data-ttu-id="823dd-119">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="823dd-119">**Library:** None</span></span>  
<span data-ttu-id="823dd-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="823dd-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="823dd-121">См. также</span><span class="sxs-lookup"><span data-stu-id="823dd-121">See Also</span></span>

- [<span data-ttu-id="823dd-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="823dd-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="823dd-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="823dd-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
