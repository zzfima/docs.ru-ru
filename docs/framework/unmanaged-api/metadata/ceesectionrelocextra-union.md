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
ms.workload: dotnet
ms.openlocfilehash: 9591967dc70d54bd020414077fcc57b8007db9d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="b5d07-102">Объединение CeeSectionRelocExtra</span><span class="sxs-lookup"><span data-stu-id="b5d07-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="b5d07-103">Представляет смещение адреса, используемый [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) интерфейс для перемещения раздела.</span><span class="sxs-lookup"><span data-stu-id="b5d07-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5d07-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5d07-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="b5d07-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b5d07-105">Members</span></span>  
  
|<span data-ttu-id="b5d07-106">Член</span><span class="sxs-lookup"><span data-stu-id="b5d07-106">Member</span></span>|<span data-ttu-id="b5d07-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="b5d07-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="b5d07-108">Коррекция верхнего адреса для раздела.</span><span class="sxs-lookup"><span data-stu-id="b5d07-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b5d07-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b5d07-109">Requirements</span></span>  
 <span data-ttu-id="b5d07-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5d07-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5d07-111">**Заголовок:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b5d07-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5d07-112">**Библиотека:** включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b5d07-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b5d07-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5d07-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5d07-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b5d07-114">See Also</span></span>  
 [<span data-ttu-id="b5d07-115">Объединения метаданных</span><span class="sxs-lookup"><span data-stu-id="b5d07-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
