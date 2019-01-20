---
title: Метод IXCLRDataProcess::EndEnumMethodInstancesByAddress
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumMethodInstancesByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a48a7fc9a141354666c50b1f6da8f1aaa180ff6c
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416624"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="30729-102">Метод IXCLRDataProcess::EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="30729-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="30729-103">Освобождает ресурсы, используемые внутренней итераторы, используется в процессе экземпляра перечисления.</span><span class="sxs-lookup"><span data-stu-id="30729-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="30729-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="30729-104">Syntax</span></span>

```
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

### <a name="parameters"></a><span data-ttu-id="30729-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="30729-105">Parameters</span></span>

<span data-ttu-id="30729-106">`handle` [out] Дескриптор для перечисления экземпляров метода.</span><span class="sxs-lookup"><span data-stu-id="30729-106">`handle` [out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="30729-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="30729-107">Remarks</span></span>

<span data-ttu-id="30729-108">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 29 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="30729-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="30729-109">Требования</span><span class="sxs-lookup"><span data-stu-id="30729-109">Requirements</span></span>

<span data-ttu-id="30729-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30729-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="30729-111">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="30729-111">**Header:** None</span></span>  
<span data-ttu-id="30729-112">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="30729-112">**Library:** None</span></span>  
<span data-ttu-id="30729-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="30729-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="30729-114">См. также</span><span class="sxs-lookup"><span data-stu-id="30729-114">See Also</span></span>

- [<span data-ttu-id="30729-115">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="30729-115">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="30729-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="30729-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="30729-117">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="30729-117">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
