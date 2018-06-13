---
title: Функция CloseCLREnumeration
ms.date: 03/30/2017
api_name:
- CloseCLREnumeration
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18903bd00b0a9d09365d03c155531a25dc013189
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406092"
---
# <a name="closeclrenumeration-function"></a><span data-ttu-id="ae11e-102">Функция CloseCLREnumeration</span><span class="sxs-lookup"><span data-stu-id="ae11e-102">CloseCLREnumeration Function</span></span>
<span data-ttu-id="ae11e-103">Закрывает все допустимые языка среды выполнения (CLR) продолжения запуска события находятся в массиве дескрипторов, возвращенном [функция EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)и освобождает память для массивов дескрипторов и строк пути.</span><span class="sxs-lookup"><span data-stu-id="ae11e-103">Closes any valid common language runtime (CLR) continue-startup events located in an array of handles returned by the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae11e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ae11e-104">Syntax</span></span>  
  
```  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae11e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ae11e-105">Parameters</span></span>  
 `pHandleArray`  
 <span data-ttu-id="ae11e-106">[in] Указатель на массив дескрипторов событий, возвращенные [функция EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="ae11e-106">[in] Pointer to the array of event handles returned from the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span></span>  
  
 `pStringArray`  
 <span data-ttu-id="ae11e-107">[in] Указатель на массив CLR строка пути, возвращенные [функция EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="ae11e-107">[in] Pointer to the array of CLR string paths returned from the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span></span>  
  
 `dwArrayLength`  
 <span data-ttu-id="ae11e-108">[in] Значение DWORD, содержащее размер (длину) массива `pHandleArray` или `pStringArray` (они одинаковые).</span><span class="sxs-lookup"><span data-stu-id="ae11e-108">[in] DWORD that contains the size (length) of either `pHandleArray` or `pStringArray` (they are the same).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae11e-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ae11e-109">Return Value</span></span>  
 <span data-ttu-id="ae11e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ae11e-110">S_OK</span></span>  
 <span data-ttu-id="ae11e-111">Дескрипторы, открытые [функция EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) , закрываются и освободить память, выделенная для массивов дескрипторов и строк.</span><span class="sxs-lookup"><span data-stu-id="ae11e-111">Handles opened by the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) are closed, and memory allocated for the handle and string arrays is freed.</span></span>  
  
 <span data-ttu-id="ae11e-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ae11e-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="ae11e-113">Длина массива `pHandleArray` не соответствует длине, переданной в `dwArrayLength`.</span><span class="sxs-lookup"><span data-stu-id="ae11e-113">The length of `pHandleArray` does not match the length that is passed in `dwArrayLength`.</span></span>  
  
 <span data-ttu-id="ae11e-114">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="ae11e-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="ae11e-115">Функции не удалось освободить память для массивов `pHandleArray` и `pStringArray`.</span><span class="sxs-lookup"><span data-stu-id="ae11e-115">The function is unable to free the memory for `pHandleArray` and `pStringArray`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae11e-116">Требования</span><span class="sxs-lookup"><span data-stu-id="ae11e-116">Requirements</span></span>  
 <span data-ttu-id="ae11e-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae11e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae11e-118">**Заголовок:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="ae11e-118">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="ae11e-119">**Библиотека:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="ae11e-119">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="ae11e-120">**Версии платформы .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ae11e-120">**.NET Framework Versions:** 3.5 SP1</span></span>
