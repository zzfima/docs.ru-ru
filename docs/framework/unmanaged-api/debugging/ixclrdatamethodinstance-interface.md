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
ms.openlocfilehash: 0eef69cea9f59911b5076f56579b0192be357431
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659115"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="c0a0c-102">Интерфейс IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="c0a0c-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="c0a0c-103">Предоставляет методы для запроса на получение сведений о экземпляра метода.</span><span class="sxs-lookup"><span data-stu-id="c0a0c-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="c0a0c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c0a0c-104">Methods</span></span>

| <span data-ttu-id="c0a0c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c0a0c-105">Method</span></span>                                                                                                                  | <span data-ttu-id="c0a0c-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="c0a0c-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="c0a0c-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="c0a0c-107">GetILAddressMap</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="c0a0c-108">Возвращает IL для сведений о сопоставлении адрес.</span><span class="sxs-lookup"><span data-stu-id="c0a0c-108">Gets the IL to address mapping information.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c0a0c-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="c0a0c-109">Remarks</span></span>

<span data-ttu-id="c0a0c-110">Этот интерфейс находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="c0a0c-110">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="c0a0c-111">Однако это COM-интерфейс, наследуемый от `IUnknown` с идентификатором GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` , можно получить с помощью обычных механизмов COM.</span><span class="sxs-lookup"><span data-stu-id="c0a0c-111">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="c0a0c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="c0a0c-112">Requirements</span></span>

<span data-ttu-id="c0a0c-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0a0c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="c0a0c-114">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="c0a0c-114">**Header:** None</span></span>  
<span data-ttu-id="c0a0c-115">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="c0a0c-115">**Library:** None</span></span>  
<span data-ttu-id="c0a0c-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c0a0c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c0a0c-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c0a0c-117">See also</span></span>

- [<span data-ttu-id="c0a0c-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="c0a0c-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="c0a0c-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c0a0c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
