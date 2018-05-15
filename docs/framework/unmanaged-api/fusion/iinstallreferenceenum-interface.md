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
ms.openlocfilehash: cac9f9db0b7527a80671c825a4435e8ea2d135b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="d5961-102">Интерфейс IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="d5961-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="d5961-103">Представляет перечислитель для сборок, установленные в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="d5961-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5961-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5961-104">Syntax</span></span>  
  
```  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d5961-105">Методы</span><span class="sxs-lookup"><span data-stu-id="d5961-105">Methods</span></span>  
  
|<span data-ttu-id="d5961-106">Метод</span><span class="sxs-lookup"><span data-stu-id="d5961-106">Method</span></span>|<span data-ttu-id="d5961-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d5961-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d5961-108">Метод GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="d5961-108">GetNextInstallReferenceItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="d5961-109">Возвращает указатель на следующий `IInstallReferenceItem` , содержащихся в данном `IInstallReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="d5961-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d5961-110">Требования</span><span class="sxs-lookup"><span data-stu-id="d5961-110">Requirements</span></span>  
 <span data-ttu-id="d5961-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5961-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5961-112">**Заголовок:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d5961-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d5961-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5961-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5961-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d5961-114">See Also</span></span>  
 [<span data-ttu-id="d5961-115">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="d5961-115">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="d5961-116">Интерфейс IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="d5961-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
