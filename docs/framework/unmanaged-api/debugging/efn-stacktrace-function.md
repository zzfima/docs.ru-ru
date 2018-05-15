---
title: Функция _EFN_StackTrace
ms.date: 03/30/2017
api_name:
- _EFN_StackTrace
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_StackTrace
helpviewer_keywords:
- _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 39a249108d10e5dc382775378e2d6b84bba87356
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="efnstacktrace-function"></a><span data-ttu-id="cb6be-102">Функция _EFN_StackTrace</span><span class="sxs-lookup"><span data-stu-id="cb6be-102">_EFN_StackTrace Function</span></span>
<span data-ttu-id="cb6be-103">Предоставляет текстовое представление трассировки управляемого стека и массив записей `CONTEXT`, по одной для каждого перехода между неуправляемым и управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="cb6be-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb6be-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb6be-104">Syntax</span></span>  
  
```  
HRESULT CALLBACK _EFN_StackTrace(  
    [in]  PDEBUG_CLIENT  Client,  
    [out] WCHAR          wszTextOut[],  
    [out] size_t         *puiTextLength,  
    [out] LPVOID         pTransitionContexts,  
    [out] size_t         *puiTransitionContextCount,  
    [in]  size_t         uiSizeOfContext,  
    [in]  DWORD          Flags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb6be-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cb6be-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="cb6be-106">[in] Клиент которого выполняется отладка.</span><span class="sxs-lookup"><span data-stu-id="cb6be-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="cb6be-107">[out] Текстовое представление трассировки стека.</span><span class="sxs-lookup"><span data-stu-id="cb6be-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="cb6be-108">[out] Указатель на число символов в `wszTextOut`.</span><span class="sxs-lookup"><span data-stu-id="cb6be-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="cb6be-109">[out] Массив контексты перехода.</span><span class="sxs-lookup"><span data-stu-id="cb6be-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="cb6be-110">[out] Указатель на число контекстов перехода в массиве.</span><span class="sxs-lookup"><span data-stu-id="cb6be-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="cb6be-111">[in] Размер структуры контекста.</span><span class="sxs-lookup"><span data-stu-id="cb6be-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="cb6be-112">[in] Значение 0 или SOS_STACKTRACE_SHOWADDRESSES (0x01) для отображения регистр EBP и указатель стека ввод (ESP) перед каждой `module!functionname` строки.</span><span class="sxs-lookup"><span data-stu-id="cb6be-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb6be-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="cb6be-113">Remarks</span></span>  
 <span data-ttu-id="cb6be-114">`_EFN_StackTrace` Структуру может вызываться из программный интерфейс WinDbg.</span><span class="sxs-lookup"><span data-stu-id="cb6be-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="cb6be-115">Параметры используются следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cb6be-115">Parameters are used as follows:</span></span>  
  
-   <span data-ttu-id="cb6be-116">Если `wszTextOut` имеет значение null и `puiTextLength` — не null, функция возвращает длину строки в `puiTextLength`.</span><span class="sxs-lookup"><span data-stu-id="cb6be-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
-   <span data-ttu-id="cb6be-117">Если `wszTextOut` — не null, функция сохраняет текст в `wszTextOut` до местоположения, указанного параметром `puiTextLength`.</span><span class="sxs-lookup"><span data-stu-id="cb6be-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="cb6be-118">Он возвращает успешно, если было достаточно места в буфере или возвращает значение E_OUTOFMEMORY, если буфер недостаточно длинный.</span><span class="sxs-lookup"><span data-stu-id="cb6be-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
-   <span data-ttu-id="cb6be-119">Переход части функции учитывается, если `pTransitionContexts` и `puiTransitionContextCount` оба имеют значение null.</span><span class="sxs-lookup"><span data-stu-id="cb6be-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="cb6be-120">В этом случае функция предоставляет вызывающим объектам с помощью текстовых выходных данных только имена функций.</span><span class="sxs-lookup"><span data-stu-id="cb6be-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
-   <span data-ttu-id="cb6be-121">Если `pTransitionContexts` имеет значение null и `puiTransitionContextCount` — не null, функция возвращает необходимое количество записей контекста в `puiTransitionContextCount`.</span><span class="sxs-lookup"><span data-stu-id="cb6be-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
-   <span data-ttu-id="cb6be-122">Если `pTransitionContexts` — не null, функция воспринимает его как массив структур длины `puiTransitionContextCount`.</span><span class="sxs-lookup"><span data-stu-id="cb6be-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="cb6be-123">Размер структуры определяется `uiSizeOfContext`, и должен быть размер [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) или `CONTEXT` для архитектуры.</span><span class="sxs-lookup"><span data-stu-id="cb6be-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
-   <span data-ttu-id="cb6be-124">`wszTextOut` записывается в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="cb6be-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
-   <span data-ttu-id="cb6be-125">Если в шестнадцатеричном формате смещение равно 0x0, смещения не записывается.</span><span class="sxs-lookup"><span data-stu-id="cb6be-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
-   <span data-ttu-id="cb6be-126">Если нет управляемого кода в потоке в данный момент в контексте, функция возвращает значение SOS_E_NOMANAGEDCODE.</span><span class="sxs-lookup"><span data-stu-id="cb6be-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
-   <span data-ttu-id="cb6be-127">`Flags` Параметр имеет значение 0 или SOS_STACKTRACE_SHOWADDRESSES для просмотра EBP и ESP перед каждой `module!functionname` строки.</span><span class="sxs-lookup"><span data-stu-id="cb6be-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="cb6be-128">По умолчанию — 0.</span><span class="sxs-lookup"><span data-stu-id="cb6be-128">By default, it is 0.</span></span>  
  
    ```  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="cb6be-129">Требования</span><span class="sxs-lookup"><span data-stu-id="cb6be-129">Requirements</span></span>  
 <span data-ttu-id="cb6be-130">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb6be-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb6be-131">**Заголовок:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="cb6be-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="cb6be-132">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb6be-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb6be-133">См. также</span><span class="sxs-lookup"><span data-stu-id="cb6be-133">See Also</span></span>  
 [<span data-ttu-id="cb6be-134">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="cb6be-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
