---
title: Интерфейс ICLRStrongName2
ms.date: 03/30/2017
api_name:
- ICLRStrongName2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName2
helpviewer_keywords:
- ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bf9e3d2df8f507e118b393007c3958358a830cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="7135c-102">Интерфейс ICLRStrongName2</span><span class="sxs-lookup"><span data-stu-id="7135c-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="7135c-103">Предоставляет возможность создавать с помощью группы SHA-2 (SHA-256, SHA-384 и SHA-512) хэш-алгоритмов Secure строгие имена.</span><span class="sxs-lookup"><span data-stu-id="7135c-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7135c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7135c-104">Methods</span></span>  
  
|<span data-ttu-id="7135c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7135c-105">Method</span></span>|<span data-ttu-id="7135c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="7135c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7135c-107">Метод StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="7135c-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="7135c-108">Возвращает открытый ключ из пары открытого и закрытого ключей и указывает хэш-алгоритм и алгоритм подписи.</span><span class="sxs-lookup"><span data-stu-id="7135c-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="7135c-109">Метод StrongNameSignatureVerificationEx2</span><span class="sxs-lookup"><span data-stu-id="7135c-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="7135c-110">Проверяет подпись сборки строгим именем, а также сопоставление ключ ECMA действительный ключ.</span><span class="sxs-lookup"><span data-stu-id="7135c-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7135c-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="7135c-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7135c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="7135c-112">Requirements</span></span>  
 <span data-ttu-id="7135c-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7135c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7135c-114">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7135c-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7135c-115">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7135c-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7135c-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7135c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
