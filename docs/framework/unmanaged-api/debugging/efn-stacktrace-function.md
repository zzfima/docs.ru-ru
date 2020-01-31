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
ms.openlocfilehash: cc5093a5ba0afcccaf960e9b8776f93a061cc2f5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785668"
---
# <a name="_efn_stacktrace-function"></a><span data-ttu-id="34c89-102">\_ЕФН\_StackTrace, функция</span><span class="sxs-lookup"><span data-stu-id="34c89-102">\_EFN\_StackTrace Function</span></span>
<span data-ttu-id="34c89-103">Предоставляет текстовое представление трассировки управляемого стека и массив записей `CONTEXT`, по одной для каждого перехода между неуправляемым и управляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="34c89-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34c89-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34c89-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="34c89-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="34c89-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="34c89-106">окне Отлаживаемый клиент.</span><span class="sxs-lookup"><span data-stu-id="34c89-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="34c89-107">заполняет Текстовое представление трассировки стека.</span><span class="sxs-lookup"><span data-stu-id="34c89-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="34c89-108">заполняет Указатель на число символов в `wszTextOut`.</span><span class="sxs-lookup"><span data-stu-id="34c89-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="34c89-109">заполняет Массив контекстов перехода.</span><span class="sxs-lookup"><span data-stu-id="34c89-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="34c89-110">заполняет Указатель на число контекстов перехода в массиве.</span><span class="sxs-lookup"><span data-stu-id="34c89-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="34c89-111">окне Размер структуры контекста.</span><span class="sxs-lookup"><span data-stu-id="34c89-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="34c89-112">окне Задайте значение 0 или SOS_STACKTRACE_SHOWADDRESSES (0x01) для отображения регистра EBP и указателя ввода стека (ESP) перед каждой строкой `module!functionname`.</span><span class="sxs-lookup"><span data-stu-id="34c89-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34c89-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="34c89-113">Remarks</span></span>  
 <span data-ttu-id="34c89-114">Структура `_EFN_StackTrace` может быть вызвана из программного интерфейса WinDbg.</span><span class="sxs-lookup"><span data-stu-id="34c89-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="34c89-115">Параметры используются следующим образом.</span><span class="sxs-lookup"><span data-stu-id="34c89-115">Parameters are used as follows:</span></span>  
  
- <span data-ttu-id="34c89-116">Если `wszTextOut` имеет значение NULL и `puiTextLength` не равно null, функция возвращает длину строки в `puiTextLength`.</span><span class="sxs-lookup"><span data-stu-id="34c89-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
- <span data-ttu-id="34c89-117">Если `wszTextOut` не равно null, функция сохраняет текст в `wszTextOut` вплоть до расположения, указанного в `puiTextLength`.</span><span class="sxs-lookup"><span data-stu-id="34c89-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="34c89-118">Он возвращает значение, если в буфере достаточно места, или возвращает E_OUTOFMEMORY, если буфер недостаточно длинный.</span><span class="sxs-lookup"><span data-stu-id="34c89-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
- <span data-ttu-id="34c89-119">Переходная часть функции пропускается, если `pTransitionContexts` и `puiTransitionContextCount` равны NULL.</span><span class="sxs-lookup"><span data-stu-id="34c89-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="34c89-120">В этом случае функция предоставляет вызывающим объектам текстовые выходные данные только имен функций.</span><span class="sxs-lookup"><span data-stu-id="34c89-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
- <span data-ttu-id="34c89-121">Если `pTransitionContexts` имеет значение NULL и `puiTransitionContextCount` не равно null, функция возвращает необходимое число контекстных записей в `puiTransitionContextCount`.</span><span class="sxs-lookup"><span data-stu-id="34c89-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
- <span data-ttu-id="34c89-122">Если `pTransitionContexts` не равно null, функция обрабатывает ее как массив структур `puiTransitionContextCount`длины.</span><span class="sxs-lookup"><span data-stu-id="34c89-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="34c89-123">Размер структуры задается `uiSizeOfContext`и должен быть размером [симплеконтекст](stacktrace-simplecontext-structure.md) или `CONTEXT` для архитектуры.</span><span class="sxs-lookup"><span data-stu-id="34c89-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
- <span data-ttu-id="34c89-124">`wszTextOut` записывается в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="34c89-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- <span data-ttu-id="34c89-125">Если смещение в шестнадцатеричном формате имеет значение 0x0, смещение не записывается.</span><span class="sxs-lookup"><span data-stu-id="34c89-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
- <span data-ttu-id="34c89-126">Если в текущем потоке нет управляемого кода, функция возвращает SOS_E_NOMANAGEDCODE.</span><span class="sxs-lookup"><span data-stu-id="34c89-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
- <span data-ttu-id="34c89-127">Параметр `Flags` имеет значение 0 или SOS_STACKTRACE_SHOWADDRESSES, чтобы видеть EBP и ESP перед каждой строкой `module!functionname`.</span><span class="sxs-lookup"><span data-stu-id="34c89-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="34c89-128">По умолчанию это 0.</span><span class="sxs-lookup"><span data-stu-id="34c89-128">By default, it is 0.</span></span>  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="34c89-129">Требования</span><span class="sxs-lookup"><span data-stu-id="34c89-129">Requirements</span></span>  
 <span data-ttu-id="34c89-130">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34c89-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34c89-131">**Заголовок:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="34c89-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="34c89-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34c89-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34c89-133">См. также:</span><span class="sxs-lookup"><span data-stu-id="34c89-133">See also</span></span>

- [<span data-ttu-id="34c89-134">Глобальные статические функции отладки</span><span class="sxs-lookup"><span data-stu-id="34c89-134">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
