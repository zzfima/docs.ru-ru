---
title: Перечисление CorMethodSemanticsAttr
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f888c39160e52e550d07f58b9c5bcd11fd625658
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564085"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="8c032-102">Перечисление CorMethodSemanticsAttr</span><span class="sxs-lookup"><span data-stu-id="8c032-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="8c032-103">Содержит значения, описывающие связь между методом и соответствующим свойством или событием.</span><span class="sxs-lookup"><span data-stu-id="8c032-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c032-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c032-104">Syntax</span></span>  
  
```  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="8c032-105">Участники</span><span class="sxs-lookup"><span data-stu-id="8c032-105">Members</span></span>  
  
|<span data-ttu-id="8c032-106">Член</span><span class="sxs-lookup"><span data-stu-id="8c032-106">Member</span></span>|<span data-ttu-id="8c032-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="8c032-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="8c032-108">Указывает, что метод вызывается `set` метод доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="8c032-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="8c032-109">Указывает, что метод вызывается `get` метод доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="8c032-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="8c032-110">Указывает, что метод имеет отношение к свойство или событие, отличные от определенных здесь.</span><span class="sxs-lookup"><span data-stu-id="8c032-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="8c032-111">Указывает, что этот метод добавляет методы обработчика для события.</span><span class="sxs-lookup"><span data-stu-id="8c032-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="8c032-112">Указывает, что метод удаляет методы обработчика для события.</span><span class="sxs-lookup"><span data-stu-id="8c032-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="8c032-113">Указывает, что метод вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="8c032-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8c032-114">Требования</span><span class="sxs-lookup"><span data-stu-id="8c032-114">Requirements</span></span>  
 <span data-ttu-id="8c032-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c032-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c032-116">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="8c032-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8c032-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c032-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c032-118">См. также</span><span class="sxs-lookup"><span data-stu-id="8c032-118">See also</span></span>
- [<span data-ttu-id="8c032-119">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="8c032-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
