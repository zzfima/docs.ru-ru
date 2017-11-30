---
title: "Метод ICeeGen::GetSectionBlock"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetSectionBlock
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4732eef9a47f9ea1e919bd9d855afbec18974454
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="b2c1a-102">Метод ICeeGen::GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="b2c1a-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="b2c1a-103">Получает блок базы кода раздела.</span><span class="sxs-lookup"><span data-stu-id="b2c1a-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="b2c1a-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="b2c1a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2c1a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2c1a-105">Syntax</span></span>  
  
```  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2c1a-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2c1a-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="b2c1a-107">[in] Раздел, из которого извлекается блок базу кода.</span><span class="sxs-lookup"><span data-stu-id="b2c1a-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="b2c1a-108">[in] Длина блока требуется получить.</span><span class="sxs-lookup"><span data-stu-id="b2c1a-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="b2c1a-109">[in] Байт, относительно начала данного раздела, с которой необходимо выровнять первый байт блока.</span><span class="sxs-lookup"><span data-stu-id="b2c1a-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="b2c1a-110">Это положение блока в разделе.</span><span class="sxs-lookup"><span data-stu-id="b2c1a-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="b2c1a-111">[out] Указатель на расположение, принимающая адрес полученные блока.</span><span class="sxs-lookup"><span data-stu-id="b2c1a-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2c1a-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2c1a-112">Remarks</span></span>  
 <span data-ttu-id="b2c1a-113">Вызовите `GetSectionBlock` только при наличии особых требований к разделам, не обрабатываются другими способами.</span><span class="sxs-lookup"><span data-stu-id="b2c1a-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2c1a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b2c1a-114">Requirements</span></span>  
 <span data-ttu-id="b2c1a-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2c1a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2c1a-116">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b2c1a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b2c1a-117">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b2c1a-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b2c1a-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2c1a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2c1a-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b2c1a-119">See Also</span></span>  
 [<span data-ttu-id="b2c1a-120">ICeeGen-интерфейс</span><span class="sxs-lookup"><span data-stu-id="b2c1a-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
