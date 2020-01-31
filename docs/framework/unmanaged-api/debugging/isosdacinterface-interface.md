---
title: Интерфейс ISOSDacInterface
ms.date: 02/01/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 94349a3f7b18c8ce29bb3a71cb9d10ee4eac8036
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790479"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="baef9-102">Интерфейс ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="baef9-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="baef9-103">Предоставляет вспомогательные методы для доступа к данным из `SOS`.</span><span class="sxs-lookup"><span data-stu-id="baef9-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="baef9-104">Методы</span><span class="sxs-lookup"><span data-stu-id="baef9-104">Methods</span></span>

| <span data-ttu-id="baef9-105">Метод</span><span class="sxs-lookup"><span data-stu-id="baef9-105">Method</span></span>                                                                                                               | <span data-ttu-id="baef9-106">Описание</span><span class="sxs-lookup"><span data-stu-id="baef9-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="baef9-107">жетмесоддескдата</span><span class="sxs-lookup"><span data-stu-id="baef9-107">GetMethodDescData</span></span>](isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="baef9-108">Возвращает данные для заданного указателя MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="baef9-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="baef9-109">жетмесоддескптрфромип</span><span class="sxs-lookup"><span data-stu-id="baef9-109">GetMethodDescPtrFromIP</span></span>](isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="baef9-110">Получает указатель MethodDesc, соответствующий методу, содержащему указанный адрес собственной инструкции.</span><span class="sxs-lookup"><span data-stu-id="baef9-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="baef9-111">жетмодуледата</span><span class="sxs-lookup"><span data-stu-id="baef9-111">GetModuleData</span></span>](isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="baef9-112">Извлекает данные, соответствующие модулю, загруженному по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="baef9-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="baef9-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="baef9-113">Remarks</span></span>

<span data-ttu-id="baef9-114">Этот интерфейс находится внутри среды выполнения и не предоставляется через все файлы заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="baef9-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="baef9-115">Однако это COM-интерфейс, производный от `IUnknown` с GUID `436f00f2-b42a-4b9f-870c-e73db66ae930`, который можно получить с помощью обычных механизмов COM.</span><span class="sxs-lookup"><span data-stu-id="baef9-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="baef9-116">Требования</span><span class="sxs-lookup"><span data-stu-id="baef9-116">Requirements</span></span>

<span data-ttu-id="baef9-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baef9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="baef9-118">**Заголовок:** None</span><span class="sxs-lookup"><span data-stu-id="baef9-118">**Header:** None</span></span>  
<span data-ttu-id="baef9-119">**Библиотека:** None</span><span class="sxs-lookup"><span data-stu-id="baef9-119">**Library:** None</span></span>  
<span data-ttu-id="baef9-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="baef9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="baef9-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="baef9-121">See also</span></span>

- [<span data-ttu-id="baef9-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="baef9-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="baef9-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="baef9-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
