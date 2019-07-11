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
ms.openlocfilehash: 40ab90a3218d4309cda709004a191e9440fe505d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769583"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="582dc-102">Метод IXCLRDataProcess::EnumModule</span><span class="sxs-lookup"><span data-stu-id="582dc-102">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="582dc-103">Перечисляет модули этого процесса.</span><span class="sxs-lookup"><span data-stu-id="582dc-103">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="582dc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="582dc-104">Syntax</span></span>

```cpp
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a><span data-ttu-id="582dc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="582dc-105">Parameters</span></span>

`handle`\
<span data-ttu-id="582dc-106">[in, out] Дескриптор для перечисления модули.</span><span class="sxs-lookup"><span data-stu-id="582dc-106">[in, out] A handle for enumerating the modules.</span></span>

`mod`\
<span data-ttu-id="582dc-107">[out] Перечислимый модуль.</span><span class="sxs-lookup"><span data-stu-id="582dc-107">[out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="582dc-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="582dc-108">Remarks</span></span>

<span data-ttu-id="582dc-109">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 25 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="582dc-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="582dc-110">Требования</span><span class="sxs-lookup"><span data-stu-id="582dc-110">Requirements</span></span>

<span data-ttu-id="582dc-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="582dc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="582dc-112">**Заголовок.** None</span><span class="sxs-lookup"><span data-stu-id="582dc-112">**Header:** None</span></span>  
<span data-ttu-id="582dc-113">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="582dc-113">**Library:** None</span></span>  
<span data-ttu-id="582dc-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="582dc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="582dc-115">См. также</span><span class="sxs-lookup"><span data-stu-id="582dc-115">See also</span></span>

- [<span data-ttu-id="582dc-116">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="582dc-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="582dc-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="582dc-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="582dc-118">Интерфейс IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="582dc-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
- [<span data-ttu-id="582dc-119">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="582dc-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
