---
title: IXCLRDataModule::GetMethodDefinitionByToken Метод
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetMethodDefinitionByToken Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method
helpviewer.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 294c5340caf2217f9337d654a11a63a43d46febd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176673"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="beee2-102">IXCLRDataModule::GetMethodDefinitionByToken Метод</span><span class="sxs-lookup"><span data-stu-id="beee2-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="beee2-103">Получает определение метода, соответствующее заданного маркеру метаданных.</span><span class="sxs-lookup"><span data-stu-id="beee2-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="beee2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="beee2-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="beee2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="beee2-105">Parameters</span></span>

`token`\
<span data-ttu-id="beee2-106">(в) Токен метода.</span><span class="sxs-lookup"><span data-stu-id="beee2-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="beee2-107">(ваут) Определение метода.</span><span class="sxs-lookup"><span data-stu-id="beee2-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="beee2-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="beee2-108">Remarks</span></span>

<span data-ttu-id="beee2-109">Предоставляемый метод является `IXCLRDataModule` частью интерфейса и соответствует 25-му слоту таблицы виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="beee2-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="beee2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="beee2-110">Requirements</span></span>

<span data-ttu-id="beee2-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="beee2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="beee2-112">**Заголовок:** Ни один</span><span class="sxs-lookup"><span data-stu-id="beee2-112">**Header:** None</span></span>  
<span data-ttu-id="beee2-113">**Библиотека:** Ни один</span><span class="sxs-lookup"><span data-stu-id="beee2-113">**Library:** None</span></span>  
<span data-ttu-id="beee2-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="beee2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="beee2-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="beee2-115">See also</span></span>

- [<span data-ttu-id="beee2-116">Отладки</span><span class="sxs-lookup"><span data-stu-id="beee2-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="beee2-117">Интерфейс IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="beee2-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
