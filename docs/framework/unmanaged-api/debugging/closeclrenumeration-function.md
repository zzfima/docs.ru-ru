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
ms.openlocfilehash: a9eb9bb1e4abeb98d8d0ba2b052612d918c45f22
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741083"
---
# <a name="closeclrenumeration-function"></a><span data-ttu-id="707e4-102">Функция CloseCLREnumeration</span><span class="sxs-lookup"><span data-stu-id="707e4-102">CloseCLREnumeration Function</span></span>
<span data-ttu-id="707e4-103">Закрывает любой допустимый событий среды CLR (CLR) продолжения запуска находятся в массиве дескрипторов, возвращенном [функция EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)и освобождает память для массивов дескрипторов и строк пути.</span><span class="sxs-lookup"><span data-stu-id="707e4-103">Closes any valid common language runtime (CLR) continue-startup events located in an array of handles returned by the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="707e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="707e4-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="707e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="707e4-105">Parameters</span></span>  
 `pHandleArray`  
 <span data-ttu-id="707e4-106">[in] Указатель на массив дескрипторов событий, возвращенных из [функция EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="707e4-106">[in] Pointer to the array of event handles returned from the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span></span>  
  
 `pStringArray`  
 <span data-ttu-id="707e4-107">[in] Указатель на массив путей строки среды CLR, возвращенный [функция EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="707e4-107">[in] Pointer to the array of CLR string paths returned from the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md).</span></span>  
  
 `dwArrayLength`  
 <span data-ttu-id="707e4-108">[in] Значение DWORD, содержащее размер (длину) массива `pHandleArray` или `pStringArray` (они одинаковые).</span><span class="sxs-lookup"><span data-stu-id="707e4-108">[in] DWORD that contains the size (length) of either `pHandleArray` or `pStringArray` (they are the same).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="707e4-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="707e4-109">Return Value</span></span>  
 <span data-ttu-id="707e4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="707e4-110">S_OK</span></span>  
 <span data-ttu-id="707e4-111">Дескрипторы, открытые [функция EnumerateCLRs](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) будут закрыты, и освободить память, выделенная для массивов дескрипторов и строк.</span><span class="sxs-lookup"><span data-stu-id="707e4-111">Handles opened by the [EnumerateCLRs function](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md) are closed, and memory allocated for the handle and string arrays is freed.</span></span>  
  
 <span data-ttu-id="707e4-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="707e4-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="707e4-113">Длина массива `pHandleArray` не соответствует длине, переданной в `dwArrayLength`.</span><span class="sxs-lookup"><span data-stu-id="707e4-113">The length of `pHandleArray` does not match the length that is passed in `dwArrayLength`.</span></span>  
  
 <span data-ttu-id="707e4-114">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="707e4-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="707e4-115">Функции не удалось освободить память для массивов `pHandleArray` и `pStringArray`.</span><span class="sxs-lookup"><span data-stu-id="707e4-115">The function is unable to free the memory for `pHandleArray` and `pStringArray`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="707e4-116">Требования</span><span class="sxs-lookup"><span data-stu-id="707e4-116">Requirements</span></span>  
 <span data-ttu-id="707e4-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="707e4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="707e4-118">**Заголовок:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="707e4-118">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="707e4-119">**Библиотека:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="707e4-119">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="707e4-120">**Версии платформы .NET framework:** 3.5 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="707e4-120">**.NET Framework Versions:** 3.5 SP1</span></span>
