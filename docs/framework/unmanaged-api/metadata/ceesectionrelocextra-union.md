---
title: "Объединение CeeSectionRelocExtra"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CeeSectionRelocExtra Union
api_location: mscoree.dll
api_type: COM
f1_keywords: CeeSectionRelocExtra
helpviewer_keywords: CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c5b584ced996b31be6656082af3f64a19b1f223c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="f71ee-102">Объединение CeeSectionRelocExtra</span><span class="sxs-lookup"><span data-stu-id="f71ee-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="f71ee-103">Представляет смещение адреса, используемый [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) интерфейс для перемещения раздела.</span><span class="sxs-lookup"><span data-stu-id="f71ee-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f71ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f71ee-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="f71ee-105">Члены</span><span class="sxs-lookup"><span data-stu-id="f71ee-105">Members</span></span>  
  
|<span data-ttu-id="f71ee-106">Член</span><span class="sxs-lookup"><span data-stu-id="f71ee-106">Member</span></span>|<span data-ttu-id="f71ee-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f71ee-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="f71ee-108">Коррекция верхнего адреса для раздела.</span><span class="sxs-lookup"><span data-stu-id="f71ee-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f71ee-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f71ee-109">Requirements</span></span>  
 <span data-ttu-id="f71ee-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f71ee-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f71ee-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f71ee-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f71ee-112">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f71ee-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f71ee-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f71ee-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f71ee-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f71ee-114">See Also</span></span>  
 [<span data-ttu-id="f71ee-115">Объединения метаданных</span><span class="sxs-lookup"><span data-stu-id="f71ee-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
