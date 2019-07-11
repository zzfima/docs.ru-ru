---
title: Метод IXCLRDataModule::GetMethodDefinitionByToken
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
ms.openlocfilehash: 2c0cf56f108396226b7c7399f6da75e5f47d36f3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744674"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="807a4-102">Метод IXCLRDataModule::GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="807a4-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="807a4-103">Возвращает определение метода, соответствующей токену метаданных.</span><span class="sxs-lookup"><span data-stu-id="807a4-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="807a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="807a4-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="807a4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="807a4-105">Parameters</span></span>

`token`\
<span data-ttu-id="807a4-106">[in] Маркер метода.</span><span class="sxs-lookup"><span data-stu-id="807a4-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="807a4-107">[out] Определение метода.</span><span class="sxs-lookup"><span data-stu-id="807a4-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="807a4-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="807a4-108">Remarks</span></span>

<span data-ttu-id="807a4-109">Указанный метод является частью `IXCLRDataModule` интерфейса и соответствует 25 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="807a4-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="807a4-110">Требования</span><span class="sxs-lookup"><span data-stu-id="807a4-110">Requirements</span></span>

<span data-ttu-id="807a4-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="807a4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="807a4-112">**Заголовок.** None</span><span class="sxs-lookup"><span data-stu-id="807a4-112">**Header:** None</span></span>  
<span data-ttu-id="807a4-113">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="807a4-113">**Library:** None</span></span>  
<span data-ttu-id="807a4-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="807a4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="807a4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="807a4-115">See also</span></span>

- [<span data-ttu-id="807a4-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="807a4-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="807a4-117">Интерфейс IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="807a4-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
