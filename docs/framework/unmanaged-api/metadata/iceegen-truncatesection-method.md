---
title: Метод ICeeGen::TruncateSection
ms.date: 03/30/2017
api_name:
- ICeeGen.TruncateSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type:
- apiref
ms.openlocfilehash: 87a70587027f283ef5976089b3f2daf1204e68ec
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426130"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="9e3e6-102">Метод ICeeGen::TruncateSection</span><span class="sxs-lookup"><span data-stu-id="9e3e6-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="9e3e6-103">Truncates the specified code section by the specified length.</span><span class="sxs-lookup"><span data-stu-id="9e3e6-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="9e3e6-104">This method is obsolete and should not be used.</span><span class="sxs-lookup"><span data-stu-id="9e3e6-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e3e6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e3e6-105">Syntax</span></span>  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e3e6-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="9e3e6-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="9e3e6-107">[in] The section to truncate.</span><span class="sxs-lookup"><span data-stu-id="9e3e6-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="9e3e6-108">[in] The length, in bytes, by which to truncate the section.</span><span class="sxs-lookup"><span data-stu-id="9e3e6-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e3e6-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="9e3e6-109">Remarks</span></span>  
 <span data-ttu-id="9e3e6-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span><span class="sxs-lookup"><span data-stu-id="9e3e6-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e3e6-111">Требования</span><span class="sxs-lookup"><span data-stu-id="9e3e6-111">Requirements</span></span>  
 <span data-ttu-id="9e3e6-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e3e6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e3e6-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9e3e6-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9e3e6-114">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9e3e6-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9e3e6-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e3e6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e3e6-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9e3e6-116">See also</span></span>

- [<span data-ttu-id="9e3e6-117">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="9e3e6-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
