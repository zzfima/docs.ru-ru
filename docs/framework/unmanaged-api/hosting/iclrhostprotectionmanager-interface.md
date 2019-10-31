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
ms.openlocfilehash: 0487a87420c888cf5466f54c28c2d89623260add
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141046"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="c965b-102">Интерфейс ICLRHostProtectionManager</span><span class="sxs-lookup"><span data-stu-id="c965b-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="c965b-103">Позволяет узлу блокировать выполнение конкретных управляемых классов, методов, свойств и полей в частично доверяемом коде.</span><span class="sxs-lookup"><span data-stu-id="c965b-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c965b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c965b-104">Methods</span></span>  
  
|<span data-ttu-id="c965b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c965b-105">Method</span></span>|<span data-ttu-id="c965b-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c965b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c965b-107">Метод SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="c965b-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="c965b-108">Гарантирует, что некоторые редкие состояния гонки, которые могут вызвать неустранимые ошибки среды CLR, никогда не будут возникать.</span><span class="sxs-lookup"><span data-stu-id="c965b-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="c965b-109">Метод SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="c965b-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="c965b-110">Указывает категории управляемых типов и членов, выполнение которых должно быть заблокировано в частично доверенном коде.</span><span class="sxs-lookup"><span data-stu-id="c965b-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c965b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c965b-111">Requirements</span></span>  
 <span data-ttu-id="c965b-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c965b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c965b-113">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c965b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c965b-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c965b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c965b-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c965b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c965b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="c965b-116">See also</span></span>

- [<span data-ttu-id="c965b-117">Перечисление EApiCategories</span><span class="sxs-lookup"><span data-stu-id="c965b-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="c965b-118">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="c965b-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
