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
ms.openlocfilehash: 5e36cb91c3ef741badb04b54e2b62158ecf6ced1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59134502"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="60469-102">Перечисление CorMethodSemanticsAttr</span><span class="sxs-lookup"><span data-stu-id="60469-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="60469-103">Содержит значения, описывающие связь между методом и соответствующим свойством или событием.</span><span class="sxs-lookup"><span data-stu-id="60469-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60469-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="60469-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="60469-105">Участники</span><span class="sxs-lookup"><span data-stu-id="60469-105">Members</span></span>  
  
|<span data-ttu-id="60469-106">Член</span><span class="sxs-lookup"><span data-stu-id="60469-106">Member</span></span>|<span data-ttu-id="60469-107">Описание</span><span class="sxs-lookup"><span data-stu-id="60469-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="60469-108">Указывает, что метод вызывается `set` метод доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="60469-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="60469-109">Указывает, что метод вызывается `get` метод доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="60469-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="60469-110">Указывает, что метод имеет отношение к свойство или событие, отличные от определенных здесь.</span><span class="sxs-lookup"><span data-stu-id="60469-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="60469-111">Указывает, что этот метод добавляет методы обработчика для события.</span><span class="sxs-lookup"><span data-stu-id="60469-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="60469-112">Указывает, что метод удаляет методы обработчика для события.</span><span class="sxs-lookup"><span data-stu-id="60469-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="60469-113">Указывает, что метод вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="60469-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="60469-114">Требования</span><span class="sxs-lookup"><span data-stu-id="60469-114">Requirements</span></span>  
 <span data-ttu-id="60469-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60469-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60469-116">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="60469-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="60469-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60469-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60469-118">См. также</span><span class="sxs-lookup"><span data-stu-id="60469-118">See also</span></span>

- [<span data-ttu-id="60469-119">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="60469-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
