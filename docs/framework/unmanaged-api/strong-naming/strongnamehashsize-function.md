---
title: Функция StrongNameHashSize
ms.date: 03/30/2017
api_name:
- StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameHashSize
helpviewer_keywords:
- StrongNameHashSize function [.NET Framework strong naming]
ms.assetid: 738c98d7-a60c-45fe-a296-220af05e6991
topic_type:
- apiref
ms.openlocfilehash: c656f73748faf8be7124be65f3ed455f2d5fd07a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105190"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="5504a-102">Функция StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="5504a-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="5504a-103">Получает размер буфера, необходимый для хэша, с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="5504a-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="5504a-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="5504a-104">This function has been deprecated.</span></span> <span data-ttu-id="5504a-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5504a-105">Use the [ICLRStrongName::StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5504a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5504a-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5504a-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="5504a-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="5504a-108">окне Хэш-алгоритм, используемый для вычисления размера буфера.</span><span class="sxs-lookup"><span data-stu-id="5504a-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="5504a-109">заполняет Размер возвращенного буфера в байтах.</span><span class="sxs-lookup"><span data-stu-id="5504a-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5504a-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5504a-110">Return Value</span></span>  
 <span data-ttu-id="5504a-111">`true` при успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="5504a-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5504a-112">Заметки</span><span class="sxs-lookup"><span data-stu-id="5504a-112">Remarks</span></span>  
 <span data-ttu-id="5504a-113">Если функция `StrongNameHashSize` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="5504a-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5504a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="5504a-114">Requirements</span></span>  
 <span data-ttu-id="5504a-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5504a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5504a-116">**Заголовок:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="5504a-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5504a-117">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5504a-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5504a-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5504a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5504a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5504a-119">See also</span></span>

- [<span data-ttu-id="5504a-120">Метод StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="5504a-120">StrongNameHashSize Method</span></span>](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="5504a-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="5504a-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
