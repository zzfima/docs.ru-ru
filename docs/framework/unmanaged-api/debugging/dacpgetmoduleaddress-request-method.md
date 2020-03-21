---
title: DacpGetModuleАдрес::Запрос Метод
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
ms.openlocfilehash: 6850dc256a70e0c0343104b3904e9eda62d11e7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179198"
---
# <a name="dacpgetmoduleaddressrequest-method"></a><span data-ttu-id="79b99-102">DacpGetModuleАдрес::Запрос Метод</span><span class="sxs-lookup"><span data-stu-id="79b99-102">DacpGetModuleAddress::Request Method</span></span>

<span data-ttu-id="79b99-103">Выполняет запрос на заселяют структуру из заданной структуры времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="79b99-103">Performs a request to populate the structure from the given runtime structure.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="79b99-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79b99-104">Syntax</span></span>

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a><span data-ttu-id="79b99-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="79b99-105">Parameters</span></span>

`pDataModule`\
<span data-ttu-id="79b99-106">(в) Указатель на модуль данных семян.</span><span class="sxs-lookup"><span data-stu-id="79b99-106">[in] A pointer to the seed data module.</span></span>

## <a name="remarks"></a><span data-ttu-id="79b99-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="79b99-107">Remarks</span></span>

<span data-ttu-id="79b99-108">Эта структура живет в времени выполнения и не подвергается воздействию каких-либо заголовков или файлов библиотек.</span><span class="sxs-lookup"><span data-stu-id="79b99-108">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="79b99-109">Проще всего имитировать реализацию:</span><span class="sxs-lookup"><span data-stu-id="79b99-109">To use it, the easiest way is to mimic the implementation:</span></span>

- <span data-ttu-id="79b99-110">Возврат значения, полученного `Request` от вызова `IXCLRDataModule*` метода по параметру со следующими параметрами:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span><span class="sxs-lookup"><span data-stu-id="79b99-110">Return the value obtained from calling the `Request` method on the `IXCLRDataModule*` parameter with the following parameters: `((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`</span></span>

## <a name="requirements"></a><span data-ttu-id="79b99-111">Требования</span><span class="sxs-lookup"><span data-stu-id="79b99-111">Requirements</span></span>

<span data-ttu-id="79b99-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79b99-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="79b99-113">**Заголовок:** Нет **библиотеки:** Нет</span><span class="sxs-lookup"><span data-stu-id="79b99-113">**Header:** None **Library:** None</span></span>  
<span data-ttu-id="79b99-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="79b99-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="79b99-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="79b99-115">See also</span></span>

- [<span data-ttu-id="79b99-116">Отладки</span><span class="sxs-lookup"><span data-stu-id="79b99-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="79b99-117">Интерфейс DacpGetModuleАдрес</span><span class="sxs-lookup"><span data-stu-id="79b99-117">DacpGetModuleAddress Interface</span></span>](dacpgetmoduleaddress-structure.md)
