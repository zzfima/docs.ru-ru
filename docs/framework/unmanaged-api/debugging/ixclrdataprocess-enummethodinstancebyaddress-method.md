---
title: Метод IXCLRDataProcess::EnumMethodInstanceByAddress
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
ms.openlocfilehash: 89b89a0cb056a0515bf0859069455a73f62aae4a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769620"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="a0cb1-102">Метод IXCLRDataProcess::EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="a0cb1-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="a0cb1-103">Перечисление экземпляров метод класса этот процесс, начиная с смещение адреса.</span><span class="sxs-lookup"><span data-stu-id="a0cb1-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a0cb1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0cb1-104">Syntax</span></span>

```cpp
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

## <a name="parameters"></a><span data-ttu-id="a0cb1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0cb1-105">Parameters</span></span>

`handle`\
<span data-ttu-id="a0cb1-106">[in] Дескриптор для перечисления экземпляров метода.</span><span class="sxs-lookup"><span data-stu-id="a0cb1-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="a0cb1-107">[out] Экземпляр перечисления метод.</span><span class="sxs-lookup"><span data-stu-id="a0cb1-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="a0cb1-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="a0cb1-108">Remarks</span></span>

<span data-ttu-id="a0cb1-109">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 28 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="a0cb1-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="a0cb1-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a0cb1-110">Requirements</span></span>

<span data-ttu-id="a0cb1-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0cb1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="a0cb1-112">**Заголовок.** None</span><span class="sxs-lookup"><span data-stu-id="a0cb1-112">**Header:** None</span></span>   
<span data-ttu-id="a0cb1-113">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="a0cb1-113">**Library:** None</span></span>   
<span data-ttu-id="a0cb1-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a0cb1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="a0cb1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a0cb1-115">See also</span></span>

- [<span data-ttu-id="a0cb1-116">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="a0cb1-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="a0cb1-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="a0cb1-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="a0cb1-118">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="a0cb1-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
