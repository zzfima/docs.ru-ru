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
ms.openlocfilehash: 28cd15a793d303e1d6e64c52c1d0095e8d619c7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789705"
---
# <a name="ixclrdatamethoddefinitionendenuminstances-method"></a><span data-ttu-id="a2429-102">Метод IXCLRDataMethodDefinition::EndEnumInstances</span><span class="sxs-lookup"><span data-stu-id="a2429-102">IXCLRDataMethodDefinition::EndEnumInstances Method</span></span>

<span data-ttu-id="a2429-103">Освобождает ресурсы, используемые внутренней итераторы, используется в процессе экземпляра перечисления.</span><span class="sxs-lookup"><span data-stu-id="a2429-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a2429-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2429-104">Syntax</span></span>

```
HRESULT EndEnumInstances(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="a2429-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a2429-105">Parameters</span></span>

`handle`\
<span data-ttu-id="a2429-106">[out] Дескриптор для перечисления экземпляров.</span><span class="sxs-lookup"><span data-stu-id="a2429-106">[out] A handle for enumerating the instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="a2429-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="a2429-107">Remarks</span></span>

<span data-ttu-id="a2429-108">Указанный метод является частью `IXCLRDataMethodDefinition` интерфейса и соответствует пятый слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="a2429-108">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fifth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="a2429-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a2429-109">Requirements</span></span>

<span data-ttu-id="a2429-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2429-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a2429-111">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="a2429-111">**Header:** None</span></span>  
<span data-ttu-id="a2429-112">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="a2429-112">**Library:** None</span></span>  
<span data-ttu-id="a2429-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a2429-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a2429-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a2429-114">See also</span></span>

- [<span data-ttu-id="a2429-115">Отладка</span><span class="sxs-lookup"><span data-stu-id="a2429-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="a2429-116">Интерфейс IXCLRDataMethodDefinition</span><span class="sxs-lookup"><span data-stu-id="a2429-116">IXCLRDataMethodDefinition Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamethoddefinition-interface.md)
