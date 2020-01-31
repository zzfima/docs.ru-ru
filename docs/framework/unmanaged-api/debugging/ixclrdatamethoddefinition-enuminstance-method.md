---
title: 'Метод Иксклрдатамесоддефинитион:: Енуминстанце'
ms.date: 01/16/2019
api.name:
- IXCLRDataMethodDefinition::EnumInstance Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method
helpviewer.keywords:
- IXCLRDataMethodDefinition::EnumInstance Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: b6393d7fa4853c230203521e665bbe89d7b228e2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790443"
---
# <a name="ixclrdatamethoddefinitionenuminstance-method"></a><span data-ttu-id="75917-102">Метод Иксклрдатамесоддефинитион:: Енуминстанце</span><span class="sxs-lookup"><span data-stu-id="75917-102">IXCLRDataMethodDefinition::EnumInstance Method</span></span>

<span data-ttu-id="75917-103">Перечисляет экземпляры этого определения метода.</span><span class="sxs-lookup"><span data-stu-id="75917-103">Enumerates the instances of this method definition.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="75917-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75917-104">Syntax</span></span>

```cpp
HRESULT EnumInstance(
    [in, out] CLRDATA_ENUM         *handle,
    [out] IXCLRDataMethodInstance **instance
);
```

## <a name="parameters"></a><span data-ttu-id="75917-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="75917-105">Parameters</span></span>

`handle`\
<span data-ttu-id="75917-106">[вход, выход] Маркер для перечисления экземпляров.</span><span class="sxs-lookup"><span data-stu-id="75917-106">[in, out] A handle for enumerating the instances.</span></span>

`instance`\
<span data-ttu-id="75917-107">заполняет Перечислимый экземпляр.</span><span class="sxs-lookup"><span data-stu-id="75917-107">[out] The enumerated instance.</span></span>

## <a name="remarks"></a><span data-ttu-id="75917-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="75917-108">Remarks</span></span>

<span data-ttu-id="75917-109">Предоставленный метод является частью `IXCLRDataMethodDefinition` интерфейса и соответствует четвертому слоту таблицы виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="75917-109">The provided method is part of the `IXCLRDataMethodDefinition` interface and corresponds to the fourth slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="75917-110">Требования</span><span class="sxs-lookup"><span data-stu-id="75917-110">Requirements</span></span>

<span data-ttu-id="75917-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75917-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="75917-112">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="75917-112">**Header:** None</span></span>  
<span data-ttu-id="75917-113">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="75917-113">**Library:** None</span></span>  
<span data-ttu-id="75917-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="75917-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="75917-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="75917-115">See also</span></span>

- [<span data-ttu-id="75917-116">Перечисление Клрдатасаурцетипе</span><span class="sxs-lookup"><span data-stu-id="75917-116">CLRDataSourceType Enumeration</span></span>](clrdatasourcetype-enumeration.md)
- [<span data-ttu-id="75917-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="75917-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="75917-118">Интерфейс Иксклрдатамесоддефинитион</span><span class="sxs-lookup"><span data-stu-id="75917-118">IXCLRDataMethodDefinition Interface</span></span>](ixclrdatamethoddefinition-interface.md)
- [<span data-ttu-id="75917-119">Интерфейс Иксклрдатамесодинстанце</span><span class="sxs-lookup"><span data-stu-id="75917-119">IXCLRDataMethodInstance Interface</span></span>](ixclrdatamethodinstance-interface.md)
