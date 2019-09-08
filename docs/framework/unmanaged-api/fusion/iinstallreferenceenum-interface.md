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
ms.openlocfilehash: 0d29b9e2a9b9022f682065816a62734d6c5b2d62
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796405"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="4a97e-102">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="4a97e-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="4a97e-103">Представляет перечислитель для сборок, на которые имеются ссылки, установленных в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="4a97e-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a97e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a97e-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4a97e-105">Методы</span><span class="sxs-lookup"><span data-stu-id="4a97e-105">Methods</span></span>  
  
|<span data-ttu-id="4a97e-106">Метод</span><span class="sxs-lookup"><span data-stu-id="4a97e-106">Method</span></span>|<span data-ttu-id="4a97e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4a97e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4a97e-108">Метод GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="4a97e-108">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="4a97e-109">Возвращает указатель на следующий `IInstallReferenceItem` объект, содержащийся в этом. `IInstallReferenceEnum`</span><span class="sxs-lookup"><span data-stu-id="4a97e-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a97e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="4a97e-110">Requirements</span></span>  
 <span data-ttu-id="4a97e-111">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a97e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a97e-112">**Заголовок.** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="4a97e-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4a97e-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a97e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a97e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4a97e-114">See also</span></span>

- [<span data-ttu-id="4a97e-115">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="4a97e-115">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="4a97e-116">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="4a97e-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
