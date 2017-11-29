---
title: "Перечисление CorMethodSemanticsAttr"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorMethodSemanticsAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorMethodSemanticsAttr
helpviewer_keywords: CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c6dca24aad06b1c07c86cb716f4be344c8458471
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="0f695-102">Перечисление CorMethodSemanticsAttr</span><span class="sxs-lookup"><span data-stu-id="0f695-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="0f695-103">Содержит значения, описывающие связь между методом и соответствующим свойством или событием.</span><span class="sxs-lookup"><span data-stu-id="0f695-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f695-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f695-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="0f695-105">Члены</span><span class="sxs-lookup"><span data-stu-id="0f695-105">Members</span></span>  
  
|<span data-ttu-id="0f695-106">Член</span><span class="sxs-lookup"><span data-stu-id="0f695-106">Member</span></span>|<span data-ttu-id="0f695-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0f695-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="0f695-108">Указывает, что метод является `set` метод доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="0f695-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="0f695-109">Указывает, что метод является `get` метод доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="0f695-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="0f695-110">Указывает, что метод имеет связь с свойство или событие, отличные от определенных здесь.</span><span class="sxs-lookup"><span data-stu-id="0f695-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="0f695-111">Указывает, что метод добавляет методы обработчика для события.</span><span class="sxs-lookup"><span data-stu-id="0f695-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="0f695-112">Указывает, что метод удаляет методы обработчика для события.</span><span class="sxs-lookup"><span data-stu-id="0f695-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="0f695-113">Указывает, что метод вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="0f695-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0f695-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0f695-114">Requirements</span></span>  
 <span data-ttu-id="0f695-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f695-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f695-116">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="0f695-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="0f695-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f695-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f695-118">См. также</span><span class="sxs-lookup"><span data-stu-id="0f695-118">See Also</span></span>  
 [<span data-ttu-id="0f695-119">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="0f695-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
