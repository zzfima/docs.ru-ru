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
ms.openlocfilehash: a81da147c1483e7649612050f4aba29a2cc63b49
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416714"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="111b5-102">Метод IXCLRDataProcess::StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="111b5-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="111b5-103">Предоставляет маркер, чтобы перечислить модули, процесса.</span><span class="sxs-lookup"><span data-stu-id="111b5-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="111b5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="111b5-104">Syntax</span></span>

```
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

### <a name="parameters"></a><span data-ttu-id="111b5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="111b5-105">Parameters</span></span>

<span data-ttu-id="111b5-106">`handle` [out] Дескриптор для перечисления модули.</span><span class="sxs-lookup"><span data-stu-id="111b5-106">`handle` [out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="111b5-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="111b5-107">Remarks</span></span>

<span data-ttu-id="111b5-108">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 24 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="111b5-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="111b5-109">Требования</span><span class="sxs-lookup"><span data-stu-id="111b5-109">Requirements</span></span>

<span data-ttu-id="111b5-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="111b5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="111b5-111">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="111b5-111">**Header:** None</span></span>  
<span data-ttu-id="111b5-112">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="111b5-112">**Library:** None</span></span>  
<span data-ttu-id="111b5-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="111b5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="111b5-114">См. также</span><span class="sxs-lookup"><span data-stu-id="111b5-114">See Also</span></span>

- [<span data-ttu-id="111b5-115">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="111b5-115">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="111b5-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="111b5-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="111b5-117">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="111b5-117">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
