---
title: "Метод ICeeGen::AddSectionReloc"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.AddSectionReloc
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a74f01e3904c6f3f472110288abbec42fa892fdc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="8f7d5-102">Метод ICeeGen::AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="8f7d5-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="8f7d5-103">Добавляет инструкцию .reloc в базу кода.</span><span class="sxs-lookup"><span data-stu-id="8f7d5-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="8f7d5-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="8f7d5-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f7d5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f7d5-105">Syntax</span></span>  
  
```  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f7d5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8f7d5-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="8f7d5-107">[in] Раздел кода в памяти, к которому необходимо добавить инструкцию .reloc.</span><span class="sxs-lookup"><span data-stu-id="8f7d5-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="8f7d5-108">[in] Смещение раздела.</span><span class="sxs-lookup"><span data-stu-id="8f7d5-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="8f7d5-109">[in] Раздел, к которому `offset` ссылается.</span><span class="sxs-lookup"><span data-stu-id="8f7d5-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="8f7d5-110">[in] Один из [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) значений, указывающих вид .reloc инструкции для добавления.</span><span class="sxs-lookup"><span data-stu-id="8f7d5-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f7d5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="8f7d5-111">Requirements</span></span>  
 <span data-ttu-id="8f7d5-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f7d5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f7d5-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8f7d5-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8f7d5-114">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8f7d5-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8f7d5-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f7d5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f7d5-116">См. также</span><span class="sxs-lookup"><span data-stu-id="8f7d5-116">See Also</span></span>  
 [<span data-ttu-id="8f7d5-117">ICeeGen-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8f7d5-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
