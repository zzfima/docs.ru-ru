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
ms.openlocfilehash: 95a798d662b44cf2e088af84d3b1eec97da8e7fb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177945"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="5120d-102">Перечисление CorPropertyAttr</span><span class="sxs-lookup"><span data-stu-id="5120d-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="5120d-103">Содержит значения, описывающие метаданные свойства.</span><span class="sxs-lookup"><span data-stu-id="5120d-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5120d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5120d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="5120d-105">Члены</span><span class="sxs-lookup"><span data-stu-id="5120d-105">Members</span></span>  
  
|<span data-ttu-id="5120d-106">Участник</span><span class="sxs-lookup"><span data-stu-id="5120d-106">Member</span></span>|<span data-ttu-id="5120d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5120d-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="5120d-108">Уточняется, что свойство является особенным, и что его название описывает, как.</span><span class="sxs-lookup"><span data-stu-id="5120d-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="5120d-109">Зарезервировано для внутреннего использования общим временем выполнения языка.</span><span class="sxs-lookup"><span data-stu-id="5120d-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="5120d-110">Уточняется, что внутренние AAIs с общим временем выполнения языка должны проверять кодирование имени свойства.</span><span class="sxs-lookup"><span data-stu-id="5120d-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="5120d-111">Указывает, что свойство имеет значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5120d-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="5120d-112">Не используется.</span><span class="sxs-lookup"><span data-stu-id="5120d-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5120d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="5120d-113">Requirements</span></span>  
 <span data-ttu-id="5120d-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5120d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5120d-115">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="5120d-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5120d-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5120d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5120d-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5120d-117">See also</span></span>

- [<span data-ttu-id="5120d-118">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="5120d-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
