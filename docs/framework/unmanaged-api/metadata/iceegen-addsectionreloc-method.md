---
title: Метод ICeeGen::AddSectionReloc
ms.date: 03/30/2017
api_name:
- ICeeGen.AddSectionReloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c281d03c6e3774938cfa6e4b4b3a541738b38489
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444347"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="0cf09-102">Метод ICeeGen::AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="0cf09-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="0cf09-103">Добавляет инструкцию .reloc в базу кода.</span><span class="sxs-lookup"><span data-stu-id="0cf09-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="0cf09-104">Этот метод является устаревшим и не должны использоваться.</span><span class="sxs-lookup"><span data-stu-id="0cf09-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cf09-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0cf09-105">Syntax</span></span>  
  
```  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0cf09-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0cf09-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="0cf09-107">[in] Раздел кода в памяти, к которому необходимо добавить инструкцию .reloc.</span><span class="sxs-lookup"><span data-stu-id="0cf09-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="0cf09-108">[in] Смещение раздела.</span><span class="sxs-lookup"><span data-stu-id="0cf09-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="0cf09-109">[in] Раздел, к которому `offset` ссылается.</span><span class="sxs-lookup"><span data-stu-id="0cf09-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="0cf09-110">[in] Один из [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) значений, указывающих вид .reloc инструкции для добавления.</span><span class="sxs-lookup"><span data-stu-id="0cf09-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cf09-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0cf09-111">Requirements</span></span>  
 <span data-ttu-id="0cf09-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cf09-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cf09-113">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0cf09-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0cf09-114">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0cf09-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0cf09-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cf09-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cf09-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0cf09-116">See Also</span></span>  
 [<span data-ttu-id="0cf09-117">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="0cf09-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
