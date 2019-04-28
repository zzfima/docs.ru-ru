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
ms.openlocfilehash: 35faeb69e864a428dc40394ad89a7d50b95bbcab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757668"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="eb9b6-102">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="eb9b6-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="eb9b6-103">Представляет перечислитель для упоминаемой сборок, установленных в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="eb9b6-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb9b6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb9b6-104">Syntax</span></span>  
  
```  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="eb9b6-105">Методы</span><span class="sxs-lookup"><span data-stu-id="eb9b6-105">Methods</span></span>  
  
|<span data-ttu-id="eb9b6-106">Метод</span><span class="sxs-lookup"><span data-stu-id="eb9b6-106">Method</span></span>|<span data-ttu-id="eb9b6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="eb9b6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb9b6-108">Метод GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="eb9b6-108">GetNextInstallReferenceItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="eb9b6-109">Получает указатель на следующий `IInstallReferenceItem` , содержащихся в данном `IInstallReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="eb9b6-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eb9b6-110">Требования</span><span class="sxs-lookup"><span data-stu-id="eb9b6-110">Requirements</span></span>  
 <span data-ttu-id="eb9b6-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb9b6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb9b6-112">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="eb9b6-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="eb9b6-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb9b6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb9b6-114">См. также</span><span class="sxs-lookup"><span data-stu-id="eb9b6-114">See also</span></span>

- [<span data-ttu-id="eb9b6-115">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="eb9b6-115">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="eb9b6-116">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="eb9b6-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
