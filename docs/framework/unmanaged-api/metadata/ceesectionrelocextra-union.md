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
ms.openlocfilehash: 7becace679b62a635d8231c3d42213f247f44190
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444175"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="b9a62-102">Объединение CeeSectionRelocExtra</span><span class="sxs-lookup"><span data-stu-id="b9a62-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="b9a62-103">Представляет смещение адреса, используемое интерфейсом [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) для перемещения раздела.</span><span class="sxs-lookup"><span data-stu-id="b9a62-103">Represents an address offset that is used by the [ICeeGen](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9a62-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9a62-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="b9a62-105">Члены</span><span class="sxs-lookup"><span data-stu-id="b9a62-105">Members</span></span>  
  
|<span data-ttu-id="b9a62-106">Член</span><span class="sxs-lookup"><span data-stu-id="b9a62-106">Member</span></span>|<span data-ttu-id="b9a62-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b9a62-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="b9a62-108">Корректировка верхнего адреса для раздела.</span><span class="sxs-lookup"><span data-stu-id="b9a62-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b9a62-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b9a62-109">Requirements</span></span>  
 <span data-ttu-id="b9a62-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9a62-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9a62-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="b9a62-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9a62-112">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b9a62-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9a62-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9a62-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9a62-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="b9a62-114">See also</span></span>

- [<span data-ttu-id="b9a62-115">Объединения метаданных</span><span class="sxs-lookup"><span data-stu-id="b9a62-115">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
