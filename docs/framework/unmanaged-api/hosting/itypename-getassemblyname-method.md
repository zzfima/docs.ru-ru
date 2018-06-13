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
ms.openlocfilehash: 7b983491c3794603bea250e684ee097397aa004a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440178"
---
# <a name="itypenamegetassemblyname-method"></a><span data-ttu-id="8a40c-102">Метод ITypeName::GetAssemblyName</span><span class="sxs-lookup"><span data-stu-id="8a40c-102">ITypeName::GetAssemblyName Method</span></span>
<span data-ttu-id="8a40c-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="8a40c-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a40c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a40c-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyName (  
    [out, retval] BSTR* rgbszAssemblyNames  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="8a40c-105">Требования</span><span class="sxs-lookup"><span data-stu-id="8a40c-105">Requirements</span></span>  
 <span data-ttu-id="8a40c-106">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a40c-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a40c-107">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8a40c-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a40c-108">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a40c-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a40c-109">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a40c-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a40c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="8a40c-110">See Also</span></span>  
 [<span data-ttu-id="8a40c-111">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="8a40c-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
