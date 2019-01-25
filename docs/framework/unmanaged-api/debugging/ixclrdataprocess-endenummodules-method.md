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
ms.openlocfilehash: 50ad55674360d7b880af3ddf701cf17005f30ce7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722742"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="8943c-102">Метод IXCLRDataProcess::EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="8943c-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="8943c-103">Освобождает ресурсы, используемые внутренней итераторы, используемые при перечислении модуля.</span><span class="sxs-lookup"><span data-stu-id="8943c-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="8943c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8943c-104">Syntax</span></span>
```
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a><span data-ttu-id="8943c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8943c-105">Parameters</span></span>
<span data-ttu-id="8943c-106">`handle` [out] Дескриптор для перечисления модули.</span><span class="sxs-lookup"><span data-stu-id="8943c-106">`handle` [out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="8943c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="8943c-107">Remarks</span></span>

<span data-ttu-id="8943c-108">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 26 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="8943c-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="8943c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8943c-109">Requirements</span></span>

<span data-ttu-id="8943c-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8943c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="8943c-111">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="8943c-111">**Header:** None</span></span>   
<span data-ttu-id="8943c-112">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="8943c-112">**Library:** None</span></span>   
<span data-ttu-id="8943c-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8943c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   

## <a name="see-also"></a><span data-ttu-id="8943c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8943c-114">See also</span></span>

- [<span data-ttu-id="8943c-115">Отладка</span><span class="sxs-lookup"><span data-stu-id="8943c-115">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="8943c-116">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="8943c-116">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
