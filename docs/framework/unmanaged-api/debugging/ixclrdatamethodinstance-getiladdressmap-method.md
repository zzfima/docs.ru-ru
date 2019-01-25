---
title: Метод IXCLRDataMethodInstance::GetILAddressMap
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodInstance::GetILAddressMap Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method
helpviewer.keywords:
- IXCLRDataMethodInstance::GetILAddressMap Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 8442d1373ede241d262ab41928fd5d9924ec9c80
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567195"
---
# <a name="ixclrdatamethodinstancegetiladdressmap-method"></a><span data-ttu-id="945f4-102">Метод IXCLRDataMethodInstance::GetILAddressMap</span><span class="sxs-lookup"><span data-stu-id="945f4-102">IXCLRDataMethodInstance::GetILAddressMap Method</span></span>

<span data-ttu-id="945f4-103">Возвращает IL для сведений о сопоставлении адрес.</span><span class="sxs-lookup"><span data-stu-id="945f4-103">Gets the IL to address mapping information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="945f4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="945f4-104">Syntax</span></span>

```
HRESULT GetILAddressMap(
    [in] ULONG32                                   mapLen,
    [out] ULONG32                                 *mapNeeded,
    [out, size_is(mapLen)] CLRDATA_IL_ADDRESS_MAP  maps[]
);
```

### <a name="parameters"></a><span data-ttu-id="945f4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="945f4-105">Parameters</span></span>

<span data-ttu-id="945f4-106">`mapLen` [in] Длина массива предоставленного сопоставления.</span><span class="sxs-lookup"><span data-stu-id="945f4-106">`mapLen` [in] The length of the provided maps array.</span></span>

<span data-ttu-id="945f4-107">`mapNeeded` [out] Число записей карты, необходимые для метода.</span><span class="sxs-lookup"><span data-stu-id="945f4-107">`mapNeeded` [out] The number of map entries that the method needs.</span></span>

<span data-ttu-id="945f4-108">`maps` [out, size_is(mapLen)] Массив для хранения записей карты.</span><span class="sxs-lookup"><span data-stu-id="945f4-108">`maps` [out, size_is(mapLen)] The array for storing the map entries.</span></span>

## <a name="remarks"></a><span data-ttu-id="945f4-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="945f4-109">Remarks</span></span>

<span data-ttu-id="945f4-110">Указанный метод является частью `IXCLRDataMethodInstance` интерфейса и соответствует 14 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="945f4-110">The provided method is part of the `IXCLRDataMethodInstance` interface and corresponds to the 14th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="945f4-111">Требования</span><span class="sxs-lookup"><span data-stu-id="945f4-111">Requirements</span></span>

<span data-ttu-id="945f4-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="945f4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="945f4-113">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="945f4-113">**Header:** None</span></span>  
<span data-ttu-id="945f4-114">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="945f4-114">**Library:** None</span></span>  
<span data-ttu-id="945f4-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="945f4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="945f4-116">См. также</span><span class="sxs-lookup"><span data-stu-id="945f4-116">See also</span></span>

- [<span data-ttu-id="945f4-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="945f4-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="945f4-118">Интерфейс IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="945f4-118">IXCLRDataMethodInstance Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)
