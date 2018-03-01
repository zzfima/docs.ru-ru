---
title: "Перечисление CorMethodSemanticsAttr"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 09e0c1397a94b75a812e6cbdc52e612a930edae9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="f31bd-102">Перечисление CorMethodSemanticsAttr</span><span class="sxs-lookup"><span data-stu-id="f31bd-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="f31bd-103">Содержит значения, описывающие связь между методом и соответствующим свойством или событием.</span><span class="sxs-lookup"><span data-stu-id="f31bd-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f31bd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f31bd-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="f31bd-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f31bd-105">Members</span></span>  
  
|<span data-ttu-id="f31bd-106">Член</span><span class="sxs-lookup"><span data-stu-id="f31bd-106">Member</span></span>|<span data-ttu-id="f31bd-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="f31bd-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="f31bd-108">Указывает, что метод является `set` метод доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="f31bd-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="f31bd-109">Указывает, что метод является `get` метод доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="f31bd-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="f31bd-110">Указывает, что метод имеет связь с свойство или событие, отличные от определенных здесь.</span><span class="sxs-lookup"><span data-stu-id="f31bd-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="f31bd-111">Указывает, что метод добавляет методы обработчика для события.</span><span class="sxs-lookup"><span data-stu-id="f31bd-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="f31bd-112">Указывает, что метод удаляет методы обработчика для события.</span><span class="sxs-lookup"><span data-stu-id="f31bd-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="f31bd-113">Указывает, что метод вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="f31bd-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f31bd-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f31bd-114">Requirements</span></span>  
 <span data-ttu-id="f31bd-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f31bd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f31bd-116">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="f31bd-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f31bd-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f31bd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f31bd-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f31bd-118">See Also</span></span>  
 [<span data-ttu-id="f31bd-119">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="f31bd-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
