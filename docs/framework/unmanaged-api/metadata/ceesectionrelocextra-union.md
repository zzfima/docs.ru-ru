---
title: Объединение CeeSectionRelocExtra
ms.date: 03/30/2017
api_name:
- CeeSectionRelocExtra Union
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocExtra
helpviewer_keywords:
- CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d6a5673c2aaf287131274b0c590f00a69c64fed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517153"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="77852-102">Объединение CeeSectionRelocExtra</span><span class="sxs-lookup"><span data-stu-id="77852-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="77852-103">Представляет смещение адреса, используемые [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) интерфейс для перемещения раздела.</span><span class="sxs-lookup"><span data-stu-id="77852-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77852-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="77852-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="77852-105">Участники</span><span class="sxs-lookup"><span data-stu-id="77852-105">Members</span></span>  
  
|<span data-ttu-id="77852-106">Член</span><span class="sxs-lookup"><span data-stu-id="77852-106">Member</span></span>|<span data-ttu-id="77852-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="77852-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="77852-108">Коррекция верхнего адреса для раздела.</span><span class="sxs-lookup"><span data-stu-id="77852-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77852-109">Требования</span><span class="sxs-lookup"><span data-stu-id="77852-109">Requirements</span></span>  
 <span data-ttu-id="77852-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77852-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77852-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="77852-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77852-112">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="77852-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="77852-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77852-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77852-114">См. также</span><span class="sxs-lookup"><span data-stu-id="77852-114">See also</span></span>
- [<span data-ttu-id="77852-115">Объединения метаданных</span><span class="sxs-lookup"><span data-stu-id="77852-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
