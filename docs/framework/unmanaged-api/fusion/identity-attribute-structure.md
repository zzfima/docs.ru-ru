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
ms.openlocfilehash: cb970d31fb5158adc7dbcbb7cc0175cc91c83c8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698048"
---
# <a name="identityattribute-structure"></a><span data-ttu-id="adbbb-102">Структура IDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="adbbb-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="adbbb-103">Содержит сведения об атрибутах метаданных о [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="adbbb-103">Contains metadata attribute information about an [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adbbb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="adbbb-104">Syntax</span></span>  
  
```  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="adbbb-105">Участники</span><span class="sxs-lookup"><span data-stu-id="adbbb-105">Members</span></span>  
  
|<span data-ttu-id="adbbb-106">Член</span><span class="sxs-lookup"><span data-stu-id="adbbb-106">Member</span></span>|<span data-ttu-id="adbbb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="adbbb-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="adbbb-108">Указатель на строку символов с завершающим нулем, содержащая пространство имен к которому принадлежит атрибут.</span><span class="sxs-lookup"><span data-stu-id="adbbb-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="adbbb-109">Указатель на строку символов с завершающим нулем, которая содержит имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="adbbb-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="adbbb-110">Указатель на строку символов с завершающим нулем, которая содержит значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="adbbb-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adbbb-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="adbbb-111">Remarks</span></span>  
 <span data-ttu-id="adbbb-112">`IDENTITY_ATTRIBUTE` Структура содержит три указатели на строки символов с завершающим нулем.</span><span class="sxs-lookup"><span data-stu-id="adbbb-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="adbbb-113">Эти три строки описывают один атрибут.</span><span class="sxs-lookup"><span data-stu-id="adbbb-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="adbbb-114">Экземпляр `IDENTITY_ATTRIBUTE` структура связан с экземпляром [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="adbbb-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="adbbb-115">`IDENTITY_ATTRIBUTE` Структура содержит фактические строки и соответствующий `IDENTITY_ATTRIBUTE_BLOB` структура перечислены смещения до трех строк в `IDENTITY_ATTRIBUTE` структуры.</span><span class="sxs-lookup"><span data-stu-id="adbbb-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adbbb-116">Требования</span><span class="sxs-lookup"><span data-stu-id="adbbb-116">Requirements</span></span>  
 <span data-ttu-id="adbbb-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adbbb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adbbb-118">**Заголовок.** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="adbbb-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="adbbb-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adbbb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adbbb-120">См. также</span><span class="sxs-lookup"><span data-stu-id="adbbb-120">See also</span></span>

- [<span data-ttu-id="adbbb-121">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="adbbb-121">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
- [<span data-ttu-id="adbbb-122">Структура IDENTITY_ATTRIBUTE_BLOB</span><span class="sxs-lookup"><span data-stu-id="adbbb-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)
- [<span data-ttu-id="adbbb-123">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="adbbb-123">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
