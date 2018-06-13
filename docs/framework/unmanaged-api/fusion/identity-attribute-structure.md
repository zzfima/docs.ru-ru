---
title: Структура IDENTITY_ATTRIBUTE
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f716ff35ae0cd3d2a53c55756b8957e54fa355c6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431539"
---
# <a name="identityattribute-structure"></a><span data-ttu-id="5a6ac-102">Структура IDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="5a6ac-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="5a6ac-103">Содержит сведения об атрибутах метаданных о [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5a6ac-103">Contains metadata attribute information about an [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a6ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5a6ac-104">Syntax</span></span>  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="5a6ac-105">Участники</span><span class="sxs-lookup"><span data-stu-id="5a6ac-105">Members</span></span>  
  
|<span data-ttu-id="5a6ac-106">Член</span><span class="sxs-lookup"><span data-stu-id="5a6ac-106">Member</span></span>|<span data-ttu-id="5a6ac-107">Описание</span><span class="sxs-lookup"><span data-stu-id="5a6ac-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="5a6ac-108">Указатель на завершающуюся значением null строка, содержащая пространство имен к которому принадлежит атрибут.</span><span class="sxs-lookup"><span data-stu-id="5a6ac-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="5a6ac-109">Указатель на завершающуюся значением null строка, содержащая имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="5a6ac-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="5a6ac-110">Указатель на завершающуюся значением null строка, содержащая значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="5a6ac-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a6ac-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="5a6ac-111">Remarks</span></span>  
 <span data-ttu-id="5a6ac-112">`IDENTITY_ATTRIBUTE` Структура содержит три указатели на строки символом null.</span><span class="sxs-lookup"><span data-stu-id="5a6ac-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="5a6ac-113">Эти три строки описывают один атрибут.</span><span class="sxs-lookup"><span data-stu-id="5a6ac-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="5a6ac-114">Экземпляр `IDENTITY_ATTRIBUTE` структуры связан с экземпляром [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="5a6ac-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="5a6ac-115">`IDENTITY_ATTRIBUTE` Структура содержит фактические строки и соответствующий `IDENTITY_ATTRIBUTE_BLOB` структуры перечислены смещения до трех строк в `IDENTITY_ATTRIBUTE` структуры.</span><span class="sxs-lookup"><span data-stu-id="5a6ac-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a6ac-116">Требования</span><span class="sxs-lookup"><span data-stu-id="5a6ac-116">Requirements</span></span>  
 <span data-ttu-id="5a6ac-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a6ac-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a6ac-118">**Заголовок:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="5a6ac-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="5a6ac-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a6ac-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a6ac-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5a6ac-120">See Also</span></span>  
 [<span data-ttu-id="5a6ac-121">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="5a6ac-121">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 [<span data-ttu-id="5a6ac-122">Структура IDENTITY_ATTRIBUTE_BLOB</span><span class="sxs-lookup"><span data-stu-id="5a6ac-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)  
 [<span data-ttu-id="5a6ac-123">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="5a6ac-123">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
