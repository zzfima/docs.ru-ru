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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ee808ba403a513b897134420b45ebe8cd3537571
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="78589-102">Перечисление CorLocalRefPreservation</span><span class="sxs-lookup"><span data-stu-id="78589-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="78589-103">Содержит значения флага для обработки локальных ссылок.</span><span class="sxs-lookup"><span data-stu-id="78589-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78589-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="78589-104">Syntax</span></span>  
  
```  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="78589-105">Участники</span><span class="sxs-lookup"><span data-stu-id="78589-105">Members</span></span>  
  
|<span data-ttu-id="78589-106">Член</span><span class="sxs-lookup"><span data-stu-id="78589-106">Member</span></span>|<span data-ttu-id="78589-107">Описание</span><span class="sxs-lookup"><span data-stu-id="78589-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="78589-108">Сохранить нет локальных ссылок.</span><span class="sxs-lookup"><span data-stu-id="78589-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="78589-109">Сохраняет ссылки на локальный тип.</span><span class="sxs-lookup"><span data-stu-id="78589-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="78589-110">Сохраняет ссылки на локальный член.</span><span class="sxs-lookup"><span data-stu-id="78589-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="78589-111">Требования</span><span class="sxs-lookup"><span data-stu-id="78589-111">Requirements</span></span>  
 <span data-ttu-id="78589-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78589-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78589-113">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="78589-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="78589-114">**Версии платформы .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78589-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78589-115">См. также</span><span class="sxs-lookup"><span data-stu-id="78589-115">See Also</span></span>  
 [<span data-ttu-id="78589-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="78589-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
