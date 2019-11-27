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
ms.openlocfilehash: bab215a8221696a0e43e228278085fcef52a40e9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442822"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="1f012-102">Перечисление CorMethodSemanticsAttr</span><span class="sxs-lookup"><span data-stu-id="1f012-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="1f012-103">Содержит значения, описывающие связь между методом и соответствующим свойством или событием.</span><span class="sxs-lookup"><span data-stu-id="1f012-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f012-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f012-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="1f012-105">Члены</span><span class="sxs-lookup"><span data-stu-id="1f012-105">Members</span></span>  
  
|<span data-ttu-id="1f012-106">Член</span><span class="sxs-lookup"><span data-stu-id="1f012-106">Member</span></span>|<span data-ttu-id="1f012-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1f012-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="1f012-108">Указывает, что метод является `set`ным методом доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="1f012-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="1f012-109">Указывает, что метод является `get`ным методом доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="1f012-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="1f012-110">Указывает, что метод имеет связь со свойством или событием, отличным от указанных здесь.</span><span class="sxs-lookup"><span data-stu-id="1f012-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="1f012-111">Указывает, что метод добавляет методы обработчика для события.</span><span class="sxs-lookup"><span data-stu-id="1f012-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="1f012-112">Указывает, что метод удаляет методы обработчика для события.</span><span class="sxs-lookup"><span data-stu-id="1f012-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="1f012-113">Указывает, что метод вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="1f012-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1f012-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1f012-114">Requirements</span></span>  
 <span data-ttu-id="1f012-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f012-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f012-116">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="1f012-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1f012-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f012-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f012-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="1f012-118">See also</span></span>

- [<span data-ttu-id="1f012-119">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="1f012-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
