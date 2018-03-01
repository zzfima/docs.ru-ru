---
title: "Функция EnumerateCLRs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EnumerateCLRs
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- EnumerateCLRs
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- EnumerateCLRs function
ms.assetid: f8d50cb3-ec4f-4529-8fe3-bd61fd28e13c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6539b471d6a3075bb4cec69b382cf7702a439d5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="enumerateclrs-function"></a><span data-ttu-id="d7da2-102">Функция EnumerateCLRs</span><span class="sxs-lookup"><span data-stu-id="d7da2-102">EnumerateCLRs Function</span></span>
<span data-ttu-id="d7da2-103">Предоставляет механизм для перечисления сред CLR в процессе.</span><span class="sxs-lookup"><span data-stu-id="d7da2-103">Provides a mechanism for enumerating the CLRs in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7da2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7da2-104">Syntax</span></span>  
  
```  
HRESULT EnumerateCLRs (  
    [in]  DWORD      debuggeePID,  
    [out] HANDLE**   ppHandleArrayOut,  
    [out] LPWSTR**   ppStringArrayOut,  
    [out] DWORD*     pdwArrayLengthOut  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d7da2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7da2-105">Parameters</span></span>  
 `debuggeePID`  
 <span data-ttu-id="d7da2-106">[in] Идентификатор процесса, из которого будут перечислены загруженные среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d7da2-106">[in] Process identifier of the process from which loaded CLRs will be enumerated.</span></span>  
  
 `ppHandleArrayOut`  
 <span data-ttu-id="d7da2-107">[out] Указатель на массив, содержащий дескрипторы событий, которые используются для продолжения запуска среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d7da2-107">[out] Pointer to an array containing event handles that are used to continue a CLR startup.</span></span> <span data-ttu-id="d7da2-108">Не все дескрипторы в массиве могут быть допустимыми.</span><span class="sxs-lookup"><span data-stu-id="d7da2-108">Each handle in the array is not guaranteed to be valid.</span></span> <span data-ttu-id="d7da2-109">Если дескриптор допустимый, его следует использовать как событие  продолжения запуска для соответствующей среды выполнения, находящейся по тому же индексу `ppStringArrayOut`.</span><span class="sxs-lookup"><span data-stu-id="d7da2-109">If valid, the handle is to be used as the continue-startup event for the corresponding runtime located in the same index of `ppStringArrayOut`.</span></span>  
  
 `ppStringArrayOut`  
 <span data-ttu-id="d7da2-110">[out] Указатель на массив строк, определяющих полные пути к средам CLR, загруженным в процессе.</span><span class="sxs-lookup"><span data-stu-id="d7da2-110">[out] Pointer to an array of strings that specify full paths to CLRs loaded in the process.</span></span>  
  
 `pdwArrayLengthOut`  
 <span data-ttu-id="d7da2-111">[out] Указатель на значение DWORD, содержащее длину одинакового размера массивов `ppHandleArrayOut` и `pdwArrayLengthOut`.</span><span class="sxs-lookup"><span data-stu-id="d7da2-111">[out] Pointer to a DWORD that contains the length of the equally sized `ppHandleArrayOut` and `pdwArrayLengthOut`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7da2-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d7da2-112">Return Value</span></span>  
 <span data-ttu-id="d7da2-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d7da2-113">S_OK</span></span>  
 <span data-ttu-id="d7da2-114">Количество сред CLR в процессе успешно определено, и соответствующие массивы дескрипторов и путей заполнены должным образом.</span><span class="sxs-lookup"><span data-stu-id="d7da2-114">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="d7da2-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d7da2-115">E_INVALIDARG</span></span>  
 <span data-ttu-id="d7da2-116">Либо `ppHandleArrayOut`, либо `ppStringArrayOut` имеет значение null, или `pdwArrayLengthOut` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="d7da2-116">Either `ppHandleArrayOut` or `ppStringArrayOut` is null, or `pdwArrayLengthOut` is null.</span></span>  
  
 <span data-ttu-id="d7da2-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d7da2-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="d7da2-118">Функции не удалось выделить достаточно памяти для массивов дескрипторов и путей.</span><span class="sxs-lookup"><span data-stu-id="d7da2-118">The function is unable to allocate enough memory for the handle and path arrays.</span></span>  
  
 <span data-ttu-id="d7da2-119">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="d7da2-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="d7da2-120">Не удалось перечислить загруженные среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d7da2-120">Unable to enumerate loaded CLRs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7da2-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="d7da2-121">Remarks</span></span>  
 <span data-ttu-id="d7da2-122">Для целевого процесса, который определяется идентификатором `debuggeePID`, функция возвращает массив путей `ppStringArrayOut` в среды CLR, загруженные в процесс; массив дескрипторов событий `ppHandleArrayOut`, который может содержать событие продолжения запуска для среды CLR с тем же индексом, и размер массивов `pdwArrayLengthOut`, который задает число загружаемых CLR.</span><span class="sxs-lookup"><span data-stu-id="d7da2-122">For a target process that is identified by `debuggeePID`, the function returns an array of paths, `ppStringArrayOut`, to CLRs loaded in the process; an array of event handles, `ppHandleArrayOut`, which may contain a continue-startup event for the CLR at the same index; and the size of the arrays, `pdwArrayLengthOut`, which specifies the number of CLRs that are loaded.</span></span>  
  
 <span data-ttu-id="d7da2-123">В операционной системе Windows `debuggeePID` сопоставляется с идентификатором процесса ОС.</span><span class="sxs-lookup"><span data-stu-id="d7da2-123">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="d7da2-124">Память для `ppHandleArrayOut` и `ppStringArrayOut` выделяется этой функцией.</span><span class="sxs-lookup"><span data-stu-id="d7da2-124">The memory for `ppHandleArrayOut` and `ppStringArrayOut` are allocated by this function.</span></span> <span data-ttu-id="d7da2-125">Чтобы освободить выделенную память, необходимо вызвать [функция CloseCLREnumeration](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md).</span><span class="sxs-lookup"><span data-stu-id="d7da2-125">To free the memory allocated, you must call [CloseCLREnumeration Function](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md).</span></span>  
  
 <span data-ttu-id="d7da2-126">Эта функция может вызываться с параметрами обоих массивов, имеющими значение null, для возврата числа CLR в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="d7da2-126">This function can be called with both array parameters set to null in order to return the count of CLRs in the target process.</span></span> <span data-ttu-id="d7da2-127">Из этого числа вызывающий объект может определить размер буфера, который будет создан: `(sizeof(HANDLE) * count) + (sizeof(LPWSTR) * count) + (sizeof(WCHAR*) * count * MAX_PATH)`.</span><span class="sxs-lookup"><span data-stu-id="d7da2-127">From this count, a caller can infer the size of the buffer that will be created: `(sizeof(HANDLE) * count) + (sizeof(LPWSTR) * count) + (sizeof(WCHAR*) * count * MAX_PATH)`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7da2-128">Требования</span><span class="sxs-lookup"><span data-stu-id="d7da2-128">Requirements</span></span>  
 <span data-ttu-id="d7da2-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7da2-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7da2-130">**Заголовок:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="d7da2-130">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="d7da2-131">**Библиотека:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="d7da2-131">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="d7da2-132">**Версии платформы .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="d7da2-132">**.NET Framework Versions:** 3.5 SP1</span></span>
