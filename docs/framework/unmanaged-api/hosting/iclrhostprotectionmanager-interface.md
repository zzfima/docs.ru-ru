---
title: "Интерфейс ICLRHostProtectionManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostProtectionManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostProtectionManager
helpviewer_keywords: ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c88279eb26b819adaaaf86dcf59105c6ac728017
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="29617-102">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="29617-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="29617-103">Ведущее приложение может блокировать определенные управляемые классы, методы, свойства и поля при выполнении в частично доверенный код.</span><span class="sxs-lookup"><span data-stu-id="29617-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="29617-104">Методы</span><span class="sxs-lookup"><span data-stu-id="29617-104">Methods</span></span>  
  
|<span data-ttu-id="29617-105">Метод</span><span class="sxs-lookup"><span data-stu-id="29617-105">Method</span></span>|<span data-ttu-id="29617-106">Описание</span><span class="sxs-lookup"><span data-stu-id="29617-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="29617-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="29617-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="29617-108">Обеспечивает гарантию, никогда не проявит себя некоторых редких условиях гонки, можно вызвать неустранимые ошибки времени выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="29617-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="29617-109">Setprotectedcategories-метод</span><span class="sxs-lookup"><span data-stu-id="29617-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="29617-110">Задает категории управляемых типов и членов, которые должны блокироваться в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="29617-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="29617-111">Требования</span><span class="sxs-lookup"><span data-stu-id="29617-111">Requirements</span></span>  
 <span data-ttu-id="29617-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29617-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29617-113">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="29617-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="29617-114">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="29617-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="29617-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29617-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29617-116">См. также</span><span class="sxs-lookup"><span data-stu-id="29617-116">See Also</span></span>  
 [<span data-ttu-id="29617-117">EApiCategories-перечисление</span><span class="sxs-lookup"><span data-stu-id="29617-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [<span data-ttu-id="29617-118">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="29617-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
