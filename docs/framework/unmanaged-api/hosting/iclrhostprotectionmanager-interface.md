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
ms.openlocfilehash: fd096344c987d8901f0baab86e370abbb03528e5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944676"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="c62ea-102">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="c62ea-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="c62ea-103">Ведущее приложение может блокировать определенные управляемые классы, методы, свойства и поля запуска частично доверенного кода.</span><span class="sxs-lookup"><span data-stu-id="c62ea-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c62ea-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c62ea-104">Methods</span></span>  
  
|<span data-ttu-id="c62ea-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c62ea-105">Method</span></span>|<span data-ttu-id="c62ea-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c62ea-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c62ea-107">Метод SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="c62ea-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="c62ea-108">Гарантирует, что никогда не будет возникать некоторых редких условиях гонки, которые могут вызвать неустранимые ошибки времени выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="c62ea-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="c62ea-109">Метод SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="c62ea-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="c62ea-110">Задает категории управляемых типов и членов, которые должны блокироваться в частично доверенным кодом.</span><span class="sxs-lookup"><span data-stu-id="c62ea-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c62ea-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c62ea-111">Requirements</span></span>  
 <span data-ttu-id="c62ea-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c62ea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c62ea-113">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c62ea-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c62ea-114">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c62ea-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c62ea-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c62ea-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c62ea-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c62ea-116">See also</span></span>

- [<span data-ttu-id="c62ea-117">Перечисление EApiCategories</span><span class="sxs-lookup"><span data-stu-id="c62ea-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="c62ea-118">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="c62ea-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
