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
ms.openlocfilehash: cd256250021436e611142de11c3625a21aeec814
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764740"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="b3236-102">Метод ISOSDacInterface::GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="b3236-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="b3236-103">Извлекает указатель MethodDesc, соответствующий метод, содержащий адрес заданной инструкции машинного кода.</span><span class="sxs-lookup"><span data-stu-id="b3236-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b3236-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3236-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="b3236-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3236-105">Parameters</span></span>

`ip`\
<span data-ttu-id="b3236-106">[in] Адрес в пределах метода во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="b3236-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="b3236-107">[out] Адрес `MethodDesc` для конкретного метода.</span><span class="sxs-lookup"><span data-stu-id="b3236-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="b3236-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="b3236-108">Remarks</span></span>

<span data-ttu-id="b3236-109">Указанный метод является частью [ `ISOSDacInterface` интерфейс](isosdacinterface-interface.md) и соответствует 21 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="b3236-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 21st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b3236-110">Требования</span><span class="sxs-lookup"><span data-stu-id="b3236-110">Requirements</span></span>

<span data-ttu-id="b3236-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3236-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b3236-112">**Заголовок.** None</span><span class="sxs-lookup"><span data-stu-id="b3236-112">**Header:** None</span></span>  
<span data-ttu-id="b3236-113">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="b3236-113">**Library:** None</span></span>  
<span data-ttu-id="b3236-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b3236-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b3236-115">См. также</span><span class="sxs-lookup"><span data-stu-id="b3236-115">See also</span></span>

- [<span data-ttu-id="b3236-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="b3236-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="b3236-117">Интерфейс ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="b3236-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
