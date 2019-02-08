---
title: Метод ISOSDacInterface::GetMethodDescPtrFromIP
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 74853733b1fb7f023d9f192d3e862dbf6875ecda
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828659"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="e14a0-102">Метод ISOSDacInterface::GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="e14a0-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="e14a0-103">Извлекает указатель MethodDesc, соответствующий метод, содержащий адрес заданной инструкции машинного кода.</span><span class="sxs-lookup"><span data-stu-id="e14a0-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e14a0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e14a0-104">Syntax</span></span>

```
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

### <a name="parameters"></a><span data-ttu-id="e14a0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e14a0-105">Parameters</span></span>

<span data-ttu-id="e14a0-106">`ip` [in] Адрес в пределах метода во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e14a0-106">`ip` [in] An address within the method at runtime.</span></span>

<span data-ttu-id="e14a0-107">`ppMD` [out] Адрес `MethodDesc` для конкретного метода.</span><span class="sxs-lookup"><span data-stu-id="e14a0-107">`ppMD` [out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="e14a0-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="e14a0-108">Remarks</span></span>

<span data-ttu-id="e14a0-109">Указанный метод является частью [ `ISOSDacInterface` интерфейс](isosdacinterface-interface.md) и соответствует 21 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="e14a0-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 21st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="e14a0-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e14a0-110">Requirements</span></span>

<span data-ttu-id="e14a0-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e14a0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e14a0-112">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="e14a0-112">**Header:** None</span></span>  
<span data-ttu-id="e14a0-113">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="e14a0-113">**Library:** None</span></span>  
<span data-ttu-id="e14a0-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e14a0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e14a0-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e14a0-115">See also</span></span>

- [<span data-ttu-id="e14a0-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="e14a0-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="e14a0-117">Интерфейс ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="e14a0-117">ISOSDacInterface Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)
