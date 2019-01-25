---
title: Метод IXCLRDataProcess::StartEnumMethodInstancesByAddress
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 9afbf0665b114169661a74b60c744203d160fed3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662625"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="658f9-102">Метод IXCLRDataProcess::StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="658f9-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="658f9-103">Предоставляет дескриптор для перечисления экземпляров метод `AppDomain` начиная с данного адреса.</span><span class="sxs-lookup"><span data-stu-id="658f9-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="658f9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="658f9-104">Syntax</span></span>

```
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

### <a name="parameters"></a><span data-ttu-id="658f9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="658f9-105">Parameters</span></span>

<span data-ttu-id="658f9-106">`address` [in] Адрес первого экземпляра метода.</span><span class="sxs-lookup"><span data-stu-id="658f9-106">`address` [in] The address of the first method instance.</span></span>

<span data-ttu-id="658f9-107">`appDomain` [in] Домен приложения экземпляров метода.</span><span class="sxs-lookup"><span data-stu-id="658f9-107">`appDomain` [in] The AppDomain of the method instances.</span></span>

<span data-ttu-id="658f9-108">`handle` [out] Дескриптор для перечисления экземпляров метода.</span><span class="sxs-lookup"><span data-stu-id="658f9-108">`handle` [out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="658f9-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="658f9-109">Remarks</span></span>

<span data-ttu-id="658f9-110">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 27 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="658f9-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 27th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="658f9-111">Требования</span><span class="sxs-lookup"><span data-stu-id="658f9-111">Requirements</span></span>

<span data-ttu-id="658f9-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="658f9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="658f9-113">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="658f9-113">**Header:** None</span></span>  
<span data-ttu-id="658f9-114">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="658f9-114">**Library:** None</span></span>  
<span data-ttu-id="658f9-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="658f9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="658f9-116">См. также</span><span class="sxs-lookup"><span data-stu-id="658f9-116">See also</span></span>

- [<span data-ttu-id="658f9-117">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="658f9-117">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="658f9-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="658f9-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="658f9-119">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="658f9-119">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
