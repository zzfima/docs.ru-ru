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
ms.openlocfilehash: d19a4b8116573f2ff6469fe612e7b7736651ff03
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354535"
---
# <a name="ixclrdataprocessenummethodinstancebyaddress-method"></a><span data-ttu-id="85a48-102">Метод IXCLRDataProcess::EnumMethodInstanceByAddress</span><span class="sxs-lookup"><span data-stu-id="85a48-102">IXCLRDataProcess::EnumMethodInstanceByAddress Method</span></span>

<span data-ttu-id="85a48-103">Перечисление экземпляров метод класса этот процесс, начиная с смещение адреса.</span><span class="sxs-lookup"><span data-stu-id="85a48-103">Enumerates the method instances of this process starting at an address offset.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="85a48-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="85a48-104">Syntax</span></span>

```
HRESULT EnumMethodInstanceByAddress(
    [in] CLRDATA_ENUM              *handle,
    [out] IXCLRDataMethodInstance **method
);
```

### <a name="parameters"></a><span data-ttu-id="85a48-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="85a48-105">Parameters</span></span>

`handle`\
<span data-ttu-id="85a48-106">[in] Дескриптор для перечисления экземпляров метода.</span><span class="sxs-lookup"><span data-stu-id="85a48-106">[in] A handle for enumerating the method instances.</span></span>

`mod`\
<span data-ttu-id="85a48-107">[out] Экземпляр перечисления метод.</span><span class="sxs-lookup"><span data-stu-id="85a48-107">[out] The enumerated method instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="85a48-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="85a48-108">Remarks</span></span>

<span data-ttu-id="85a48-109">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 28 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="85a48-109">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 28th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="85a48-110">Требования</span><span class="sxs-lookup"><span data-stu-id="85a48-110">Requirements</span></span>

<span data-ttu-id="85a48-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85a48-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="85a48-112">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="85a48-112">**Header:** None</span></span>   
<span data-ttu-id="85a48-113">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="85a48-113">**Library:** None</span></span>   
<span data-ttu-id="85a48-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="85a48-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   
 
## <a name="see-also"></a><span data-ttu-id="85a48-115">См. также</span><span class="sxs-lookup"><span data-stu-id="85a48-115">See also</span></span>
- [<span data-ttu-id="85a48-116">Перечисление CLRDataSourceType</span><span class="sxs-lookup"><span data-stu-id="85a48-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="85a48-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="85a48-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="85a48-118">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="85a48-118">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
