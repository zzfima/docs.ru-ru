---
title: Метод ITypeName::GetAssemblyName
ms.date: 03/30/2017
api_name:
- ITypeName.GetAssemblyName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetAssemblyName
helpviewer_keywords:
- ITypeName::GetAssemblyName method [.NET Framework hosting]
- GetAssemblyName method [.NET Framework hosting]
ms.assetid: 97801d99-f5f1-4a30-882f-959827093fac
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2bf61de20d619fb2c89cee0175e256f596ba9f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668032"
---
# <a name="itypenamegetassemblyname-method"></a><span data-ttu-id="df2e1-102">Метод ITypeName::GetAssemblyName</span><span class="sxs-lookup"><span data-stu-id="df2e1-102">ITypeName::GetAssemblyName Method</span></span>
<span data-ttu-id="df2e1-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="df2e1-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df2e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df2e1-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyName (  
    [out, retval] BSTR* rgbszAssemblyNames  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="df2e1-105">Требования</span><span class="sxs-lookup"><span data-stu-id="df2e1-105">Requirements</span></span>  
 <span data-ttu-id="df2e1-106">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df2e1-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df2e1-107">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="df2e1-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df2e1-108">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="df2e1-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df2e1-109">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df2e1-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df2e1-110">См. также</span><span class="sxs-lookup"><span data-stu-id="df2e1-110">See also</span></span>
- [<span data-ttu-id="df2e1-111">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="df2e1-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
