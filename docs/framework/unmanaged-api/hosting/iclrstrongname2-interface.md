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
ms.openlocfilehash: bc871c29f53a9ea4451a0fc1c747939724b0da87
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092248"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="2a51f-102">Интерфейс ICLRStrongName2</span><span class="sxs-lookup"><span data-stu-id="2a51f-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="2a51f-103">Предоставляет возможность создания строгих имен с помощью группы SHA-2 алгоритмов безопасных хэширования (SHA-256, SHA-384 и SHA-512).</span><span class="sxs-lookup"><span data-stu-id="2a51f-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2a51f-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2a51f-104">Methods</span></span>  
  
|<span data-ttu-id="2a51f-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2a51f-105">Method</span></span>|<span data-ttu-id="2a51f-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2a51f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2a51f-107">Метод StrongNameGetPublicKeyEx</span><span class="sxs-lookup"><span data-stu-id="2a51f-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="2a51f-108">Получает открытый ключ из пары открытого и закрытого ключей и задает алгоритм хеширования и алгоритм подписи.</span><span class="sxs-lookup"><span data-stu-id="2a51f-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="2a51f-109">Метод StrongNameSignatureVerificationEx2</span><span class="sxs-lookup"><span data-stu-id="2a51f-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="2a51f-110">Проверяет подпись сборки со строгим именем и обеспечивает сопоставление ключа ECMA с реальным ключом.</span><span class="sxs-lookup"><span data-stu-id="2a51f-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a51f-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="2a51f-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a51f-112">Требования</span><span class="sxs-lookup"><span data-stu-id="2a51f-112">Requirements</span></span>  
 <span data-ttu-id="2a51f-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a51f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a51f-114">**Заголовок:** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="2a51f-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2a51f-115">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2a51f-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a51f-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a51f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
