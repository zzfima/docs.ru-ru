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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763728"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="fd359-102">Интерфейс ICLRStrongName2</span><span class="sxs-lookup"><span data-stu-id="fd359-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="fd359-103">Предоставляет возможность создания строгих имен, с помощью группы SHA-2 (SHA-256, SHA-384 и SHA-512) хэш-алгоритмов безопасности.</span><span class="sxs-lookup"><span data-stu-id="fd359-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fd359-104">Методы</span><span class="sxs-lookup"><span data-stu-id="fd359-104">Methods</span></span>  
  
|<span data-ttu-id="fd359-105">Метод</span><span class="sxs-lookup"><span data-stu-id="fd359-105">Method</span></span>|<span data-ttu-id="fd359-106">Описание</span><span class="sxs-lookup"><span data-stu-id="fd359-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fd359-107">Метод StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="fd359-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="fd359-108">Получает открытый ключ из пары открытого и закрытого ключей и определяет хэш-алгоритма и алгоритм подписи.</span><span class="sxs-lookup"><span data-stu-id="fd359-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="fd359-109">Метод StrongNameSignatureVerificationEx2</span><span class="sxs-lookup"><span data-stu-id="fd359-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="fd359-110">Проверяет подпись сборки со строгим именем, а также сопоставление ключа ECMA фактическую клавишу.</span><span class="sxs-lookup"><span data-stu-id="fd359-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd359-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="fd359-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd359-112">Требования</span><span class="sxs-lookup"><span data-stu-id="fd359-112">Requirements</span></span>  
 <span data-ttu-id="fd359-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd359-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd359-114">**Заголовок.** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fd359-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fd359-115">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fd359-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd359-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd359-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
