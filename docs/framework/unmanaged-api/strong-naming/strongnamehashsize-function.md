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
ms.openlocfilehash: 1ed8b6f047f26235e984fb514381a9b1d85543ec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675136"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="e5011-102">Функция StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="e5011-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="e5011-103">Получает размер буфера, необходимый для хэша, с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="e5011-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="e5011-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="e5011-104">This function has been deprecated.</span></span> <span data-ttu-id="e5011-105">Используйте [ICLRStrongName::StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="e5011-105">Use the [ICLRStrongName::StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5011-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5011-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e5011-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e5011-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="e5011-108">[in] Хэш-алгоритм, используемый для вычисления размера буфера.</span><span class="sxs-lookup"><span data-stu-id="e5011-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="e5011-109">[out] Возвращаемый размер буфера в байтах.</span><span class="sxs-lookup"><span data-stu-id="e5011-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5011-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e5011-110">Return Value</span></span>  
 <span data-ttu-id="e5011-111">`true` После успешного выполнения; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="e5011-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5011-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="e5011-112">Remarks</span></span>  
 <span data-ttu-id="e5011-113">Если `StrongNameHashSize` функция не завершена, вызвать [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="e5011-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5011-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e5011-114">Requirements</span></span>  
 <span data-ttu-id="e5011-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5011-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5011-116">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="e5011-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e5011-117">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e5011-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e5011-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5011-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5011-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e5011-119">See also</span></span>
- [<span data-ttu-id="e5011-120">Метод StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="e5011-120">StrongNameHashSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="e5011-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="e5011-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
