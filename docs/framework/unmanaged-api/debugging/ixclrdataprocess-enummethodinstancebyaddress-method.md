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
ms.openlocfilehash: b42939e8e64e75337478ace67a9a91c6a03a94e3
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416684"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="3d167-102">Метод IXCLRDataProcess::EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="3d167-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="3d167-103">Перечисление экземпляров метод класса этот процесс, начиная с смещение адреса.</span><span class="sxs-lookup"><span data-stu-id="3d167-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3d167-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d167-104">Syntax</span></span>

```
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

### <a name="parameters"></a><span data-ttu-id="3d167-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d167-105">Parameters</span></span>

<span data-ttu-id="3d167-106">`handle` [in] Дескриптор для перечисления экземпляров метода.</span><span class="sxs-lookup"><span data-stu-id="3d167-106">`handle` [in] A handle for enumerating the method instances.</span></span>

<span data-ttu-id="3d167-107">`mod` [out] Экземпляр перечисления метод.</span><span class="sxs-lookup"><span data-stu-id="3d167-107">`mod` [out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="3d167-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="3d167-108">Remarks</span></span>

<span data-ttu-id="3d167-109">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 28 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="3d167-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="3d167-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3d167-110">Requirements</span></span>

<span data-ttu-id="3d167-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d167-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="3d167-112">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="3d167-112">**Header:** None</span></span>   
<span data-ttu-id="3d167-113">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="3d167-113">**Library:** None</span></span>   
<span data-ttu-id="3d167-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3d167-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="3d167-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3d167-115">See Also</span></span>
- [<span data-ttu-id="3d167-116">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="3d167-116">CLRDataSourceType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="3d167-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="3d167-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="3d167-118">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="3d167-118">IXCLRDataProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdataprocess-interface.md)
