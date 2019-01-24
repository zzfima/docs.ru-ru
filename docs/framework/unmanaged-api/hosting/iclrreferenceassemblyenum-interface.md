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
ms.openlocfilehash: e9f2f2a31247bae19d3cbb3dc667007c1cbc8acb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54499071"
---
# <a name="iclrreferenceassemblyenum-interface"></a><span data-ttu-id="f522a-102">Интерфейс ICLRReferenceAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="f522a-102">ICLRReferenceAssemblyEnum Interface</span></span>
<span data-ttu-id="f522a-103">Предоставляет методы, позволяющие основному приложению управлять набор сборок, на который указывает файл или поток, используя данные идентификации сборки, который является внутренним для общеязыковой среды выполнения (CLR), без необходимости создания или интерпретации этих данных.</span><span class="sxs-lookup"><span data-stu-id="f522a-103">Provides methods that allow the host to manipulate the set of assemblies referenced by a file or stream using assembly identity data that is internal to the common language runtime (CLR), without needing to create or understand those identities.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f522a-104">Методы</span><span class="sxs-lookup"><span data-stu-id="f522a-104">Methods</span></span>  
  
|<span data-ttu-id="f522a-105">Метод</span><span class="sxs-lookup"><span data-stu-id="f522a-105">Method</span></span>|<span data-ttu-id="f522a-106">Описание</span><span class="sxs-lookup"><span data-stu-id="f522a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f522a-107">Метод Get</span><span class="sxs-lookup"><span data-stu-id="f522a-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-get-method.md)|<span data-ttu-id="f522a-108">Получает идентификатор сборки с заданным индексом.</span><span class="sxs-lookup"><span data-stu-id="f522a-108">Gets the assembly identity at the supplied index.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f522a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f522a-109">Requirements</span></span>  
 <span data-ttu-id="f522a-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f522a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f522a-111">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f522a-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f522a-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f522a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f522a-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f522a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f522a-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f522a-114">See also</span></span>
- [<span data-ttu-id="f522a-115">Интерфейс ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="f522a-115">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="f522a-116">Интерфейс ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="f522a-116">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="f522a-117">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="f522a-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
