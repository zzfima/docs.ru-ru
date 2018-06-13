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
ms.openlocfilehash: 263981708af2e40bd3690a3cd344156488eed0dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442683"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="3f137-102">Перечисление CorPropertyAttr</span><span class="sxs-lookup"><span data-stu-id="3f137-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="3f137-103">Содержит значения, описывающие метаданные свойства.</span><span class="sxs-lookup"><span data-stu-id="3f137-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f137-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f137-104">Syntax</span></span>  
  
```  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="3f137-105">Участники</span><span class="sxs-lookup"><span data-stu-id="3f137-105">Members</span></span>  
  
|<span data-ttu-id="3f137-106">Член</span><span class="sxs-lookup"><span data-stu-id="3f137-106">Member</span></span>|<span data-ttu-id="3f137-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3f137-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="3f137-108">Указывает, что это свойство является особым, и указывает его имя как.</span><span class="sxs-lookup"><span data-stu-id="3f137-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="3f137-109">Зарезервировано для внутреннего использования средой CLR.</span><span class="sxs-lookup"><span data-stu-id="3f137-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="3f137-110">Указывает, что внутренние API метаданных среды CLR должны проверить кодировку имени свойства.</span><span class="sxs-lookup"><span data-stu-id="3f137-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="3f137-111">Указывает, что свойство имеет значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3f137-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="3f137-112">Не используется.</span><span class="sxs-lookup"><span data-stu-id="3f137-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3f137-113">Требования</span><span class="sxs-lookup"><span data-stu-id="3f137-113">Requirements</span></span>  
 <span data-ttu-id="3f137-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f137-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f137-115">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="3f137-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3f137-116">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f137-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f137-117">См. также</span><span class="sxs-lookup"><span data-stu-id="3f137-117">See Also</span></span>  
 [<span data-ttu-id="3f137-118">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="3f137-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
