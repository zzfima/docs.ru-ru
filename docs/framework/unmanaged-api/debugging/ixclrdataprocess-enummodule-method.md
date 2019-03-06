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
ms.openlocfilehash: a0398d18f9568754231082d63b4c6a2c865d8c6f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363310"
---
# <a name="ixclrdataprocessenummodule-method"></a><span data-ttu-id="0bf4e-102">Метод IXCLRDataProcess::EnumModule</span><span class="sxs-lookup"><span data-stu-id="0bf4e-102">IXCLRDataProcess::EnumModule Method</span></span>

<span data-ttu-id="0bf4e-103">Перечисляет модули этого процесса.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-103">Enumerates the modules of this process.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0bf4e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0bf4e-104">Syntax</span></span>

```
HRESULT EnumModule(
    [in, out] CLRDATA_ENUM  *handle,
    [out] IXCLRDataModule  **mod
);
```

## <a name="parameters"></a><span data-ttu-id="0bf4e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0bf4e-105">Parameters</span></span>

`handle`\
<span data-ttu-id="0bf4e-106">[in, out] Дескриптор для перечисления модули.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-106">[in, out] A handle for enumerating the modules.</span></span>

`mod`\
<span data-ttu-id="0bf4e-107">[out] Перечислимый модуль.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-107">[out] The enumerated module.</span></span>

## <a name="remarks"></a><span data-ttu-id="0bf4e-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0bf4e-108">Remarks</span></span>

<span data-ttu-id="0bf4e-109">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 25 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="0bf4e-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="0bf4e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0bf4e-110">Requirements</span></span>

<span data-ttu-id="0bf4e-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bf4e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0bf4e-112">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="0bf4e-112">**Header:** None</span></span>  
<span data-ttu-id="0bf4e-113">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="0bf4e-113">**Library:** None</span></span>  
<span data-ttu-id="0bf4e-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0bf4e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0bf4e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0bf4e-115">See also</span></span>

- [<span data-ttu-id="0bf4e-116">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="0bf4e-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="0bf4e-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="0bf4e-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="0bf4e-118">Интерфейс IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="0bf4e-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
- [<span data-ttu-id="0bf4e-119">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="0bf4e-119">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
