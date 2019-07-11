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
ms.openlocfilehash: 07ad83da2bc608e3c5925664a68eec4a548860e1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739230"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="4653d-102">Метод DacpGetModuleAddress::Request</span><span class="sxs-lookup"><span data-stu-id="4653d-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="4653d-103">Выполняет запрос для заполнения структуры из структуры данной среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4653d-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="4653d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4653d-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="4653d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4653d-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="4653d-106">[in] Указатель на модуль начальное значение данных.</span><span class="sxs-lookup"><span data-stu-id="4653d-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="4653d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="4653d-107">Remarks</span></span>

<span data-ttu-id="4653d-108">Эта структура находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="4653d-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="4653d-109">Чтобы использовать его, проще всего имитируют реализации:</span><span class="sxs-lookup"><span data-stu-id="4653d-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="4653d-110">Возвращает значение, полученное от вызова `Request` метод `IXCLRDataModule*` параметра со следующими параметрами: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="4653d-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="4653d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="4653d-111">Requirements</span></span>

<span data-ttu-id="4653d-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4653d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="4653d-113">**Заголовок.** None</span><span class="sxs-lookup"><span data-stu-id="4653d-113">**Header:** None</span></span>     
<span data-ttu-id="4653d-114">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="4653d-114">**Library:** None</span></span>  
<span data-ttu-id="4653d-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4653d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="4653d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4653d-116">See also</span></span>

- [<span data-ttu-id="4653d-117">Отладка</span><span class="sxs-lookup"><span data-stu-id="4653d-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="4653d-118">Интерфейс DacpGetModuleAddress</span><span class="sxs-lookup"><span data-stu-id="4653d-118">DacpGetModuleAddress Interface</span></span>](dacpgetmoduleaddress-structure.md)
