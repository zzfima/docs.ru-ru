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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f1a0fff266e964b506b2dc7c4030caa54abaa5ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59171825"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="ec371-102">Перечисление CorPropertyAttr</span><span class="sxs-lookup"><span data-stu-id="ec371-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="ec371-103">Содержит значения, описывающие метаданные свойства.</span><span class="sxs-lookup"><span data-stu-id="ec371-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec371-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec371-104">Syntax</span></span>  
  
```  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="ec371-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ec371-105">Members</span></span>  
  
|<span data-ttu-id="ec371-106">Член</span><span class="sxs-lookup"><span data-stu-id="ec371-106">Member</span></span>|<span data-ttu-id="ec371-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ec371-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="ec371-108">Указывает, что это специальное свойство, и указывает его имя как.</span><span class="sxs-lookup"><span data-stu-id="ec371-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="ec371-109">Зарезервировано для внутреннего использования средой CLR.</span><span class="sxs-lookup"><span data-stu-id="ec371-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="ec371-110">Указывает, что внутренние API метаданных среды CLR должна проверять кодировку имени свойства.</span><span class="sxs-lookup"><span data-stu-id="ec371-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="ec371-111">Указывает, что свойство имеет значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ec371-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="ec371-112">Не используется.</span><span class="sxs-lookup"><span data-stu-id="ec371-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ec371-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ec371-113">Requirements</span></span>  
 <span data-ttu-id="ec371-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec371-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec371-115">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ec371-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ec371-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec371-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec371-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ec371-117">See also</span></span>

- [<span data-ttu-id="ec371-118">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="ec371-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
