---
title: Интерфейс IInstallReferenceEnum
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum
helpviewer_keywords:
- IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2aed89008dd2fa86b38f243c8e7cca1bdda901e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54497778"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="ad0a5-102">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="ad0a5-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="ad0a5-103">Представляет перечислитель для упоминаемой сборок, установленных в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="ad0a5-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad0a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad0a5-104">Syntax</span></span>  
  
```  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ad0a5-105">Методы</span><span class="sxs-lookup"><span data-stu-id="ad0a5-105">Methods</span></span>  
  
|<span data-ttu-id="ad0a5-106">Метод</span><span class="sxs-lookup"><span data-stu-id="ad0a5-106">Method</span></span>|<span data-ttu-id="ad0a5-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="ad0a5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad0a5-108">Метод GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="ad0a5-108">GetNextInstallReferenceItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="ad0a5-109">Получает указатель на следующий `IInstallReferenceItem` , содержащихся в данном `IInstallReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="ad0a5-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ad0a5-110">Требования</span><span class="sxs-lookup"><span data-stu-id="ad0a5-110">Requirements</span></span>  
 <span data-ttu-id="ad0a5-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad0a5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad0a5-112">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ad0a5-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ad0a5-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad0a5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad0a5-114">См. также</span><span class="sxs-lookup"><span data-stu-id="ad0a5-114">See also</span></span>
- [<span data-ttu-id="ad0a5-115">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="ad0a5-115">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="ad0a5-116">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="ad0a5-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
