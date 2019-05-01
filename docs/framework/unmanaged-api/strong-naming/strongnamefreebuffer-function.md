---
title: Функция StrongNameFreeBuffer
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9bfc6491a1d18c81a44a7d9c5084f744c9b76281
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040915"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="a6f3d-102">Функция StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="a6f3d-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="a6f3d-103">Освобождает память, выделенную предыдущим вызовом функции строгого имени, такой как [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md) или [StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="a6f3d-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="a6f3d-104">Эта функция является устаревшей.</span><span class="sxs-lookup"><span data-stu-id="a6f3d-104">This function has been deprecated.</span></span> <span data-ttu-id="a6f3d-105">Используйте [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="a6f3d-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6f3d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6f3d-106">Syntax</span></span>  
  
```  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6f3d-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="a6f3d-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="a6f3d-108">[in] Указатель на область памяти для освобождения.</span><span class="sxs-lookup"><span data-stu-id="a6f3d-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6f3d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a6f3d-109">Requirements</span></span>  
 <span data-ttu-id="a6f3d-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6f3d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6f3d-111">**Заголовок.** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="a6f3d-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="a6f3d-112">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6f3d-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6f3d-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6f3d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f3d-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a6f3d-114">See also</span></span>

- [<span data-ttu-id="a6f3d-115">Метод StrongNameFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="a6f3d-115">StrongNameFreeBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="a6f3d-116">Интерфейс ICLRStrongName</span><span class="sxs-lookup"><span data-stu-id="a6f3d-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
