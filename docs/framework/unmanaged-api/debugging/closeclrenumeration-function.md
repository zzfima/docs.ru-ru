---
title: "Функция CloseCLREnumeration"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CloseCLREnumeration
api_location: dbgshim.dll
api_type: COM
f1_keywords: CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9f14b851795c92c3ce0c1e7536a4ff78fbdf927
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="closeclrenumeration-function"></a><span data-ttu-id="9bff7-102">Функция CloseCLREnumeration</span><span class="sxs-lookup"><span data-stu-id="9bff7-102">CloseCLREnumeration Function</span></span>
<span data-ttu-id="9bff7-103">Закрывает все допустимые языка среды выполнения (CLR) продолжения запуска события находятся в массиве дескрипторов, возвращенном [функция EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)и освобождает память для массивов дескрипторов и строк пути.</span><span class="sxs-lookup"><span data-stu-id="9bff7-103">Closes any valid common language runtime (CLR) continue-startup events located in an array of handles returned by the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bff7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9bff7-104">Syntax</span></span>  
  
```  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9bff7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9bff7-105">Parameters</span></span>  
 `pHandleArray`  
 <span data-ttu-id="9bff7-106">[in] Указатель на массив дескрипторов событий, возвращенные [функция EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="9bff7-106">[in] Pointer to the array of event handles returned from the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span></span>  
  
 `pStringArray`  
 <span data-ttu-id="9bff7-107">[in] Указатель на массив CLR строка пути, возвращенные [функция EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="9bff7-107">[in] Pointer to the array of CLR string paths returned from the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span></span>  
  
 `dwArrayLength`  
 <span data-ttu-id="9bff7-108">[in] Значение DWORD, содержащее размер (длину) массива `pHandleArray` или `pStringArray` (они одинаковые).</span><span class="sxs-lookup"><span data-stu-id="9bff7-108">[in] DWORD that contains the size (length) of either `pHandleArray` or `pStringArray` (they are the same).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9bff7-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="9bff7-109">Return Value</span></span>  
 <span data-ttu-id="9bff7-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9bff7-110">S_OK</span></span>  
 <span data-ttu-id="9bff7-111">Дескрипторы, открытые [функция EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) , закрываются и освободить память, выделенная для массивов дескрипторов и строк.</span><span class="sxs-lookup"><span data-stu-id="9bff7-111">Handles opened by the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) are closed, and memory allocated for the handle and string arrays is freed.</span></span>  
  
 <span data-ttu-id="9bff7-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="9bff7-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="9bff7-113">Длина массива `pHandleArray` не соответствует длине, переданной в `dwArrayLength`.</span><span class="sxs-lookup"><span data-stu-id="9bff7-113">The length of `pHandleArray` does not match the length that is passed in `dwArrayLength`.</span></span>  
  
 <span data-ttu-id="9bff7-114">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="9bff7-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9bff7-115">Функции не удалось освободить память для массивов `pHandleArray` и `pStringArray`.</span><span class="sxs-lookup"><span data-stu-id="9bff7-115">The function is unable to free the memory for `pHandleArray` and `pStringArray`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bff7-116">Требования</span><span class="sxs-lookup"><span data-stu-id="9bff7-116">Requirements</span></span>  
 <span data-ttu-id="9bff7-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bff7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bff7-118">**Заголовок:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="9bff7-118">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="9bff7-119">**Библиотека:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="9bff7-119">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="9bff7-120">**Версии платформы .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="9bff7-120">**.NET Framework Versions:** 3.5 SP1</span></span>
