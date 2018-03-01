---
title: "Функция StrongNameHashSize"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 20a0d5fc284dde7b127f1f177a448a95701ac8b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="f260e-102">Функция StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="f260e-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="f260e-103">Возвращает размер буфера, необходимый для хэша, с помощью указанного хэш-алгоритма.</span><span class="sxs-lookup"><span data-stu-id="f260e-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="f260e-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="f260e-104">This function has been deprecated.</span></span> <span data-ttu-id="f260e-105">Используйте [ICLRStrongName::StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="f260e-105">Use the [ICLRStrongName::StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f260e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f260e-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f260e-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="f260e-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="f260e-108">[in] Хэш-алгоритм, используемый для вычисления размера буфера.</span><span class="sxs-lookup"><span data-stu-id="f260e-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="f260e-109">[out] Размер возвращаемого буфера в байтах.</span><span class="sxs-lookup"><span data-stu-id="f260e-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f260e-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f260e-110">Return Value</span></span>  
 <span data-ttu-id="f260e-111">`true`При успешном завершении; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="f260e-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f260e-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="f260e-112">Remarks</span></span>  
 <span data-ttu-id="f260e-113">Если `StrongNameHashSize` функция не завершена, вызовите [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) функции для получения последнего формируемой ошибки.</span><span class="sxs-lookup"><span data-stu-id="f260e-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f260e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f260e-114">Requirements</span></span>  
 <span data-ttu-id="f260e-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f260e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f260e-116">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="f260e-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f260e-117">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f260e-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f260e-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f260e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f260e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f260e-119">See Also</span></span>  
 [<span data-ttu-id="f260e-120">Метод StrongNameHashSize</span><span class="sxs-lookup"><span data-stu-id="f260e-120">StrongNameHashSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)  
 [<span data-ttu-id="f260e-121">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="f260e-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
