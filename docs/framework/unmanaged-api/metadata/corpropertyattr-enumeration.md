---
title: "Перечисление CorPropertyAttr"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorPropertyAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorPropertyAttr
helpviewer_keywords: CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a87676064f39dc01d04e881bbf46476fb12a1c65
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="40878-102">Перечисление CorPropertyAttr</span><span class="sxs-lookup"><span data-stu-id="40878-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="40878-103">Содержит значения, описывающие метаданные свойства.</span><span class="sxs-lookup"><span data-stu-id="40878-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40878-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40878-104">Syntax</span></span>  
  
```  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,   
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="40878-105">Члены</span><span class="sxs-lookup"><span data-stu-id="40878-105">Members</span></span>  
  
|<span data-ttu-id="40878-106">Член</span><span class="sxs-lookup"><span data-stu-id="40878-106">Member</span></span>|<span data-ttu-id="40878-107">Описание</span><span class="sxs-lookup"><span data-stu-id="40878-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="40878-108">Указывает, что это свойство является особым, и указывает его имя как.</span><span class="sxs-lookup"><span data-stu-id="40878-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="40878-109">Зарезервировано для внутреннего использования средой CLR.</span><span class="sxs-lookup"><span data-stu-id="40878-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="40878-110">Указывает, что внутренние API метаданных среды CLR должны проверить кодировку имени свойства.</span><span class="sxs-lookup"><span data-stu-id="40878-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="40878-111">Указывает, что свойство имеет значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="40878-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="40878-112">Не используется.</span><span class="sxs-lookup"><span data-stu-id="40878-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="40878-113">Требования</span><span class="sxs-lookup"><span data-stu-id="40878-113">Requirements</span></span>  
 <span data-ttu-id="40878-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40878-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40878-115">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="40878-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="40878-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40878-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40878-117">См. также</span><span class="sxs-lookup"><span data-stu-id="40878-117">See Also</span></span>  
 [<span data-ttu-id="40878-118">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="40878-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
