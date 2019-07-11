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
ms.openlocfilehash: de1646cdbc11369b43a821d8b762879d1df7ed2e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751538"
---
# <a name="identityattribute-structure"></a><span data-ttu-id="71ecf-102">Структура IDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="71ecf-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="71ecf-103">Содержит сведения об атрибутах метаданных о [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) экземпляра.</span><span class="sxs-lookup"><span data-stu-id="71ecf-103">Contains metadata attribute information about an [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71ecf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71ecf-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="71ecf-105">Участники</span><span class="sxs-lookup"><span data-stu-id="71ecf-105">Members</span></span>  
  
|<span data-ttu-id="71ecf-106">Член</span><span class="sxs-lookup"><span data-stu-id="71ecf-106">Member</span></span>|<span data-ttu-id="71ecf-107">Описание</span><span class="sxs-lookup"><span data-stu-id="71ecf-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="71ecf-108">Указатель на строку символов с завершающим нулем, содержащая пространство имен к которому принадлежит атрибут.</span><span class="sxs-lookup"><span data-stu-id="71ecf-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="71ecf-109">Указатель на строку символов с завершающим нулем, которая содержит имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="71ecf-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="71ecf-110">Указатель на строку символов с завершающим нулем, которая содержит значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="71ecf-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71ecf-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="71ecf-111">Remarks</span></span>  
 <span data-ttu-id="71ecf-112">`IDENTITY_ATTRIBUTE` Структура содержит три указатели на строки символов с завершающим нулем.</span><span class="sxs-lookup"><span data-stu-id="71ecf-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="71ecf-113">Эти три строки описывают один атрибут.</span><span class="sxs-lookup"><span data-stu-id="71ecf-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="71ecf-114">Экземпляр `IDENTITY_ATTRIBUTE` структура связан с экземпляром [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) структуры.</span><span class="sxs-lookup"><span data-stu-id="71ecf-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="71ecf-115">`IDENTITY_ATTRIBUTE` Структура содержит фактические строки и соответствующий `IDENTITY_ATTRIBUTE_BLOB` структура перечислены смещения до трех строк в `IDENTITY_ATTRIBUTE` структуры.</span><span class="sxs-lookup"><span data-stu-id="71ecf-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71ecf-116">Требования</span><span class="sxs-lookup"><span data-stu-id="71ecf-116">Requirements</span></span>  
 <span data-ttu-id="71ecf-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71ecf-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71ecf-118">**Заголовок.** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="71ecf-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="71ecf-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71ecf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71ecf-120">См. также</span><span class="sxs-lookup"><span data-stu-id="71ecf-120">See also</span></span>

- [<span data-ttu-id="71ecf-121">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="71ecf-121">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
- [<span data-ttu-id="71ecf-122">Структура IDENTITY_ATTRIBUTE_BLOB</span><span class="sxs-lookup"><span data-stu-id="71ecf-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)
- [<span data-ttu-id="71ecf-123">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="71ecf-123">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
