---
title: Интерфейс ICLRHostProtectionManager
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d4cb310215967a79e43e43319e107b6c42551e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557439"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="5a568-102">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="5a568-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="5a568-103">Ведущее приложение может блокировать определенные управляемые классы, методы, свойства и поля запуска частично доверенного кода.</span><span class="sxs-lookup"><span data-stu-id="5a568-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a568-104">Методы</span><span class="sxs-lookup"><span data-stu-id="5a568-104">Methods</span></span>  
  
|<span data-ttu-id="5a568-105">Метод</span><span class="sxs-lookup"><span data-stu-id="5a568-105">Method</span></span>|<span data-ttu-id="5a568-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="5a568-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a568-107">Метод SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="5a568-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="5a568-108">Гарантирует, что никогда не будет возникать некоторых редких условиях гонки, которые могут вызвать неустранимые ошибки времени выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="5a568-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="5a568-109">Метод SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="5a568-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="5a568-110">Задает категории управляемых типов и членов, которые должны блокироваться в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="5a568-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a568-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5a568-111">Requirements</span></span>  
 <span data-ttu-id="5a568-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a568-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a568-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5a568-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a568-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a568-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a568-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a568-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a568-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5a568-116">See also</span></span>
- [<span data-ttu-id="5a568-117">Перечисление EApiCategories</span><span class="sxs-lookup"><span data-stu-id="5a568-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="5a568-118">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="5a568-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
