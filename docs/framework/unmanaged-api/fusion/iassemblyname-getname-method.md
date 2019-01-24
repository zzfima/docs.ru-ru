---
title: Метод IAssemblyName::GetName
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetName
helpviewer_keywords:
- GetName method, IAssemblyName interface [.NET Framework debugging]
- IAssemblyName::GetName method [.NET Framework fusion]
ms.assetid: 1dee9781-1cf3-48a9-a376-d18ea1f73280
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7859beae572f05863fb24f0257aae8b0ec16bbcf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640879"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="0a46d-102">Метод IAssemblyName::GetName</span><span class="sxs-lookup"><span data-stu-id="0a46d-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="0a46d-103">Получает простое и незашифрованное имя сборки, упоминаемой в этом [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="0a46d-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a46d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a46d-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a46d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a46d-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="0a46d-106">[in, out] Размер `pwzName` из расширенных символов, включая завершающий нуль-символ-символ.</span><span class="sxs-lookup"><span data-stu-id="0a46d-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="0a46d-107">[out] Буфер для хранения имени сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="0a46d-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a46d-108">Требования</span><span class="sxs-lookup"><span data-stu-id="0a46d-108">Requirements</span></span>  
 <span data-ttu-id="0a46d-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a46d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a46d-110">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="0a46d-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0a46d-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a46d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a46d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0a46d-112">See also</span></span>
- [<span data-ttu-id="0a46d-113">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="0a46d-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
