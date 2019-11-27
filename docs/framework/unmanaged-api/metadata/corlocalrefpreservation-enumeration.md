---
title: Перечисление CorLocalRefPreservation
ms.date: 03/30/2017
api_name:
- CorLocalRefPreservation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLocalRefPreservation
helpviewer_keywords:
- CorLocalRefPreservation enumeration [.NET Framework metadata]
ms.assetid: 44757163-1228-4213-a4c4-d4de503cc75d
topic_type:
- apiref
ms.openlocfilehash: 706ea37101f9f961e92d8cef2cf508c1dd0d56c1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450241"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="ddf3c-102">Перечисление CorLocalRefPreservation</span><span class="sxs-lookup"><span data-stu-id="ddf3c-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="ddf3c-103">Содержит значения флага для обработки локальных ссылок.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddf3c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ddf3c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="ddf3c-105">Члены</span><span class="sxs-lookup"><span data-stu-id="ddf3c-105">Members</span></span>  
  
|<span data-ttu-id="ddf3c-106">Член</span><span class="sxs-lookup"><span data-stu-id="ddf3c-106">Member</span></span>|<span data-ttu-id="ddf3c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ddf3c-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="ddf3c-108">Не сохранять локальные ссылки.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="ddf3c-109">Сохранение ссылок на локальные типы.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="ddf3c-110">Сохранение ссылок на локальные члены.</span><span class="sxs-lookup"><span data-stu-id="ddf3c-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ddf3c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ddf3c-111">Requirements</span></span>  
 <span data-ttu-id="ddf3c-112">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddf3c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddf3c-113">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="ddf3c-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ddf3c-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddf3c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddf3c-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="ddf3c-115">See also</span></span>

- [<span data-ttu-id="ddf3c-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="ddf3c-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
