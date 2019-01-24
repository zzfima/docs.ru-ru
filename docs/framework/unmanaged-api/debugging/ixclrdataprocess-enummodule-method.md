---
title: Метод IXCLRDataProcess::EnumModule
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumModule Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumModule Method
helpviewer.keywords:
- IXCLRDataProcess::EnumModule Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 1648e53df5f36f7615831b425d2b5d764731c5c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738135"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="9402a-102">Метод IXCLRDataProcess::EnumModule</span><span class="sxs-lookup"><span data-stu-id="9402a-102">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="9402a-103">Перечисляет модули этого процесса.</span><span class="sxs-lookup"><span data-stu-id="9402a-103">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9402a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9402a-104">Syntax</span></span>

```
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

### <a name="parameters"></a><span data-ttu-id="9402a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9402a-105">Parameters</span></span>

<span data-ttu-id="9402a-106">`handle` [in, out] Дескриптор для перечисления модули.</span><span class="sxs-lookup"><span data-stu-id="9402a-106">`handle` [in, out] A handle for enumerating the modules.</span></span>

<span data-ttu-id="9402a-107">`mod` [out] Перечислимый модуль.</span><span class="sxs-lookup"><span data-stu-id="9402a-107">`mod` [out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="9402a-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="9402a-108">Remarks</span></span>

<span data-ttu-id="9402a-109">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 25 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="9402a-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="9402a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9402a-110">Requirements</span></span>

<span data-ttu-id="9402a-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9402a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9402a-112">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="9402a-112">**Header:** None</span></span>  
<span data-ttu-id="9402a-113">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="9402a-113">**Library:** None</span></span>  
<span data-ttu-id="9402a-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9402a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9402a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9402a-115">See also</span></span>

- [<span data-ttu-id="9402a-116">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="9402a-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="9402a-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="9402a-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="9402a-118">Интерфейс IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="9402a-118">IXCLRDataModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)
- [<span data-ttu-id="9402a-119">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="9402a-119">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
