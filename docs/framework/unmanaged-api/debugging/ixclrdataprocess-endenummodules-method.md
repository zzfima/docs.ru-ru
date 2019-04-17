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
ms.openlocfilehash: de30384b4c12c4fcac3eafe580484685f8a43fa4
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611436"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="9127e-102">Метод IXCLRDataProcess::EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="9127e-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="9127e-103">Освобождает ресурсы, используемые внутренней итераторы, используемые при перечислении модуля.</span><span class="sxs-lookup"><span data-stu-id="9127e-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9127e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9127e-104">Syntax</span></span>

```cpp
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="9127e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9127e-105">Parameters</span></span>

`handle`\
<span data-ttu-id="9127e-106">[out] Дескриптор для перечисления модули.</span><span class="sxs-lookup"><span data-stu-id="9127e-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="9127e-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="9127e-107">Remarks</span></span>

<span data-ttu-id="9127e-108">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 26 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="9127e-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="9127e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9127e-109">Requirements</span></span>

<span data-ttu-id="9127e-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9127e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="9127e-111">**Заголовок.** Нет **библиотеки:** Нет **версий платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9127e-111">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9127e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="9127e-112">See also</span></span>

- [<span data-ttu-id="9127e-113">Отладка</span><span class="sxs-lookup"><span data-stu-id="9127e-113">Debugging</span></span>](index.md)
- [<span data-ttu-id="9127e-114">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="9127e-114">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
