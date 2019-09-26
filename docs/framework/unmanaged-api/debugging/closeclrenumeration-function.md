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
ms.openlocfilehash: 3a05a779d4a56eb8f881da1824d5ffaa363b5a01
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274283"
---
# <a name="closeclrenumeration-function"></a><span data-ttu-id="fc863-102">Функция CloseCLREnumeration</span><span class="sxs-lookup"><span data-stu-id="fc863-102">CloseCLREnumeration Function</span></span>
<span data-ttu-id="fc863-103">Закрывает все допустимые события продолжения запуска среды CLR, расположенные в массиве дескрипторов, возвращаемых [функцией EnumerateCLRs](enumerateclrs-function.md), и освобождает память для массивов дескрипторов и строковых путей.</span><span class="sxs-lookup"><span data-stu-id="fc863-103">Closes any valid common language runtime (CLR) continue-startup events located in an array of handles returned by the [EnumerateCLRs function](enumerateclrs-function.md), and frees the memory for the handle and string path arrays.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc863-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc863-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc863-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fc863-105">Parameters</span></span>  
 `pHandleArray`  
 <span data-ttu-id="fc863-106">окне Указатель на массив дескрипторов событий, возвращаемых [функцией EnumerateCLRs](enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="fc863-106">[in] Pointer to the array of event handles returned from the [EnumerateCLRs function](enumerateclrs-function.md).</span></span>  
  
 `pStringArray`  
 <span data-ttu-id="fc863-107">окне Указатель на массив строковых путей среды CLR, возвращенных [функцией EnumerateCLRs](enumerateclrs-function.md).</span><span class="sxs-lookup"><span data-stu-id="fc863-107">[in] Pointer to the array of CLR string paths returned from the [EnumerateCLRs function](enumerateclrs-function.md).</span></span>  
  
 `dwArrayLength`  
 <span data-ttu-id="fc863-108">[in] Значение DWORD, содержащее размер (длину) массива `pHandleArray` или `pStringArray` (они одинаковые).</span><span class="sxs-lookup"><span data-stu-id="fc863-108">[in] DWORD that contains the size (length) of either `pHandleArray` or `pStringArray` (they are the same).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fc863-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fc863-109">Return Value</span></span>  
 <span data-ttu-id="fc863-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fc863-110">S_OK</span></span>  
 <span data-ttu-id="fc863-111">Дескрипторы, открытые [функцией EnumerateCLRs](enumerateclrs-function.md) , закрываются, а память, выделенная для дескрипторов и массивов строк, освобождается.</span><span class="sxs-lookup"><span data-stu-id="fc863-111">Handles opened by the [EnumerateCLRs function](enumerateclrs-function.md) are closed, and memory allocated for the handle and string arrays is freed.</span></span>  
  
 <span data-ttu-id="fc863-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="fc863-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="fc863-113">Длина массива `pHandleArray` не соответствует длине, переданной в `dwArrayLength`.</span><span class="sxs-lookup"><span data-stu-id="fc863-113">The length of `pHandleArray` does not match the length that is passed in `dwArrayLength`.</span></span>  
  
 <span data-ttu-id="fc863-114">E_FAIL (или другие коды возврата E_)</span><span class="sxs-lookup"><span data-stu-id="fc863-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="fc863-115">Функции не удалось освободить память для массивов `pHandleArray` и `pStringArray`.</span><span class="sxs-lookup"><span data-stu-id="fc863-115">The function is unable to free the memory for `pHandleArray` and `pStringArray`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc863-116">Требования</span><span class="sxs-lookup"><span data-stu-id="fc863-116">Requirements</span></span>  
 <span data-ttu-id="fc863-117">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc863-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc863-118">**Заголовок:** dbgshim. h</span><span class="sxs-lookup"><span data-stu-id="fc863-118">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="fc863-119">**Библиотека:** dbgshim. dll</span><span class="sxs-lookup"><span data-stu-id="fc863-119">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="fc863-120">**.NET Framework версии:** 3.5 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="fc863-120">**.NET Framework Versions:** 3.5 SP1</span></span>
