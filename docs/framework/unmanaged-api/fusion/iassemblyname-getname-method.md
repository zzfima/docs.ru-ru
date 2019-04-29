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
ms.openlocfilehash: 88a46ecadaf2b191e8321c5629bc77b0c67dfd3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697372"
---
# <a name="iassemblynamegetname-method"></a><span data-ttu-id="778e6-102">Метод IAssemblyName::GetName</span><span class="sxs-lookup"><span data-stu-id="778e6-102">IAssemblyName::GetName Method</span></span>
<span data-ttu-id="778e6-103">Получает простое и незашифрованное имя сборки, упоминаемой в этом [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) объекта.</span><span class="sxs-lookup"><span data-stu-id="778e6-103">Gets the simple, unencrypted name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="778e6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="778e6-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in, out] LPDWORD lpcwBuffer,  
    [out]     WCHAR *pwzName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="778e6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="778e6-105">Parameters</span></span>  
 `lpcwBuffer`  
 <span data-ttu-id="778e6-106">[in, out] Размер `pwzName` из расширенных символов, включая завершающий нуль-символ-символ.</span><span class="sxs-lookup"><span data-stu-id="778e6-106">[in, out] The size of `pwzName` in wide characters, including the null terminator character.</span></span>  
  
 `pwzName`  
 <span data-ttu-id="778e6-107">[out] Буфер для хранения имени сборки, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="778e6-107">[out] A buffer to hold the name of the referenced assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="778e6-108">Требования</span><span class="sxs-lookup"><span data-stu-id="778e6-108">Requirements</span></span>  
 <span data-ttu-id="778e6-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="778e6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="778e6-110">**Заголовок.** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="778e6-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="778e6-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="778e6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="778e6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="778e6-112">See also</span></span>

- [<span data-ttu-id="778e6-113">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="778e6-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
