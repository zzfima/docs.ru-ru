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
ms.openlocfilehash: de89f20842ab505e40ee0e9795774a92a7d5f1a9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102671"
---
# <a name="itypenamegetassemblyname-method"></a><span data-ttu-id="34516-102">Метод ITypeName::GetAssemblyName</span><span class="sxs-lookup"><span data-stu-id="34516-102">ITypeName::GetAssemblyName Method</span></span>
<span data-ttu-id="34516-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="34516-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34516-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34516-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyName (  
    [out, retval] BSTR* rgbszAssemblyNames  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="34516-105">Требования</span><span class="sxs-lookup"><span data-stu-id="34516-105">Requirements</span></span>  
 <span data-ttu-id="34516-106">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34516-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34516-107">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="34516-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="34516-108">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="34516-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="34516-109">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34516-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34516-110">См. также</span><span class="sxs-lookup"><span data-stu-id="34516-110">See also</span></span>

- [<span data-ttu-id="34516-111">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="34516-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
