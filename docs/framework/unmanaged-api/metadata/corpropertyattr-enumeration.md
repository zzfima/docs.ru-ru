---
title: Перечисление CorPropertyAttr
ms.date: 03/30/2017
api_name:
- CorPropertyAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPropertyAttr
helpviewer_keywords:
- CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type:
- apiref
ms.openlocfilehash: 2d49a146a465210cea8466a75666ca3f800b090b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450143"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="8fb44-102">Перечисление CorPropertyAttr</span><span class="sxs-lookup"><span data-stu-id="8fb44-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="8fb44-103">Содержит значения, описывающие метаданные свойства.</span><span class="sxs-lookup"><span data-stu-id="8fb44-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fb44-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8fb44-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="8fb44-105">Члены</span><span class="sxs-lookup"><span data-stu-id="8fb44-105">Members</span></span>  
  
|<span data-ttu-id="8fb44-106">Член</span><span class="sxs-lookup"><span data-stu-id="8fb44-106">Member</span></span>|<span data-ttu-id="8fb44-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8fb44-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="8fb44-108">Specifies that the property is special, and that its name describes how.</span><span class="sxs-lookup"><span data-stu-id="8fb44-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="8fb44-109">Reserved for internal use by the common language runtime.</span><span class="sxs-lookup"><span data-stu-id="8fb44-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="8fb44-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span><span class="sxs-lookup"><span data-stu-id="8fb44-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="8fb44-111">Specifies that the property has a default value.</span><span class="sxs-lookup"><span data-stu-id="8fb44-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="8fb44-112">Не используется.</span><span class="sxs-lookup"><span data-stu-id="8fb44-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8fb44-113">Требования</span><span class="sxs-lookup"><span data-stu-id="8fb44-113">Requirements</span></span>  
 <span data-ttu-id="8fb44-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fb44-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fb44-115">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="8fb44-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="8fb44-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fb44-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fb44-117">См. также</span><span class="sxs-lookup"><span data-stu-id="8fb44-117">See also</span></span>

- [<span data-ttu-id="8fb44-118">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="8fb44-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
