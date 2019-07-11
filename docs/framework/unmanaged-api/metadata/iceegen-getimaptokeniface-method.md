---
title: Метод ICeeGen::GetIMapTokenIface
ms.date: 03/30/2017
api_name:
- ICeeGen.GetIMapTokenIface
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIMapTokenIface
helpviewer_keywords:
- GetIMapTokenIface method [.NET Framework metadata]
- ICeeGen::GetIMapTokenIface method [.NET Framework metadata]
ms.assetid: 847a5531-c37d-49cd-8844-9e54b5d86cf7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b42c7ed5614f5f436559ce4af462ff16896a89c0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746153"
---
# <a name="iceegengetimaptokeniface-method"></a><span data-ttu-id="64a12-102">Метод ICeeGen::GetIMapTokenIface</span><span class="sxs-lookup"><span data-stu-id="64a12-102">ICeeGen::GetIMapTokenIface Method</span></span>
<span data-ttu-id="64a12-103">Получает интерфейс, который ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="64a12-103">Gets the interface referenced by the specified token.</span></span>  
  
 <span data-ttu-id="64a12-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="64a12-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64a12-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64a12-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIMapTokenIface (  
    [in, out] IUnknown   **pIMapToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64a12-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="64a12-106">Parameters</span></span>  
 `pIMapToken`  
 <span data-ttu-id="64a12-107">[in, out] Токен метаданных для интерфейса должны быть возвращены.</span><span class="sxs-lookup"><span data-stu-id="64a12-107">[in, out] The metadata token for the interface to be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64a12-108">Требования</span><span class="sxs-lookup"><span data-stu-id="64a12-108">Requirements</span></span>  
 <span data-ttu-id="64a12-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64a12-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64a12-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="64a12-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64a12-111">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="64a12-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="64a12-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64a12-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a12-113">См. также</span><span class="sxs-lookup"><span data-stu-id="64a12-113">See also</span></span>

- [<span data-ttu-id="64a12-114">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="64a12-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
