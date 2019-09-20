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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53384a5aa7f8d11f868057f892f7b60aac2e9f02
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799040"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="52c4e-102">Функция StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="52c4e-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="52c4e-103">Получает размер буфера, необходимый для хэша, с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="52c4e-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="52c4e-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="52c4e-104">This function has been deprecated.</span></span> <span data-ttu-id="52c4e-105">Используйте вместо этого метод [метод iclrstrongname:: StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="52c4e-105">Use the [ICLRStrongName::StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52c4e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="52c4e-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52c4e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="52c4e-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="52c4e-108">окне Хэш-алгоритм, используемый для вычисления размера буфера.</span><span class="sxs-lookup"><span data-stu-id="52c4e-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="52c4e-109">заполняет Размер возвращенного буфера в байтах.</span><span class="sxs-lookup"><span data-stu-id="52c4e-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52c4e-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="52c4e-110">Return Value</span></span>  
 <span data-ttu-id="52c4e-111">`true`При успешном завершении; в противном случае —. `false`</span><span class="sxs-lookup"><span data-stu-id="52c4e-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52c4e-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="52c4e-112">Remarks</span></span>  
 <span data-ttu-id="52c4e-113">Если функция `StrongNameHashSize` не завершается успешно, вызовите функцию [StrongNameErrorInfo](strongnameerrorinfo-function.md), чтобы получить последнюю созданную ошибку.</span><span class="sxs-lookup"><span data-stu-id="52c4e-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52c4e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="52c4e-114">Requirements</span></span>  
 <span data-ttu-id="52c4e-115">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52c4e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52c4e-116">**Заголовок.** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="52c4e-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="52c4e-117">**Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="52c4e-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="52c4e-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52c4e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52c4e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="52c4e-119">See also</span></span>

- [<span data-ttu-id="52c4e-120">Метод StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="52c4e-120">StrongNameHashSize Method</span></span>](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="52c4e-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="52c4e-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
