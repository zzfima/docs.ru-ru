---
title: "Функция StrongNameFreeBuffer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: StrongNameFreeBuffer
helpviewer_keywords: StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ef48c79cc7dc0fb7d881e0cced29741431044551
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="1c140-102">Функция StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="1c140-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="1c140-103">Освобождает память, выделенная с предыдущим вызовом функции строгое имя, например [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), или [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="1c140-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="1c140-104">Эта функция устарела.</span><span class="sxs-lookup"><span data-stu-id="1c140-104">This function has been deprecated.</span></span> <span data-ttu-id="1c140-105">Используйте [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="1c140-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c140-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c140-106">Syntax</span></span>  
  
```  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c140-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="1c140-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="1c140-108">[in] Указатель на область памяти для освобождения.</span><span class="sxs-lookup"><span data-stu-id="1c140-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c140-109">Требования</span><span class="sxs-lookup"><span data-stu-id="1c140-109">Requirements</span></span>  
 <span data-ttu-id="1c140-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c140-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c140-111">**Заголовок:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="1c140-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1c140-112">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1c140-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1c140-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c140-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c140-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1c140-114">See Also</span></span>  
 [<span data-ttu-id="1c140-115">Метод StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="1c140-115">StrongNameFreeBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)  
 [<span data-ttu-id="1c140-116">Iclrstrongname-интерфейс</span><span class="sxs-lookup"><span data-stu-id="1c140-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
