---
title: "Интерфейс IApartmentCallback"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IApartmentCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: IApartmentCallback
helpviewer_keywords: IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d2f2ea73da2273ff6f0abb725ec3e3fb8ca79ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="94791-102">Интерфейс IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="94791-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="94791-103">Предоставляет методы для осуществления обратных вызовов в подразделении.</span><span class="sxs-lookup"><span data-stu-id="94791-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="94791-104">*Подразделения* — это логический контейнер, в рамках процесса для объектов, которые совместно используют те же требования доступа потока.</span><span class="sxs-lookup"><span data-stu-id="94791-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="94791-105">Методы</span><span class="sxs-lookup"><span data-stu-id="94791-105">Methods</span></span>  
  
|<span data-ttu-id="94791-106">Метод</span><span class="sxs-lookup"><span data-stu-id="94791-106">Method</span></span>|<span data-ttu-id="94791-107">Описание</span><span class="sxs-lookup"><span data-stu-id="94791-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="94791-108">DoCallback-метод</span><span class="sxs-lookup"><span data-stu-id="94791-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="94791-109">Выполняет заданную функцию в подразделении.</span><span class="sxs-lookup"><span data-stu-id="94791-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="94791-110">Требования</span><span class="sxs-lookup"><span data-stu-id="94791-110">Requirements</span></span>  
 <span data-ttu-id="94791-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94791-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94791-112">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="94791-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="94791-113">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="94791-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94791-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94791-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94791-115">См. также</span><span class="sxs-lookup"><span data-stu-id="94791-115">See Also</span></span>  
 [<span data-ttu-id="94791-116">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="94791-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
