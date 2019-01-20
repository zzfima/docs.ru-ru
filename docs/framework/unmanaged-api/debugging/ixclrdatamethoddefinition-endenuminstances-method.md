---
title: Метод IXCLRDataMethodDefinition::EndEnumInstances
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EndEnumInstances Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EndEnumInstances Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7901ba3ac95052e265df619d06996b4c9ce8baa6
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416554"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="78d2d-102">Метод IXCLRDataMethodDefinition::EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="78d2d-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="78d2d-103">Освобождает ресурсы, используемые внутренней итераторы, используется в процессе экземпляра перечисления.</span><span class="sxs-lookup"><span data-stu-id="78d2d-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="78d2d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78d2d-104">Syntax</span></span>

```
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a><span data-ttu-id="78d2d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="78d2d-105">Parameters</span></span>

<span data-ttu-id="78d2d-106">`handle` [out] Дескриптор для перечисления экземпляров.</span><span class="sxs-lookup"><span data-stu-id="78d2d-106">`handle` [out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="78d2d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="78d2d-107">Remarks</span></span>

<span data-ttu-id="78d2d-108">Указанный метод является частью `IXCLRDataMethodDefinition` интерфейса и соответствует пятый слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="78d2d-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fifth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="78d2d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="78d2d-109">Requirements</span></span>

<span data-ttu-id="78d2d-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78d2d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="78d2d-111">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="78d2d-111">**Header:** None</span></span>  
<span data-ttu-id="78d2d-112">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="78d2d-112">**Library:** None</span></span>  
<span data-ttu-id="78d2d-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="78d2d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="78d2d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="78d2d-114">See Also</span></span>

- [<span data-ttu-id="78d2d-115">Отладка</span><span class="sxs-lookup"><span data-stu-id="78d2d-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="78d2d-116">Интерфейс IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="78d2d-116">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
