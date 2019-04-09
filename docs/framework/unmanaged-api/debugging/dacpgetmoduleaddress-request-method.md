---
title: Метод DacpGetModuleAddress::Request
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 298620092c37b2c02332e9135f73584272e326bd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111687"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="dd6e1-102">Метод DacpGetModuleAddress::Request</span><span class="sxs-lookup"><span data-stu-id="dd6e1-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="dd6e1-103">Выполняет запрос для заполнения структуры из структуры данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="dd6e1-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="dd6e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd6e1-104">Syntax</span></span>

```
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="dd6e1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dd6e1-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="dd6e1-106">[in] Указатель на модуль начальное значение данных.</span><span class="sxs-lookup"><span data-stu-id="dd6e1-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="dd6e1-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="dd6e1-107">Remarks</span></span>

<span data-ttu-id="dd6e1-108">Эта структура находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="dd6e1-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="dd6e1-109">Чтобы использовать его, проще всего имитируют реализации:</span><span class="sxs-lookup"><span data-stu-id="dd6e1-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="dd6e1-110">Возвращает значение, полученное от вызова `Request` метод `IXCLRDataModule*` параметра со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="dd6e1-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters:</span></span> `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`

## <a name="requirements"></a><span data-ttu-id="dd6e1-111">Требования</span><span class="sxs-lookup"><span data-stu-id="dd6e1-111">Requirements</span></span>

<span data-ttu-id="dd6e1-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd6e1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="dd6e1-113">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="dd6e1-113">**Header:** None</span></span>     
<span data-ttu-id="dd6e1-114">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="dd6e1-114">**Library:** None</span></span>  
**<span data-ttu-id="dd6e1-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="dd6e1-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="dd6e1-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dd6e1-116">See also</span></span>

- [<span data-ttu-id="dd6e1-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="dd6e1-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="dd6e1-118">Интерфейс DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="dd6e1-118">DacpGetModuleAddress Interface</span></span>](dacpgetmoduleaddress-structure.md)