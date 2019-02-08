---
title: Интерфейс IXCLRDataMethodInstance
ms.date: 02/01/2019
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
ms.openlocfilehash: 7185802a3857fcd73c63d097090a2a7809f65279
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825931"
---
# <a name="ixclrdatamethodinstance-interface"></a><span data-ttu-id="04521-102">Интерфейс IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="04521-102">IXCLRDataMethodInstance Interface</span></span>

<span data-ttu-id="04521-103">Предоставляет методы для запроса на получение сведений о экземпляра метода.</span><span class="sxs-lookup"><span data-stu-id="04521-103">Provides methods for querying information about a method instance.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="04521-104">Методы</span><span class="sxs-lookup"><span data-stu-id="04521-104">Methods</span></span>

| <span data-ttu-id="04521-105">Метод</span><span class="sxs-lookup"><span data-stu-id="04521-105">Method</span></span>                                                                                                                  | <span data-ttu-id="04521-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="04521-106">Description</span></span>                                 |
| ----------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| [<span data-ttu-id="04521-107">GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="04521-107">GetILAddressMap</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getiladdressmap-method.md) | <span data-ttu-id="04521-108">Возвращает IL для сведений о сопоставлении адрес.</span><span class="sxs-lookup"><span data-stu-id="04521-108">Gets the IL to address mapping information.</span></span> |
| [<span data-ttu-id="04521-109">GetRepresentativeEntryAddress</span><span class="sxs-lookup"><span data-stu-id="04521-109">GetRepresentativeEntryAddress</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-getrepresentativeentryaddress-method.md) | <span data-ttu-id="04521-110">Получает наиболее характерные адрес точки входа для компиляция в собственном коде все возможные точки входа для метода...</span><span class="sxs-lookup"><span data-stu-id="04521-110">Gets the most representative entry point address for the native compilation of all the possible entry points for a method..</span></span> |


## <a name="remarks"></a><span data-ttu-id="04521-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="04521-111">Remarks</span></span>

<span data-ttu-id="04521-112">Этот интерфейс находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="04521-112">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="04521-113">Однако это COM-интерфейс, наследуемый от `IUnknown` с идентификатором GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` , можно получить с помощью обычных механизмов COM.</span><span class="sxs-lookup"><span data-stu-id="04521-113">However, it's a COM interface that derives from `IUnknown` with GUID `ECD73800-22CA-4b0d-AB55-E9BA7E6318A5` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="04521-114">Требования</span><span class="sxs-lookup"><span data-stu-id="04521-114">Requirements</span></span>

<span data-ttu-id="04521-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04521-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="04521-116">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="04521-116">**Header:** None</span></span>  
<span data-ttu-id="04521-117">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="04521-117">**Library:** None</span></span>  
<span data-ttu-id="04521-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="04521-118">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="04521-119">См. также</span><span class="sxs-lookup"><span data-stu-id="04521-119">See also</span></span>

- [<span data-ttu-id="04521-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="04521-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="04521-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="04521-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
