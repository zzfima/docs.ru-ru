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
ms.openlocfilehash: 6338034d6714e8770e06ff61994fdf4433eb1684
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781791"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="ff5a5-102">Перечисление CorLocalRefPreservation</span><span class="sxs-lookup"><span data-stu-id="ff5a5-102">CorLocalRefPreservation Enumeration</span></span>
<span data-ttu-id="ff5a5-103">Содержит значения флага для обработки локальных ссылок.</span><span class="sxs-lookup"><span data-stu-id="ff5a5-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff5a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff5a5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="ff5a5-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ff5a5-105">Members</span></span>  
  
|<span data-ttu-id="ff5a5-106">Член</span><span class="sxs-lookup"><span data-stu-id="ff5a5-106">Member</span></span>|<span data-ttu-id="ff5a5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ff5a5-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="ff5a5-108">Сохранить не локальные ссылки.</span><span class="sxs-lookup"><span data-stu-id="ff5a5-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="ff5a5-109">Сохраняет ссылки на локальный тип.</span><span class="sxs-lookup"><span data-stu-id="ff5a5-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="ff5a5-110">Сохраняет ссылки на локальный член.</span><span class="sxs-lookup"><span data-stu-id="ff5a5-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ff5a5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ff5a5-111">Requirements</span></span>  
 <span data-ttu-id="ff5a5-112">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff5a5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff5a5-113">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ff5a5-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ff5a5-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff5a5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff5a5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ff5a5-115">See also</span></span>

- [<span data-ttu-id="ff5a5-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="ff5a5-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
