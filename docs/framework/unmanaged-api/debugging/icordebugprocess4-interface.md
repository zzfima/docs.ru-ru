---
title: Интерфейс ICorDebugProcess4
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4
helpviewer_keywords:
- ICorDebugProcess4 interface [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 1bdc958f2516bcd7c2eb74312fbf478e6d49535a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948812"
---
# <a name="icordebugprocess4-interface"></a><span data-ttu-id="f294f-102">Интерфейс ICorDebugProcess4</span><span class="sxs-lookup"><span data-stu-id="f294f-102">ICorDebugProcess4 Interface</span></span>

<span data-ttu-id="f294f-103">Обеспечивает поддержку вне контроля выполнения процесса.</span><span class="sxs-lookup"><span data-stu-id="f294f-103">Provides support for out of process execution control.</span></span>

## <a name="methods"></a><span data-ttu-id="f294f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f294f-104">Methods</span></span>

| <span data-ttu-id="f294f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f294f-105">Method</span></span>                                                                 | <span data-ttu-id="f294f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f294f-106">Description</span></span>                                                                                             |
| ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="f294f-107">ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="f294f-107">ProcessStateChanged</span></span>](icordebugprocess4-processstatechanged-method.md) | <span data-ttu-id="f294f-108">Уведомляет конвейера ICorDebug о том, что внепроцессные отладчик процесс продолжает выполнение отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="f294f-108">Notifies the ICorDebug pipeline that the out of process debugger is continuing the debugee's execution.</span></span> |

## <a name="remarks"></a><span data-ttu-id="f294f-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="f294f-109">Remarks</span></span>

<span data-ttu-id="f294f-110">Этот интерфейс находится внутри среды выполнения и не предоставляется с помощью любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="f294f-110">This interface lives inside the runtime and isn't exposed through any headers or library files.</span></span> <span data-ttu-id="f294f-111">Однако это COM-интерфейс, наследуемый от `IUnknown` с идентификатором GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` , можно получить с помощью обычных механизмов COM.</span><span class="sxs-lookup"><span data-stu-id="f294f-111">However, it's a COM interface that derives from `IUnknown` with GUID `E930C679-78AF-4953-8AB7-B0AABF0F9F80` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="f294f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="f294f-112">Requirements</span></span>

<span data-ttu-id="f294f-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f294f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="f294f-114">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="f294f-114">**Header:** None</span></span>

<span data-ttu-id="f294f-115">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="f294f-115">**Library:** None</span></span>

<span data-ttu-id="f294f-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f294f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f294f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f294f-117">See also</span></span>

- [<span data-ttu-id="f294f-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f294f-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f294f-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="f294f-119">Debugging</span></span>](index.md)
