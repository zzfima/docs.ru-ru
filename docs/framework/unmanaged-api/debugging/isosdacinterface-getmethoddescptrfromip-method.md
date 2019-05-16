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
ms.openlocfilehash: c92b112262aa2bede03bddc1396947b5fdfd6286
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65629993"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="9c7f5-102">Метод ISOSDacInterface::GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="9c7f5-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="9c7f5-103">Извлекает указатель MethodDesc, соответствующий метод, содержащий адрес заданной инструкции машинного кода.</span><span class="sxs-lookup"><span data-stu-id="9c7f5-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="9c7f5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c7f5-104">Syntax</span></span>

```
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="9c7f5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c7f5-105">Parameters</span></span>

`ip`\
<span data-ttu-id="9c7f5-106">[in] Адрес в пределах метода во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="9c7f5-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="9c7f5-107">[out] Адрес `MethodDesc` для конкретного метода.</span><span class="sxs-lookup"><span data-stu-id="9c7f5-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c7f5-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="9c7f5-108">Remarks</span></span>

<span data-ttu-id="9c7f5-109">Указанный метод является частью [ `ISOSDacInterface` интерфейс](isosdacinterface-interface.md) и соответствует 21 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="9c7f5-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 21st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="9c7f5-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9c7f5-110">Requirements</span></span>

<span data-ttu-id="9c7f5-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c7f5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="9c7f5-112">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="9c7f5-112">**Header:** None</span></span>  
<span data-ttu-id="9c7f5-113">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="9c7f5-113">**Library:** None</span></span>  
<span data-ttu-id="9c7f5-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9c7f5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="9c7f5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9c7f5-115">See also</span></span>

- [<span data-ttu-id="9c7f5-116">Отладка</span><span class="sxs-lookup"><span data-stu-id="9c7f5-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="9c7f5-117">Интерфейс ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="9c7f5-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
