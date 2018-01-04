---
title: "Интерфейс IInstallReferenceEnum"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IInstallReferenceEnum
api_location: fusion.dll
api_type: COM
f1_keywords: IInstallReferenceEnum
helpviewer_keywords: IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2f1a80d1d79fce952a7071abd5e435604824d00e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="a227e-102">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="a227e-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="a227e-103">Представляет перечислитель для сборок, установленные в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="a227e-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a227e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a227e-104">Syntax</span></span>  
  
```  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a227e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="a227e-105">Methods</span></span>  
  
|<span data-ttu-id="a227e-106">Метод</span><span class="sxs-lookup"><span data-stu-id="a227e-106">Method</span></span>|<span data-ttu-id="a227e-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="a227e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a227e-108">Метод GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="a227e-108">GetNextInstallReferenceItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="a227e-109">Возвращает указатель на следующий `IInstallReferenceItem` , содержащихся в данном `IInstallReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="a227e-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a227e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a227e-110">Requirements</span></span>  
 <span data-ttu-id="a227e-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a227e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a227e-112">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="a227e-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a227e-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a227e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a227e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a227e-114">See Also</span></span>  
 [<span data-ttu-id="a227e-115">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="a227e-115">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="a227e-116">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="a227e-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
