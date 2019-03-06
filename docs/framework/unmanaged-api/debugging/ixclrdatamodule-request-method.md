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
ms.openlocfilehash: 336e47d531fc880571165cd55f117825cd1a2abb
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374873"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="fe3f2-102">Метод IXCLRDataModule::Request</span><span class="sxs-lookup"><span data-stu-id="fe3f2-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="fe3f2-103">Запросы, чтобы заполнить буфер с данными модуля.</span><span class="sxs-lookup"><span data-stu-id="fe3f2-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="fe3f2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fe3f2-104">Syntax</span></span>
```
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

### <a name="parameters"></a><span data-ttu-id="fe3f2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fe3f2-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="fe3f2-106">[in] Тип отправляемого запроса.</span><span class="sxs-lookup"><span data-stu-id="fe3f2-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="fe3f2-107">[in] размер входного буфера, который передается в.</span><span class="sxs-lookup"><span data-stu-id="fe3f2-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="fe3f2-108">[in, size_is(inBufferSize)] Указатель на буфер для необработанных данных, которые будут отправляться в запрос.</span><span class="sxs-lookup"><span data-stu-id="fe3f2-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="fe3f2-109">[in] Размер выходного буфера.</span><span class="sxs-lookup"><span data-stu-id="fe3f2-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="fe3f2-110">[out, size_is(outBufferSize)] Указатель буфера, используемого для хранения запрос-ответ.</span><span class="sxs-lookup"><span data-stu-id="fe3f2-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe3f2-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="fe3f2-111">Remarks</span></span>

<span data-ttu-id="fe3f2-112">Указанный метод является частью `IXCLRDataModule` интерфейса и соответствует 36-ая слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="fe3f2-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 36th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="fe3f2-113">Требования</span><span class="sxs-lookup"><span data-stu-id="fe3f2-113">Requirements</span></span>

<span data-ttu-id="fe3f2-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe3f2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="fe3f2-115">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="fe3f2-115">**Header:** None</span></span>   
<span data-ttu-id="fe3f2-116">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="fe3f2-116">**Library:** None</span></span>  
<span data-ttu-id="fe3f2-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fe3f2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="fe3f2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fe3f2-118">See also</span></span>
- [<span data-ttu-id="fe3f2-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="fe3f2-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="fe3f2-120">Интерфейс IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="fe3f2-120">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)