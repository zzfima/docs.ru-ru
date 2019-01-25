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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1ef6583587b960d74c83350b061be3c2e36fd4f9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722690"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="05538-102">Метод ICeeGen::TruncateSection</span><span class="sxs-lookup"><span data-stu-id="05538-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="05538-103">Усекает заданный раздел кода указанной длины.</span><span class="sxs-lookup"><span data-stu-id="05538-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="05538-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="05538-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05538-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05538-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="05538-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="05538-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="05538-107">[in] Раздел для усечения.</span><span class="sxs-lookup"><span data-stu-id="05538-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="05538-108">[in] Длина в байтах, по которому для усечения в разделе.</span><span class="sxs-lookup"><span data-stu-id="05538-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05538-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="05538-109">Remarks</span></span>  
 <span data-ttu-id="05538-110">Вызовите `TruncateSection` только при наличии особых требований к разделам, которые не обрабатываются другими способами.</span><span class="sxs-lookup"><span data-stu-id="05538-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05538-111">Требования</span><span class="sxs-lookup"><span data-stu-id="05538-111">Requirements</span></span>  
 <span data-ttu-id="05538-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05538-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05538-113">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="05538-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="05538-114">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="05538-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="05538-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05538-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05538-116">См. также</span><span class="sxs-lookup"><span data-stu-id="05538-116">See also</span></span>
- [<span data-ttu-id="05538-117">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="05538-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
