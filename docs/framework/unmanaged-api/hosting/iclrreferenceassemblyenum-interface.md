---
title: Интерфейс ICLRReferenceAssemblyEnum
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum
helpviewer_keywords:
- ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: 8adbf092-c3ba-4bee-b25b-0de6e43a4ce5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d66177c57acf2f41198ea37169756bc1629a2854
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433006"
---
# <a name="iclrreferenceassemblyenum-interface"></a><span data-ttu-id="249ac-102">Интерфейс ICLRReferenceAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="249ac-102">ICLRReferenceAssemblyEnum Interface</span></span>
<span data-ttu-id="249ac-103">Предоставляет методы, позволяющие основному приложению управлять набор сборок, на который указывает файл или поток, используя данные идентификации сборки, которые являются внутренними для общеязыковой среды выполнения (CLR), без необходимости создания или интерпретации этих данных.</span><span class="sxs-lookup"><span data-stu-id="249ac-103">Provides methods that allow the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the common language runtime (CLR), without needing to create or understand those identities.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="249ac-104">Методы</span><span class="sxs-lookup"><span data-stu-id="249ac-104">Methods</span></span>  
  
|<span data-ttu-id="249ac-105">Метод</span><span class="sxs-lookup"><span data-stu-id="249ac-105">Method</span></span>|<span data-ttu-id="249ac-106">Описание</span><span class="sxs-lookup"><span data-stu-id="249ac-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="249ac-107">Метод Get</span><span class="sxs-lookup"><span data-stu-id="249ac-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-get-method.md)|<span data-ttu-id="249ac-108">Возвращает удостоверение сборки с заданным индексом.</span><span class="sxs-lookup"><span data-stu-id="249ac-108">Gets the assembly identity at the supplied index.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="249ac-109">Требования</span><span class="sxs-lookup"><span data-stu-id="249ac-109">Requirements</span></span>  
 <span data-ttu-id="249ac-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="249ac-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="249ac-111">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="249ac-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="249ac-112">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="249ac-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="249ac-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="249ac-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="249ac-114">См. также</span><span class="sxs-lookup"><span data-stu-id="249ac-114">See Also</span></span>  
 [<span data-ttu-id="249ac-115">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="249ac-115">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="249ac-116">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="249ac-116">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="249ac-117">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="249ac-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
