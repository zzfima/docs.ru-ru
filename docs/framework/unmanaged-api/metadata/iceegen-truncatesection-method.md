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
ms.openlocfilehash: a7b21179faec0b6f37b8084c9ee8a0bfd327193e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443568"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="710cc-102">Метод ICeeGen::TruncateSection</span><span class="sxs-lookup"><span data-stu-id="710cc-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="710cc-103">Усекает заданный раздел кода указанной длины.</span><span class="sxs-lookup"><span data-stu-id="710cc-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="710cc-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="710cc-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="710cc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="710cc-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="710cc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="710cc-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="710cc-107">[in] Раздел для усечения.</span><span class="sxs-lookup"><span data-stu-id="710cc-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="710cc-108">[in] Длина в байтах, с помощью которого для усечения в разделе.</span><span class="sxs-lookup"><span data-stu-id="710cc-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="710cc-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="710cc-109">Remarks</span></span>  
 <span data-ttu-id="710cc-110">Вызовите `TruncateSection` только при наличии особых требований к разделам, не обрабатываются другими способами.</span><span class="sxs-lookup"><span data-stu-id="710cc-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="710cc-111">Требования</span><span class="sxs-lookup"><span data-stu-id="710cc-111">Requirements</span></span>  
 <span data-ttu-id="710cc-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="710cc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="710cc-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="710cc-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="710cc-114">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="710cc-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="710cc-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="710cc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="710cc-116">См. также</span><span class="sxs-lookup"><span data-stu-id="710cc-116">See Also</span></span>  
 [<span data-ttu-id="710cc-117">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="710cc-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
