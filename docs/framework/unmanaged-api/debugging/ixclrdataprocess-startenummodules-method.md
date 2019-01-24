---
title: Метод IXCLRDataProcess::StartEnumModules
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::StartEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::StartEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::StartEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 4a086157b27b7426cb6d5f17f13426c0f26d2b2d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658225"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="ccc78-102">Метод IXCLRDataProcess::StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="ccc78-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="ccc78-103">Предоставляет маркер, чтобы перечислить модули, процесса.</span><span class="sxs-lookup"><span data-stu-id="ccc78-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="ccc78-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ccc78-104">Syntax</span></span>

```
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

### <a name="parameters"></a><span data-ttu-id="ccc78-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ccc78-105">Parameters</span></span>

<span data-ttu-id="ccc78-106">`handle` [out] Дескриптор для перечисления модули.</span><span class="sxs-lookup"><span data-stu-id="ccc78-106">`handle` [out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="ccc78-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="ccc78-107">Remarks</span></span>

<span data-ttu-id="ccc78-108">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 24 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="ccc78-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="ccc78-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ccc78-109">Requirements</span></span>

<span data-ttu-id="ccc78-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccc78-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ccc78-111">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="ccc78-111">**Header:** None</span></span>  
<span data-ttu-id="ccc78-112">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="ccc78-112">**Library:** None</span></span>  
<span data-ttu-id="ccc78-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ccc78-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ccc78-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ccc78-114">See also</span></span>

- [<span data-ttu-id="ccc78-115">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="ccc78-115">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="ccc78-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="ccc78-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="ccc78-117">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="ccc78-117">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
