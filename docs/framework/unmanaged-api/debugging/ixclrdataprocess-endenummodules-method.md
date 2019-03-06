---
title: Метод IXCLRDataProcess::EndEnumModules
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3b7050e92af6fc58b45837840b2796a5deac955c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375341"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="24225-102">Метод IXCLRDataProcess::EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="24225-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="24225-103">Освобождает ресурсы, используемые внутренней итераторы, используемые при перечислении модуля.</span><span class="sxs-lookup"><span data-stu-id="24225-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="24225-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="24225-104">Syntax</span></span>
```
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="24225-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="24225-105">Parameters</span></span>

`handle`\
<span data-ttu-id="24225-106">[out] Дескриптор для перечисления модули.</span><span class="sxs-lookup"><span data-stu-id="24225-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="24225-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="24225-107">Remarks</span></span>

<span data-ttu-id="24225-108">Указанный метод является частью `IXCLRDataProcess` интерфейса и соответствует 26 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="24225-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="24225-109">Требования</span><span class="sxs-lookup"><span data-stu-id="24225-109">Requirements</span></span>

<span data-ttu-id="24225-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24225-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="24225-111">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="24225-111">**Header:** None</span></span>   
<span data-ttu-id="24225-112">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="24225-112">**Library:** None</span></span>   
<span data-ttu-id="24225-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="24225-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   

## <a name="see-also"></a><span data-ttu-id="24225-114">См. также</span><span class="sxs-lookup"><span data-stu-id="24225-114">See also</span></span>

- [<span data-ttu-id="24225-115">Отладка</span><span class="sxs-lookup"><span data-stu-id="24225-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="24225-116">Интерфейс IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="24225-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
