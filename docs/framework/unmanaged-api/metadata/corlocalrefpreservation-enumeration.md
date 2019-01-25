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
ms.openlocfilehash: e9ed3cdac726fbdbf9ee2b33f42565d8594bc36e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669683"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="f9651-102">Перечисление CorLocalRefPreservation</span><span class="sxs-lookup"><span data-stu-id="f9651-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="f9651-103">Содержит значения флага для обработки локальных ссылок.</span><span class="sxs-lookup"><span data-stu-id="f9651-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9651-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9651-104">Syntax</span></span>  
  
```  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="f9651-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f9651-105">Members</span></span>  
  
|<span data-ttu-id="f9651-106">Член</span><span class="sxs-lookup"><span data-stu-id="f9651-106">Member</span></span>|<span data-ttu-id="f9651-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f9651-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="f9651-108">Сохранить не локальные ссылки.</span><span class="sxs-lookup"><span data-stu-id="f9651-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="f9651-109">Сохраняет ссылки на локальный тип.</span><span class="sxs-lookup"><span data-stu-id="f9651-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="f9651-110">Сохраняет ссылки на локальный член.</span><span class="sxs-lookup"><span data-stu-id="f9651-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f9651-111">Требования</span><span class="sxs-lookup"><span data-stu-id="f9651-111">Requirements</span></span>  
 <span data-ttu-id="f9651-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9651-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9651-113">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="f9651-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f9651-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9651-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9651-115">См. также</span><span class="sxs-lookup"><span data-stu-id="f9651-115">See also</span></span>
- [<span data-ttu-id="f9651-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="f9651-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
