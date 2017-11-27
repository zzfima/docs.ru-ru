---
title: "Структура IDENTITY_ATTRIBUTE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDENTITY_ATTRIBUTE
api_location: fusion.dll
api_type: COM
f1_keywords: IDENTITY_ATTRIBUTE
helpviewer_keywords: IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3fc4d9f7a95a3283d87f036163592f43e87dd053
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="identityattribute-structure"></a><span data-ttu-id="1c23a-102">Структура IDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="1c23a-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="1c23a-103">Содержит сведения об атрибутах метаданных о [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1c23a-103">Contains metadata attribute information about an [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c23a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1c23a-104">Syntax</span></span>  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="1c23a-105">Члены</span><span class="sxs-lookup"><span data-stu-id="1c23a-105">Members</span></span>  
  
|<span data-ttu-id="1c23a-106">Член</span><span class="sxs-lookup"><span data-stu-id="1c23a-106">Member</span></span>|<span data-ttu-id="1c23a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1c23a-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="1c23a-108">Указатель на завершающуюся значением null строка, содержащая пространство имен к которому принадлежит атрибут.</span><span class="sxs-lookup"><span data-stu-id="1c23a-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="1c23a-109">Указатель на завершающуюся значением null строка, содержащая имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="1c23a-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="1c23a-110">Указатель на завершающуюся значением null строка, содержащая значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="1c23a-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c23a-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="1c23a-111">Remarks</span></span>  
 <span data-ttu-id="1c23a-112">`IDENTITY_ATTRIBUTE` Структура содержит три указатели на строки символом null.</span><span class="sxs-lookup"><span data-stu-id="1c23a-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="1c23a-113">Эти три строки описывают один атрибут.</span><span class="sxs-lookup"><span data-stu-id="1c23a-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="1c23a-114">Экземпляр `IDENTITY_ATTRIBUTE` структуры связан с экземпляром [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="1c23a-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="1c23a-115">`IDENTITY_ATTRIBUTE` Структура содержит фактические строки и соответствующий `IDENTITY_ATTRIBUTE_BLOB` структуры перечислены смещения до трех строк в `IDENTITY_ATTRIBUTE` структуры.</span><span class="sxs-lookup"><span data-stu-id="1c23a-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c23a-116">Требования</span><span class="sxs-lookup"><span data-stu-id="1c23a-116">Requirements</span></span>  
 <span data-ttu-id="1c23a-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c23a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c23a-118">**Заголовок:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="1c23a-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="1c23a-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c23a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c23a-120">См. также</span><span class="sxs-lookup"><span data-stu-id="1c23a-120">See Also</span></span>  
 [<span data-ttu-id="1c23a-121">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="1c23a-121">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 [<span data-ttu-id="1c23a-122">IDENTITY_ATTRIBUTE_BLOB-структура</span><span class="sxs-lookup"><span data-stu-id="1c23a-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)  
 [<span data-ttu-id="1c23a-123">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="1c23a-123">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
