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
ms.openlocfilehash: 88ce9dd928871d71058fe28c243a9fb51b729778
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416687"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="9b951-102">Метод IXCLRDataProcess::StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="9b951-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="9b951-103">Предоставляет дескриптор для перечисления экземпляров метод `AppDomain` начиная с данного адреса.</span><span class="sxs-lookup"><span data-stu-id="9b951-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9b951-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b951-104">Syntax</span></span>

```
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

### <a name="parameters"></a><span data-ttu-id="9b951-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9b951-105">Parameters</span></span>

<span data-ttu-id="9b951-106">`address` [in] Адрес первого экземпляра метода.</span><span class="sxs-lookup"><span data-stu-id="9b951-106">`address` [in] The address of the first method instance.</span></span>

<span data-ttu-id="9b951-107">`appDomain` [in] Домен приложения экземпляров метода.</span><span class="sxs-lookup"><span data-stu-id="9b951-107">`appDomain` [in] The AppDomain of the method instances.</span></span>

<span data-ttu-id="9b951-108">`handle` [out] Дескриптор для перечисления экземпляров метода.</span><span class="sxs-lookup"><span data-stu-id="9b951-108">`handle` [out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="9b951-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="9b951-109">Remarks</span></span>

<span data-ttu-id="9b951-110">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 27 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="9b951-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 27th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="9b951-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9b951-111">Requirements</span></span>

<span data-ttu-id="9b951-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b951-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9b951-113">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="9b951-113">**Header:** None</span></span>  
<span data-ttu-id="9b951-114">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="9b951-114">**Library:** None</span></span>  
<span data-ttu-id="9b951-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9b951-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9b951-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9b951-116">See Also</span></span>

- [<span data-ttu-id="9b951-117">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="9b951-117">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="9b951-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="9b951-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="9b951-119">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="9b951-119">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
