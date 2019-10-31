---
title: Интерфейс IApartmentCallback
ms.date: 03/30/2017
api_name:
- IApartmentCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IApartmentCallback
helpviewer_keywords:
- IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type:
- apiref
ms.openlocfilehash: 4424509c16dd1d9f83db117ae7343fa03995297e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126912"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="d5b18-102">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="d5b18-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="d5b18-103">Предоставляет методы для выполнения обратных вызовов в апартаменте.</span><span class="sxs-lookup"><span data-stu-id="d5b18-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="d5b18-104">*Апартамент* — это логический контейнер в рамках процесса для объектов, имеющих одинаковые требования доступа к потокам.</span><span class="sxs-lookup"><span data-stu-id="d5b18-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d5b18-105">Методы</span><span class="sxs-lookup"><span data-stu-id="d5b18-105">Methods</span></span>  
  
|<span data-ttu-id="d5b18-106">Метод</span><span class="sxs-lookup"><span data-stu-id="d5b18-106">Method</span></span>|<span data-ttu-id="d5b18-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d5b18-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5b18-108">Метод DoCallback</span><span class="sxs-lookup"><span data-stu-id="d5b18-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="d5b18-109">Выполняет указанную функцию в апартаменте.</span><span class="sxs-lookup"><span data-stu-id="d5b18-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d5b18-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d5b18-110">Requirements</span></span>  
 <span data-ttu-id="d5b18-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5b18-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5b18-112">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d5b18-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5b18-113">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d5b18-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5b18-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5b18-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5b18-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d5b18-115">See also</span></span>

- [<span data-ttu-id="d5b18-116">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="d5b18-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
