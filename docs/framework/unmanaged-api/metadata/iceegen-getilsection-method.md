---
title: Метод ICeeGen::GetIlSection
ms.date: 03/30/2017
api_name:
- ICeeGen.GetIlSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIlSection
helpviewer_keywords:
- GetIlSection method [.NET Framework metadata]
- ICeeGen::GetIlSection method [.NET Framework metadata]
ms.assetid: 6f2db2ca-203f-4ac3-9530-208642ca385e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0e9d71edc580591b698ad039f8ee73e49c4e1d6a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489050"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="ccc20-102">Метод ICeeGen::GetIlSection</span><span class="sxs-lookup"><span data-stu-id="ccc20-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="ccc20-103">Получает раздел базовый код на промежуточном языке ссылается заданный дескриптор.</span><span class="sxs-lookup"><span data-stu-id="ccc20-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="ccc20-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="ccc20-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccc20-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ccc20-105">Syntax</span></span>  
  
```  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccc20-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ccc20-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="ccc20-107">[in] Дескриптор раздела, чтобы получить.</span><span class="sxs-lookup"><span data-stu-id="ccc20-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccc20-108">Требования</span><span class="sxs-lookup"><span data-stu-id="ccc20-108">Requirements</span></span>  
 <span data-ttu-id="ccc20-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccc20-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccc20-110">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ccc20-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ccc20-111">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ccc20-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ccc20-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccc20-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccc20-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ccc20-113">See also</span></span>
- [<span data-ttu-id="ccc20-114">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="ccc20-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
