---
title: Структура DacpMethodDescData
ms.date: 02/01/2019
api.name:
- DacpMethodDescData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpMethodDescData Structure
helpviewer.keywords:
- DacpMethodDescData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 567dc3942f79b6bfd29338b9103083aa64e66451
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203201"
---
# <a name="dacpmethoddescdata-structure"></a><span data-ttu-id="a9ccd-102">Структура DacpMethodDescData</span><span class="sxs-lookup"><span data-stu-id="a9ccd-102">DacpMethodDescData Structure</span></span>

<span data-ttu-id="a9ccd-103">Определяет транспорт буфер сведения среды выполнения метода.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-103">Defines a transport buffer for a method's runtime information.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="a9ccd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a9ccd-104">Syntax</span></span>

```
struct DacpMethodDescData
{
    int             bHasNativeCode;
    int             bIsDynamic;
    unsigned short  wSlotNumber;
    CLRDATA_ADDRESS NativeCodeAddr;
    CLRDATA_ADDRESS data;
    CLRDATA_ADDRESS MethodDescPtr;
    CLRDATA_ADDRESS nativeCodeInfo;
    CLRDATA_ADDRESS moduleInfo;
    mdToken         MDToken;
    CLRDATA_ADDRESS payloadGC;
    CLRDATA_ADDRESS payloadGC2;
    CLRDATA_ADDRESS managedDynamicMethodObject;
    CLRDATA_ADDRESS requestedIP;
    DacpReJitData   rejitDataCurrent;
    DacpReJitData   rejitDataRequested;
    unsigned long   cJittedRejitVersions;
};
```

## <a name="members"></a><span data-ttu-id="a9ccd-105">Участники</span><span class="sxs-lookup"><span data-stu-id="a9ccd-105">Members</span></span>

| <span data-ttu-id="a9ccd-106">Член</span><span class="sxs-lookup"><span data-stu-id="a9ccd-106">Member</span></span>                       | <span data-ttu-id="a9ccd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a9ccd-107">Description</span></span>                                                                                     |
| ---------------------------- | ----------------------------------------------------------------------------------------------- |
| `bHasNativeCode`             | <span data-ttu-id="a9ccd-108">Указывает, имеет ли среда выполнения машинного кода, доступных для данного экземпляра метода.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-108">Indicates if the runtime has native code available for the given instantiation of the method.</span></span> |
| `bIsDynamic`                 | <span data-ttu-id="a9ccd-109">Указывает, если метод создается динамически во время создания облегченного кода.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-109">Indicates if the method is generated dynamically through lightweight code generation.</span></span>           |
| `wSlotNumber`                | <span data-ttu-id="a9ccd-110">Метод номер ячейки в таблицу методов.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-110">The method's slot number in the method table.</span></span>                                                   |
| `NativeCodeAddr`             | <span data-ttu-id="a9ccd-111">Начального адреса собственного метода.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-111">The method's initial native address.</span></span>                                                            |
| `data`                       | <span data-ttu-id="a9ccd-112">Указатель на буфер, внутреннего использования средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-112">Pointer to a buffer used internally by the runtime.</span></span>                                             |
| `MethodDescPtr`              | <span data-ttu-id="a9ccd-113">Указатель на `MethodDesc` в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-113">Pointer to the `MethodDesc` in the runtime.</span></span>                                                     |
| `nativeCodeInfo`             | <span data-ttu-id="a9ccd-114">Указатель на буфер, используется внутренним образом средой выполнения для отслеживания методов.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-114">Pointer to a buffer used internally by the runtime to track methods.</span></span>                            |
| `moduleInfo`                 | <span data-ttu-id="a9ccd-115">Указатель на буфер для внутреннего применения средой выполнения сведений о модуле.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-115">Pointer to a buffer used internally by the runtime for module information.</span></span>                      |
| `MDToken`                    | <span data-ttu-id="a9ccd-116">Токен, связанный с данный метод.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-116">Token associated with the given method.</span></span>                                                         |
| `payloadGC`                  | <span data-ttu-id="a9ccd-117">Указатель на буфер сбора мусора внутреннего использования средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-117">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `payloadGC2`                 | <span data-ttu-id="a9ccd-118">Указатель на буфер сбора мусора внутреннего использования средой выполнения.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-118">Pointer to a garbage collection buffer used internally by the runtime.</span></span>                          |
| `managedDynamicMethodObject` | <span data-ttu-id="a9ccd-119">Если метод является динамическим, среда выполнения использует этот буфер внутренне, для отслеживания данных.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-119">If the method is dynamic, the runtime uses this buffer internally for information tracking.</span></span>     |
| `requestedIP`                | <span data-ttu-id="a9ccd-120">Используется для заполнения структуры на каждый запрос при указанного адреса машинного кода.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-120">Used to populate the structure per request when given a native code address.</span></span>                    |
| `rejitDataCurrent`           | <span data-ttu-id="a9ccd-121">Сведения о последней инструментированной версии метода.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-121">Information about the latest instrumented version of the method.</span></span>                                   |
| `rejitDataRequested`         | <span data-ttu-id="a9ccd-122">Rejit сведения для запрошенного собственного адреса.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-122">Rejit information for the requested native address.</span></span>                                             |
| `cJittedRejitVersions`       | <span data-ttu-id="a9ccd-123">Количество раз, когда метод был rejitted через инструментарий.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-123">Number of times the method has been rejitted through instrumentation.</span></span>                           |

## <a name="remarks"></a><span data-ttu-id="a9ccd-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="a9ccd-124">Remarks</span></span>

<span data-ttu-id="a9ccd-125">Эта структура находится внутри среды выполнения и не предоставляется через любой заголовков или библиотек.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-125">This structure lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="a9ccd-126">Чтобы использовать его, определите структуру, как указано выше.</span><span class="sxs-lookup"><span data-stu-id="a9ccd-126">To use it, define the structure as specified above.</span></span>

## <a name="requirements"></a><span data-ttu-id="a9ccd-127">Требования</span><span class="sxs-lookup"><span data-stu-id="a9ccd-127">Requirements</span></span>
<span data-ttu-id="a9ccd-128">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9ccd-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="a9ccd-129">**Заголовок.** Нет</span><span class="sxs-lookup"><span data-stu-id="a9ccd-129">**Header:** None</span></span>  
<span data-ttu-id="a9ccd-130">**Библиотека:** Нет</span><span class="sxs-lookup"><span data-stu-id="a9ccd-130">**Library:** None</span></span>  
<span data-ttu-id="a9ccd-131">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a9ccd-131">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="a9ccd-132">См. также</span><span class="sxs-lookup"><span data-stu-id="a9ccd-132">See also</span></span>

- [<span data-ttu-id="a9ccd-133">Отладка</span><span class="sxs-lookup"><span data-stu-id="a9ccd-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="a9ccd-134">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="a9ccd-134">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="a9ccd-135">Общие типы данных</span><span class="sxs-lookup"><span data-stu-id="a9ccd-135">Common Data Types</span></span>](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)
