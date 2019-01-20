---
title: Метод IXCLRDataProcess::EndEnumModules
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: cd49ae5fa274c577cfa3c04ec599e488384dfc64
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416657"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="656fa-102">Метод IXCLRDataProcess::EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="656fa-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="656fa-103">Освобождает ресурсы, используемые внутренней итераторы, используемые при перечислении модуля.</span><span class="sxs-lookup"><span data-stu-id="656fa-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="656fa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="656fa-104">Syntax</span></span>
```
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a><span data-ttu-id="656fa-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="656fa-105">Parameters</span></span>
<span data-ttu-id="656fa-106">`handle` [out] Дескриптор для перечисления модули.</span><span class="sxs-lookup"><span data-stu-id="656fa-106">`handle` [out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="656fa-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="656fa-107">Remarks</span></span>

<span data-ttu-id="656fa-108">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 26 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="656fa-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="656fa-109">Требования</span><span class="sxs-lookup"><span data-stu-id="656fa-109">Requirements</span></span>

<span data-ttu-id="656fa-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="656fa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="656fa-111">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="656fa-111">**Header:** None</span></span>   
<span data-ttu-id="656fa-112">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="656fa-112">**Library:** None</span></span>   
<span data-ttu-id="656fa-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="656fa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   

## <a name="see-also"></a><span data-ttu-id="656fa-114">См. также</span><span class="sxs-lookup"><span data-stu-id="656fa-114">See Also</span></span>

- [<span data-ttu-id="656fa-115">Отладка</span><span class="sxs-lookup"><span data-stu-id="656fa-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="656fa-116">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="656fa-116">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
