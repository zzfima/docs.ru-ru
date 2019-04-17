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
ms.openlocfilehash: 755063ca6da29a2e4733dd653306192ac0434ec0
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2019
ms.locfileid: "59610604"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="bcb1b-102">Метод IXCLRDataModule::Request</span><span class="sxs-lookup"><span data-stu-id="bcb1b-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="bcb1b-103">Запросы, чтобы заполнить буфер с данными модуля.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="bcb1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bcb1b-104">Syntax</span></span>

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="bcb1b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bcb1b-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="bcb1b-106">[in] Тип отправляемого запроса.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="bcb1b-107">[in] размер входного буфера, который передается в.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="bcb1b-108">[in, size_is(inBufferSize)] Указатель на буфер для необработанных данных, которые будут отправляться в запрос.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="bcb1b-109">[in] Размер выходного буфера.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="bcb1b-110">[out, size_is(outBufferSize)] Указатель буфера, используемого для хранения запрос-ответ.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="bcb1b-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="bcb1b-111">Remarks</span></span>

<span data-ttu-id="bcb1b-112">Указанный метод является частью `IXCLRDataModule` интерфейса и соответствует 36-ая слот в таблице виртуального метода.</span><span class="sxs-lookup"><span data-stu-id="bcb1b-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 36th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="bcb1b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="bcb1b-113">Requirements</span></span>

<span data-ttu-id="bcb1b-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcb1b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="bcb1b-115">**Заголовок.** Нет **библиотеки:** Нет **версий платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bcb1b-115">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bcb1b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bcb1b-116">See also</span></span>

- [<span data-ttu-id="bcb1b-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="bcb1b-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="bcb1b-118">Интерфейс IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="bcb1b-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)