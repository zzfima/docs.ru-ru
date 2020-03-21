---
title: IXCLRDataProcess::EnumMethodInstanceByAddress Метод
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::EnumMethodInstanceByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: afc5fc377dd45d5e8d4d2d7b3385ca0524df69e1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176660"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="29ea0-102">IXCLRDataProcess::EnumMethodInstanceByAddress Метод</span><span class="sxs-lookup"><span data-stu-id="29ea0-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="29ea0-103">Перечисляет экземпляры метода этого процесса, начиная с смещения адреса.</span><span class="sxs-lookup"><span data-stu-id="29ea0-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="29ea0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29ea0-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="29ea0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="29ea0-105">Parameters</span></span>

`handle`\
<span data-ttu-id="29ea0-106">(в) Ручка для перечисления экземпляров метода.</span><span class="sxs-lookup"><span data-stu-id="29ea0-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="29ea0-107">(ваут) Перечисленный экземпляр метода.</span><span class="sxs-lookup"><span data-stu-id="29ea0-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="29ea0-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="29ea0-108">Remarks</span></span>

<span data-ttu-id="29ea0-109">Предоставляемый метод является `IXCLRDataProcess` частью интерфейса и соответствует 28-му слоту таблицы виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="29ea0-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="29ea0-110">Требования</span><span class="sxs-lookup"><span data-stu-id="29ea0-110">Requirements</span></span>

<span data-ttu-id="29ea0-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29ea0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="29ea0-112">**Заголовок:** Нет **библиотеки:** Нет **.NET Рамочные версии:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="29ea0-112">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="29ea0-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="29ea0-113">See also</span></span>

- [<span data-ttu-id="29ea0-114">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="29ea0-114">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="29ea0-115">Отладки</span><span class="sxs-lookup"><span data-stu-id="29ea0-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="29ea0-116">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="29ea0-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
