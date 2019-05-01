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
ms.openlocfilehash: 8a78a4b82d0b2064c90c938a8614b0c7594f7856
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043294"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="3bdd9-102">Объединение CeeSectionRelocExtra</span><span class="sxs-lookup"><span data-stu-id="3bdd9-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="3bdd9-103">Представляет смещение адреса, используемые [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) интерфейс для перемещения раздела.</span><span class="sxs-lookup"><span data-stu-id="3bdd9-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bdd9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3bdd9-104">Syntax</span></span>  
  
```  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="3bdd9-105">Участники</span><span class="sxs-lookup"><span data-stu-id="3bdd9-105">Members</span></span>  
  
|<span data-ttu-id="3bdd9-106">Член</span><span class="sxs-lookup"><span data-stu-id="3bdd9-106">Member</span></span>|<span data-ttu-id="3bdd9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3bdd9-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="3bdd9-108">Коррекция верхнего адреса для раздела.</span><span class="sxs-lookup"><span data-stu-id="3bdd9-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3bdd9-109">Требования</span><span class="sxs-lookup"><span data-stu-id="3bdd9-109">Requirements</span></span>  
 <span data-ttu-id="3bdd9-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bdd9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bdd9-111">**Заголовок.** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3bdd9-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3bdd9-112">**Библиотека:** Включена как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3bdd9-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3bdd9-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bdd9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bdd9-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3bdd9-114">See also</span></span>

- [<span data-ttu-id="3bdd9-115">Объединения метаданных</span><span class="sxs-lookup"><span data-stu-id="3bdd9-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
