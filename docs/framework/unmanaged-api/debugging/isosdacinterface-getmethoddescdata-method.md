---
title: Метод ISOSDacInterface::GetMethodDescData
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3f22752446413c622a20340541b0ac328f63c77b
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416734"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="3eabf-102">Метод ISOSDacInterface::GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="3eabf-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="3eabf-103">Получает данные для заданного [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span><span class="sxs-lookup"><span data-stu-id="3eabf-103">Gets the data for the given [MethodDesc](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md).</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="3eabf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3eabf-104">Syntax</span></span>

```
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    void                       *data,
    ULONG                      cRevertedRejitVersions,
    void                      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

### <a name="parameters"></a><span data-ttu-id="3eabf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3eabf-105">Parameters</span></span>

<span data-ttu-id="3eabf-106">`methodDesc` [in] Адрес MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="3eabf-106">`methodDesc` [in] The address of the MethodDesc.</span></span>

<span data-ttu-id="3eabf-107">`ip` [in] IP-адрес метода.</span><span class="sxs-lookup"><span data-stu-id="3eabf-107">`ip` [in] The IP address of the method.</span></span>

<span data-ttu-id="3eabf-108">`data` [out] Данные, связанные с MethodDesc, возвращенный внутренним API.</span><span class="sxs-lookup"><span data-stu-id="3eabf-108">`data` [out] The data associated with the MethodDesc as returned from the internal APIs.</span></span> <span data-ttu-id="3eabf-109">Структура необходимо по крайней мере 168 байта.</span><span class="sxs-lookup"><span data-stu-id="3eabf-109">The structure needs at least 168 bytes.</span></span>

<span data-ttu-id="3eabf-110">`cRevertedRejitVersions` [out] Число версий rejit возвращенного в предыдущее состояние.</span><span class="sxs-lookup"><span data-stu-id="3eabf-110">`cRevertedRejitVersions` [out] The number of reverted rejit versions.</span></span>

<span data-ttu-id="3eabf-111">`rgRevertedRejitData` [out] Данные, связанные с версиями возвращенного в предыдущее состояние rejit, возвращенный внутренним API.</span><span class="sxs-lookup"><span data-stu-id="3eabf-111">`rgRevertedRejitData` [out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span> <span data-ttu-id="3eabf-112">Структура необходимо по крайней мере 24 байта.</span><span class="sxs-lookup"><span data-stu-id="3eabf-112">The structure needs at least 24 bytes.</span></span>

<span data-ttu-id="3eabf-113">`pcNeededRevertedRejitData` [out] Число байтов, необходимое для хранения данных, связанные с восстанавливаемой версиями ReJit.</span><span class="sxs-lookup"><span data-stu-id="3eabf-113">`pcNeededRevertedRejitData` [out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="3eabf-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="3eabf-114">Remarks</span></span>

<span data-ttu-id="3eabf-115">Указанный метод является частью `ISOSDacInterface` интерфейса и соответствует 20 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="3eabf-115">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="3eabf-116">Также `CLRDATA_ADDRESS` являются 64-разрядного целого числа без знака.</span><span class="sxs-lookup"><span data-stu-id="3eabf-116">Also the `CLRDATA_ADDRESS` are 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="3eabf-117">Требования</span><span class="sxs-lookup"><span data-stu-id="3eabf-117">Requirements</span></span>

<span data-ttu-id="3eabf-118">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3eabf-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="3eabf-119">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="3eabf-119">**Header:** None</span></span>  
<span data-ttu-id="3eabf-120">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="3eabf-120">**Library:** None</span></span>  
<span data-ttu-id="3eabf-121">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3eabf-121">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3eabf-122">См. также</span><span class="sxs-lookup"><span data-stu-id="3eabf-122">See Also</span></span>

- [<span data-ttu-id="3eabf-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="3eabf-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="3eabf-124">Интерфейс ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="3eabf-124">ISOSDacInterface Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)
