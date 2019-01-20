---
title: Метод IXCLRDataMethodDefinition::EnumInstance
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 420acda89858713f12ea87a8c8d3909682a3f5e3
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416727"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="779ba-102">Метод IXCLRDataMethodDefinition::EnumInstance</span><span class="sxs-lookup"><span data-stu-id="779ba-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="779ba-103">Перечисление экземпляров класса определения метода.</span><span class="sxs-lookup"><span data-stu-id="779ba-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="779ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="779ba-104">Syntax</span></span>

```
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

### <a name="parameters"></a><span data-ttu-id="779ba-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="779ba-105">Parameters</span></span>

<span data-ttu-id="779ba-106">`handle` [in, out] Дескриптор для перечисления экземпляров.</span><span class="sxs-lookup"><span data-stu-id="779ba-106">`handle` [in, out] A handle for enumerating the instances.</span></span>

<span data-ttu-id="779ba-107">`instance` [out] Экземпляр перечисления.</span><span class="sxs-lookup"><span data-stu-id="779ba-107">`instance` [out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="779ba-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="779ba-108">Remarks</span></span>

<span data-ttu-id="779ba-109">Указанный метод является частью `IXCLRDataMethodDefinition` интерфейса и соответствует четвертый слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="779ba-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="779ba-110">Требования</span><span class="sxs-lookup"><span data-stu-id="779ba-110">Requirements</span></span>

<span data-ttu-id="779ba-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="779ba-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="779ba-112">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="779ba-112">**Header:** None</span></span>  
<span data-ttu-id="779ba-113">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="779ba-113">**Library:** None</span></span>  
<span data-ttu-id="779ba-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="779ba-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="779ba-115">См. также</span><span class="sxs-lookup"><span data-stu-id="779ba-115">See Also</span></span>

- [<span data-ttu-id="779ba-116">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="779ba-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="779ba-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="779ba-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="779ba-118">Интерфейс IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="779ba-118">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="779ba-119">Интерфейс IXCLRDataMethodInstance</span><span class="sxs-lookup"><span data-stu-id="779ba-119">IXCLRDataMethodInstance Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethodinstance-interface.md)
