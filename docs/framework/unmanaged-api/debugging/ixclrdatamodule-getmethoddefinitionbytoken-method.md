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
ms.openlocfilehash: 1371b86f30324908a639b3b1bbae0ae007ba590a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708094"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="6b608-102">Метод IXCLRDataModule::GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="6b608-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="6b608-103">Возвращает определение метода, соответствующей токену метаданных.</span><span class="sxs-lookup"><span data-stu-id="6b608-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="6b608-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b608-104">Syntax</span></span>

```
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

### <a name="parameters"></a><span data-ttu-id="6b608-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6b608-105">Parameters</span></span>

<span data-ttu-id="6b608-106">`token` [in] Маркер метода.</span><span class="sxs-lookup"><span data-stu-id="6b608-106">`token` [in] The method token.</span></span>

<span data-ttu-id="6b608-107">`methodDefinition` [out] Определение метода.</span><span class="sxs-lookup"><span data-stu-id="6b608-107">`methodDefinition` [out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="6b608-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="6b608-108">Remarks</span></span>

<span data-ttu-id="6b608-109">Указанный метод является частью `IXCLRDataModule` интерфейса и соответствует 25 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="6b608-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="6b608-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6b608-110">Requirements</span></span>

<span data-ttu-id="6b608-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b608-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6b608-112">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="6b608-112">**Header:** None</span></span>  
<span data-ttu-id="6b608-113">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="6b608-113">**Library:** None</span></span>  
<span data-ttu-id="6b608-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6b608-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="6b608-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6b608-115">See also</span></span>

- [<span data-ttu-id="6b608-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="6b608-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="6b608-117">Интерфейс IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="6b608-117">IXCLRDataModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)
