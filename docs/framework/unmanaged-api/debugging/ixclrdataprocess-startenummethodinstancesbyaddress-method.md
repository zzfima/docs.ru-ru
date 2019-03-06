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
ms.openlocfilehash: 8d0494e53705493de814ed4d4caa869e1e8a700f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374574"
---
# <a name="ixclrdataprocessstartenummethodinstancesbyaddress-method"></a><span data-ttu-id="a6a62-102">Метод IXCLRDataProcess::StartEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="a6a62-102">IXCLRDataProcess::StartEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="a6a62-103">Предоставляет дескриптор для перечисления экземпляров метод `AppDomain` начиная с данного адреса.</span><span class="sxs-lookup"><span data-stu-id="a6a62-103">Provides a handle to enumerate the method instances of `AppDomain` starting at a given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a6a62-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6a62-104">Syntax</span></span>

```
HRESULT StartEnumMethodInstancesByAddress(
    [in] CLRDATA_ADDRESS     address,
    [in] IXCLRDataAppDomain *appDomain,
    [out] CLRDATA_ENUM      *handle
);
```

### <a name="parameters"></a><span data-ttu-id="a6a62-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a6a62-105">Parameters</span></span>

`address`\
<span data-ttu-id="a6a62-106">[in] Адрес первого экземпляра метода.</span><span class="sxs-lookup"><span data-stu-id="a6a62-106">[in] The address of the first method instance.</span></span>

`appDomain`\
<span data-ttu-id="a6a62-107">[in] Домен приложения экземпляров метода.</span><span class="sxs-lookup"><span data-stu-id="a6a62-107">[in] The AppDomain of the method instances.</span></span>

`handle`\
<span data-ttu-id="a6a62-108">[out] Дескриптор для перечисления экземпляров метода.</span><span class="sxs-lookup"><span data-stu-id="a6a62-108">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="a6a62-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="a6a62-109">Remarks</span></span>

<span data-ttu-id="a6a62-110">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 27 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="a6a62-110">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 27th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="a6a62-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a6a62-111">Requirements</span></span>

<span data-ttu-id="a6a62-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6a62-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a6a62-113">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="a6a62-113">**Header:** None</span></span>  
<span data-ttu-id="a6a62-114">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="a6a62-114">**Library:** None</span></span>  
<span data-ttu-id="a6a62-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a6a62-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a6a62-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a6a62-116">See also</span></span>

- [<span data-ttu-id="a6a62-117">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="a6a62-117">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="a6a62-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="a6a62-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="a6a62-119">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="a6a62-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
