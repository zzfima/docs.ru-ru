---
title: Метод IXCLRDataModule::Request
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::Request Method
helpviewer.keywords:
- IXCLRDataModule::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 0226a11b142515296d976e3d645cb2475d634420
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2019
ms.locfileid: "54416587"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="b6dc4-102">Метод IXCLRDataModule::Request</span><span class="sxs-lookup"><span data-stu-id="b6dc4-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="b6dc4-103">Запросы, чтобы заполнить буфер с данными модуля.</span><span class="sxs-lookup"><span data-stu-id="b6dc4-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="b6dc4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6dc4-104">Syntax</span></span>
```
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

### <a name="parameters"></a><span data-ttu-id="b6dc4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b6dc4-105">Parameters</span></span>

<span data-ttu-id="b6dc4-106">`reqCode` [in] Тип отправляемого запроса.</span><span class="sxs-lookup"><span data-stu-id="b6dc4-106">`reqCode` [in] Request type to be sent.</span></span>

<span data-ttu-id="b6dc4-107">`inBufferSize` [in] размер входного буфера, который передается в.</span><span class="sxs-lookup"><span data-stu-id="b6dc4-107">`inBufferSize` [in] size of the input buffer to be passed in.</span></span>

<span data-ttu-id="b6dc4-108">`inBuffer` [in, size_is(inBufferSize)] Указатель на буфер для необработанных данных, которые будут отправляться в запрос.</span><span class="sxs-lookup"><span data-stu-id="b6dc4-108">`inBuffer` [in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

<span data-ttu-id="b6dc4-109">`outBufferSize` [in] Размер выходного буфера.</span><span class="sxs-lookup"><span data-stu-id="b6dc4-109">`outBufferSize` [in] Size of the output buffer.</span></span>

<span data-ttu-id="b6dc4-110">`outBuffer` [out, size_is(outBufferSize)] Указатель буфера, используемого для хранения запрос-ответ.</span><span class="sxs-lookup"><span data-stu-id="b6dc4-110">`outBuffer` [out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="b6dc4-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="b6dc4-111">Remarks</span></span>

<span data-ttu-id="b6dc4-112">Указанный метод является частью `IXCLRDataModule` интерфейса и соответствует 36-ая слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="b6dc4-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 36th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="b6dc4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="b6dc4-113">Requirements</span></span>

<span data-ttu-id="b6dc4-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6dc4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="b6dc4-115">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="b6dc4-115">**Header:** None</span></span>   
<span data-ttu-id="b6dc4-116">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="b6dc4-116">**Library:** None</span></span>  
<span data-ttu-id="b6dc4-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b6dc4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b6dc4-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b6dc4-118">See Also</span></span>
- [<span data-ttu-id="b6dc4-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="b6dc4-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="b6dc4-120">Интерфейс IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="b6dc4-120">IXCLRDataModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)
