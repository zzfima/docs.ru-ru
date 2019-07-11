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
ms.openlocfilehash: 84ccbd7a8be7d90a541fb2d54baa3d7f66d3d31e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746114"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="4805c-102">Метод ICeeGen::GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="4805c-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="4805c-103">Получает блок разделе базы кода.</span><span class="sxs-lookup"><span data-stu-id="4805c-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="4805c-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="4805c-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4805c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4805c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="4805c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4805c-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="4805c-107">[in] Раздел, из которого извлекается блок кода.</span><span class="sxs-lookup"><span data-stu-id="4805c-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="4805c-108">[in] Длина блока, который требуется получить.</span><span class="sxs-lookup"><span data-stu-id="4805c-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="4805c-109">[in] Байт, относительно начала данного раздела, с которой необходимо выровнять первого байта блока.</span><span class="sxs-lookup"><span data-stu-id="4805c-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="4805c-110">Это положение блока в разделе.</span><span class="sxs-lookup"><span data-stu-id="4805c-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="4805c-111">[out] Указатель на расположение, которое получает адрес извлеченных блока.</span><span class="sxs-lookup"><span data-stu-id="4805c-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4805c-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="4805c-112">Remarks</span></span>  
 <span data-ttu-id="4805c-113">Вызовите `GetSectionBlock` только при наличии особых требований к разделам, которые не обрабатываются другими способами.</span><span class="sxs-lookup"><span data-stu-id="4805c-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4805c-114">Требования</span><span class="sxs-lookup"><span data-stu-id="4805c-114">Requirements</span></span>  
 <span data-ttu-id="4805c-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4805c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4805c-116">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4805c-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4805c-117">**Библиотека:** Используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4805c-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4805c-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4805c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4805c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4805c-119">See also</span></span>

- [<span data-ttu-id="4805c-120">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="4805c-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
