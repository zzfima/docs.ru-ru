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
ms.openlocfilehash: 4e32facc65162c4deb853cd507a00126e5f786e7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352598"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="b35b2-102">Метод ISOSDacInterface::GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="b35b2-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="b35b2-103">Получает данные для заданный указатель MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="b35b2-103">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b35b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b35b2-104">Syntax</span></span>

```
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a><span data-ttu-id="b35b2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b35b2-105">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="b35b2-106">[in] Адрес MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="b35b2-106">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="b35b2-107">[in] IP-адрес метода.</span><span class="sxs-lookup"><span data-stu-id="b35b2-107">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="b35b2-108">[out] Данные, связанные с MethodDesc, возвращенный внутренним API.</span><span class="sxs-lookup"><span data-stu-id="b35b2-108">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="b35b2-109">[out] Число версий rejit возвращенного в предыдущее состояние.</span><span class="sxs-lookup"><span data-stu-id="b35b2-109">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="b35b2-110">[out] Данные, связанные с версиями возвращенного в предыдущее состояние rejit, возвращенный внутренним API.</span><span class="sxs-lookup"><span data-stu-id="b35b2-110">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="b35b2-111">[out] Число байтов, необходимое для хранения данных, связанные с восстанавливаемой версиями ReJit.</span><span class="sxs-lookup"><span data-stu-id="b35b2-111">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="b35b2-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="b35b2-112">Remarks</span></span>

<span data-ttu-id="b35b2-113">Указанный метод является частью `ISOSDacInterface` интерфейса и соответствует 20 слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="b35b2-113">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="b35b2-114">Чтобы иметь возможность использовать их, [ `CLRDATA_ADDRESS` ](../common-data-types-unmanaged-api-reference.md) должен быть определен как 64-разрядное целое число без знака.</span><span class="sxs-lookup"><span data-stu-id="b35b2-114">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="b35b2-115">Требования</span><span class="sxs-lookup"><span data-stu-id="b35b2-115">Requirements</span></span>

<span data-ttu-id="b35b2-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b35b2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b35b2-117">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="b35b2-117">**Header:** None</span></span>  
<span data-ttu-id="b35b2-118">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="b35b2-118">**Library:** None</span></span>  
<span data-ttu-id="b35b2-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b35b2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b35b2-120">См. также</span><span class="sxs-lookup"><span data-stu-id="b35b2-120">See also</span></span>

- [<span data-ttu-id="b35b2-121">Отладка</span><span class="sxs-lookup"><span data-stu-id="b35b2-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="b35b2-122">Интерфейс ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="b35b2-122">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)