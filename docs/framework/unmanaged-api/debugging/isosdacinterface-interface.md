---
title: Интерфейс ISOSDacInterface
ms.date: 02/01/2019
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
ms.openlocfilehash: ccaf479fc4fb90007b4999e95ee03bdd0529321e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922152"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="1750f-102">Интерфейс ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="1750f-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="1750f-103">Предоставляет вспомогательные методы для доступа к данным из `SOS`.</span><span class="sxs-lookup"><span data-stu-id="1750f-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="1750f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="1750f-104">Methods</span></span>

| <span data-ttu-id="1750f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="1750f-105">Method</span></span>                                                                                                               | <span data-ttu-id="1750f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="1750f-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="1750f-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="1750f-107">GetMethodDescData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="1750f-108">Получает данные для заданный указатель MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="1750f-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="1750f-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="1750f-109">GetMethodDescPtrFromIP</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="1750f-110">Извлекает указатель MethodDesc, соответствующий метод, содержащий адрес заданной инструкции машинного кода.</span><span class="sxs-lookup"><span data-stu-id="1750f-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="1750f-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="1750f-111">GetModuleData</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="1750f-112">Извлекает данные, соответствующие модуль загружен по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="1750f-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="1750f-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="1750f-113">Remarks</span></span>

<span data-ttu-id="1750f-114">Этот интерфейс находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="1750f-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="1750f-115">Однако это COM-интерфейс, наследуемый от `IUnknown` с идентификатором GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` , можно получить с помощью обычных механизмов COM.</span><span class="sxs-lookup"><span data-stu-id="1750f-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="1750f-116">Требования</span><span class="sxs-lookup"><span data-stu-id="1750f-116">Requirements</span></span>

<span data-ttu-id="1750f-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1750f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="1750f-118">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="1750f-118">**Header:** None</span></span>  
<span data-ttu-id="1750f-119">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="1750f-119">**Library:** None</span></span>  
<span data-ttu-id="1750f-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1750f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1750f-121">См. также</span><span class="sxs-lookup"><span data-stu-id="1750f-121">See also</span></span>

- [<span data-ttu-id="1750f-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="1750f-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="1750f-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="1750f-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
