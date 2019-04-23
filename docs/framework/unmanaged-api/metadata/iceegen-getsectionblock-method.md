---
title: Метод ICeeGen::GetSectionBlock
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e600f29a9036bb28031bd7854bc8cbb34c4566a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200653"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="e8995-102">Метод ICeeGen::GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="e8995-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="e8995-103">Получает блок разделе базы кода.</span><span class="sxs-lookup"><span data-stu-id="e8995-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="e8995-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="e8995-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8995-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8995-105">Syntax</span></span>  
  
```  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="e8995-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e8995-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="e8995-107">[in] Раздел, из которого извлекается блок кода.</span><span class="sxs-lookup"><span data-stu-id="e8995-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="e8995-108">[in] Длина блока, который требуется получить.</span><span class="sxs-lookup"><span data-stu-id="e8995-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="e8995-109">[in] Байт, относительно начала данного раздела, с которой необходимо выровнять первого байта блока.</span><span class="sxs-lookup"><span data-stu-id="e8995-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="e8995-110">Это положение блока в разделе.</span><span class="sxs-lookup"><span data-stu-id="e8995-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="e8995-111">[out] Указатель на расположение, которое получает адрес извлеченных блока.</span><span class="sxs-lookup"><span data-stu-id="e8995-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8995-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="e8995-112">Remarks</span></span>  
 <span data-ttu-id="e8995-113">Вызовите `GetSectionBlock` только при наличии особых требований к разделам, которые не обрабатываются другими способами.</span><span class="sxs-lookup"><span data-stu-id="e8995-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8995-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e8995-114">Requirements</span></span>  
 <span data-ttu-id="e8995-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8995-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8995-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e8995-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e8995-117">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e8995-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e8995-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8995-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8995-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e8995-119">See also</span></span>

- [<span data-ttu-id="e8995-120">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="e8995-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
