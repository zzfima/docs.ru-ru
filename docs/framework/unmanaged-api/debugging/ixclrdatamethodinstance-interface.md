---
title: Интерфейс IXCLRDataMethodInstance
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance Interface
helpviewer.keywords:
- IXCLRDataMethodInstance Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 5bf724bc76591ae59c073b5b9a788ca065f51dc0
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416527"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="8e3bc-102">Интерфейс IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="8e3bc-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="8e3bc-103">Предоставляет методы для запроса на получение сведений о экземпляра метода.</span><span class="sxs-lookup"><span data-stu-id="8e3bc-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="8e3bc-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8e3bc-104">Methods</span></span>

| <span data-ttu-id="8e3bc-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8e3bc-105">Method</span></span>                                                                                                                  | <span data-ttu-id="8e3bc-106">Описание</span><span class="sxs-lookup"><span data-stu-id="8e3bc-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="8e3bc-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="8e3bc-107">GetILAddressMap</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="8e3bc-108">Возвращает IL для сведений о сопоставлении адрес.</span><span class="sxs-lookup"><span data-stu-id="8e3bc-108">Gets the IL to address mapping information.</span></span> |

## <a name="remarks"></a><span data-ttu-id="8e3bc-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="8e3bc-109">Remarks</span></span>

<span data-ttu-id="8e3bc-110">Этот интерфейс находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="8e3bc-110">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="8e3bc-111">Однако это COM-интерфейс, наследуемый от `IUnknown` с идентификатором GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` , можно получить с помощью обычных механизмов COM.</span><span class="sxs-lookup"><span data-stu-id="8e3bc-111">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="8e3bc-112">Требования</span><span class="sxs-lookup"><span data-stu-id="8e3bc-112">Requirements</span></span>

<span data-ttu-id="8e3bc-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e3bc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8e3bc-114">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="8e3bc-114">**Header:** None</span></span>  
<span data-ttu-id="8e3bc-115">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="8e3bc-115">**Library:** None</span></span>  
<span data-ttu-id="8e3bc-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8e3bc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8e3bc-117">См. также</span><span class="sxs-lookup"><span data-stu-id="8e3bc-117">See Also</span></span>

- [<span data-ttu-id="8e3bc-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="8e3bc-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="8e3bc-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8e3bc-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
