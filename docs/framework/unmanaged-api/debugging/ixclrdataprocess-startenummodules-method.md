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
ms.openlocfilehash: 79c4e0ed99a068d7d806d5c25580dc477aac6475
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752627"
---
# <a name="ixclrdataprocessstartenummodules-method"></a><span data-ttu-id="f2b81-102">Метод IXCLRDataProcess::StartEnumModules</span><span class="sxs-lookup"><span data-stu-id="f2b81-102">IXCLRDataProcess::StartEnumModules Method</span></span>

<span data-ttu-id="f2b81-103">Предоставляет маркер, чтобы перечислить модули, процесса.</span><span class="sxs-lookup"><span data-stu-id="f2b81-103">Provides a handle to enumerate the modules of a process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="f2b81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f2b81-104">Syntax</span></span>

```cpp
HRESULT StartEnumModules(
    [out] CLRDATA_ENUM *handle
);
```

## <a name="parameters"></a><span data-ttu-id="f2b81-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f2b81-105">Parameters</span></span>

`handle`\
<span data-ttu-id="f2b81-106">[out] Дескриптор для перечисления модули.</span><span class="sxs-lookup"><span data-stu-id="f2b81-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="f2b81-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f2b81-107">Remarks</span></span>

<span data-ttu-id="f2b81-108">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 24 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="f2b81-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 24th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="f2b81-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f2b81-109">Requirements</span></span>

<span data-ttu-id="f2b81-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2b81-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="f2b81-111">**Заголовок.** None</span><span class="sxs-lookup"><span data-stu-id="f2b81-111">**Header:** None</span></span>  
<span data-ttu-id="f2b81-112">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="f2b81-112">**Library:** None</span></span>  
<span data-ttu-id="f2b81-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f2b81-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f2b81-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f2b81-114">See also</span></span>

- [<span data-ttu-id="f2b81-115">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="f2b81-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="f2b81-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="f2b81-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="f2b81-117">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="f2b81-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
