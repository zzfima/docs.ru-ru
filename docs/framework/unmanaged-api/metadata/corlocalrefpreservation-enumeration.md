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
ms.openlocfilehash: 845994b96445d8ec2a0e37affc5164b432894a91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045716"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="be20a-102">Перечисление CorLocalRefPreservation</span><span class="sxs-lookup"><span data-stu-id="be20a-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="be20a-103">Содержит значения флага для обработки локальных ссылок.</span><span class="sxs-lookup"><span data-stu-id="be20a-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be20a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="be20a-104">Syntax</span></span>  
  
```  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="be20a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="be20a-105">Members</span></span>  
  
|<span data-ttu-id="be20a-106">Член</span><span class="sxs-lookup"><span data-stu-id="be20a-106">Member</span></span>|<span data-ttu-id="be20a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="be20a-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="be20a-108">Сохранить не локальные ссылки.</span><span class="sxs-lookup"><span data-stu-id="be20a-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="be20a-109">Сохраняет ссылки на локальный тип.</span><span class="sxs-lookup"><span data-stu-id="be20a-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="be20a-110">Сохраняет ссылки на локальный член.</span><span class="sxs-lookup"><span data-stu-id="be20a-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be20a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="be20a-111">Requirements</span></span>  
 <span data-ttu-id="be20a-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be20a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be20a-113">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="be20a-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="be20a-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be20a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be20a-115">См. также</span><span class="sxs-lookup"><span data-stu-id="be20a-115">See also</span></span>

- [<span data-ttu-id="be20a-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="be20a-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
