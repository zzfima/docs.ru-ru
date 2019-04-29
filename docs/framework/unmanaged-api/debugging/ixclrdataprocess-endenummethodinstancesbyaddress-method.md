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
ms.openlocfilehash: 072e775d11d44dfbca27f1616889e388ae61d467
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775483"
---
# <a name="ixclrdataprocessendenummethodinstancesbyaddress-method"></a><span data-ttu-id="fcd02-102">Метод IXCLRDataProcess::EndEnumMethodInstancesByAddress</span><span class="sxs-lookup"><span data-stu-id="fcd02-102">IXCLRDataProcess::EndEnumMethodInstancesByAddress Method</span></span>

<span data-ttu-id="fcd02-103">Освобождает ресурсы, используемые внутренней итераторы, используется в процессе экземпляра перечисления.</span><span class="sxs-lookup"><span data-stu-id="fcd02-103">Releases the resources used by internal iterators used during instance enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="fcd02-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fcd02-104">Syntax</span></span>

```
HRESULT EndEnumMethodInstancesByAddress(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="fcd02-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fcd02-105">Parameters</span></span>

`handle`\
<span data-ttu-id="fcd02-106">[out] Дескриптор для перечисления экземпляров метода.</span><span class="sxs-lookup"><span data-stu-id="fcd02-106">[out] A handle for enumerating the method instances.</span></span>

## <a name="remarks"></a><span data-ttu-id="fcd02-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="fcd02-107">Remarks</span></span>

<span data-ttu-id="fcd02-108">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 29 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="fcd02-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 29th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="fcd02-109">Требования</span><span class="sxs-lookup"><span data-stu-id="fcd02-109">Requirements</span></span>

<span data-ttu-id="fcd02-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcd02-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="fcd02-111">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="fcd02-111">**Header:** None</span></span>  
<span data-ttu-id="fcd02-112">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="fcd02-112">**Library:** None</span></span>  
<span data-ttu-id="fcd02-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fcd02-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="fcd02-114">См. также</span><span class="sxs-lookup"><span data-stu-id="fcd02-114">See also</span></span>

- [<span data-ttu-id="fcd02-115">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="fcd02-115">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="fcd02-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="fcd02-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="fcd02-117">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="fcd02-117">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
