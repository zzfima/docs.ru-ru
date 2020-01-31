---
title: Интерфейс IXCLRDataModule
ms.date: 01/16/2019
api.name:
- IXCLRDataModule Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule Interface
helpviewer.keywords:
- IXCLRDataModule Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 8757642db6c4375cf55d1f7288669c4c8a752a38
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790394"
---
# <a name="ixclrdatamodule-interface"></a><span data-ttu-id="ae3df-102">Интерфейс IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="ae3df-102">IXCLRDataModule Interface</span></span>

<span data-ttu-id="ae3df-103">Предоставляет методы для запроса сведений о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="ae3df-103">Provides methods for querying information about a loaded module.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="ae3df-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ae3df-104">Methods</span></span>

| <span data-ttu-id="ae3df-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ae3df-105">Method</span></span>                                                                                                                                | <span data-ttu-id="ae3df-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ae3df-106">Description</span></span>                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="ae3df-107">жетмесоддефинитионбитокен</span><span class="sxs-lookup"><span data-stu-id="ae3df-107">GetMethodDefinitionByToken</span></span>](ixclrdatamodule-getmethoddefinitionbytoken-method.md) | <span data-ttu-id="ae3df-108">Возвращает определение метода, соответствующее заданному маркеру метаданных.</span><span class="sxs-lookup"><span data-stu-id="ae3df-108">Gets the method definition corresponding to a given metadata token.</span></span> |
| [<span data-ttu-id="ae3df-109">Запрос</span><span class="sxs-lookup"><span data-stu-id="ae3df-109">Request</span></span>](ixclrdatamodule-request-method.md)                                       | <span data-ttu-id="ae3df-110">Запросы на заполнение буфера данными модуля.</span><span class="sxs-lookup"><span data-stu-id="ae3df-110">Requests to populate the buffer given with the module's data.</span></span>       |
| [<span data-ttu-id="ae3df-111">жетверсионид</span><span class="sxs-lookup"><span data-stu-id="ae3df-111">GetVersionId</span></span>](ixclrdatamodule-getversionid-method.md)                             | <span data-ttu-id="ae3df-112">Возвращает идентификатор версии модуля.</span><span class="sxs-lookup"><span data-stu-id="ae3df-112">Gets the module's version ID.</span></span>                                       |

## <a name="remarks"></a><span data-ttu-id="ae3df-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="ae3df-113">Remarks</span></span>

<span data-ttu-id="ae3df-114">Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="ae3df-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="ae3df-115">Однако это COM-интерфейс, производный от `IUnknown` с GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2`, который можно получить с помощью обычных механизмов COM.</span><span class="sxs-lookup"><span data-stu-id="ae3df-115">However, it's a COM interface that derives from `IUnknown` with GUID `88E32849-0A0A-4cb0-9022-7CD2E9E139E2` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="ae3df-116">Требования</span><span class="sxs-lookup"><span data-stu-id="ae3df-116">Requirements</span></span>

<span data-ttu-id="ae3df-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae3df-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="ae3df-118">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="ae3df-118">**Header:** None</span></span>  
<span data-ttu-id="ae3df-119">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="ae3df-119">**Library:** None</span></span>  
<span data-ttu-id="ae3df-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ae3df-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="ae3df-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="ae3df-121">See also</span></span>

- [<span data-ttu-id="ae3df-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="ae3df-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="ae3df-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ae3df-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
