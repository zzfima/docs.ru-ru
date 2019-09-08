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
ms.openlocfilehash: e0bcabb32d50b236d42a555c073b50ba3a234dde
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796487"
---
# <a name="identity_attribute-structure"></a><span data-ttu-id="47f81-102">Структура IDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="47f81-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="47f81-103">Содержит сведения об атрибутах метаданных для экземпляра [идефинитионидентити](idefinitionidentity-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="47f81-103">Contains metadata attribute information about an [IDefinitionIdentity](idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47f81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="47f81-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="47f81-105">Участники</span><span class="sxs-lookup"><span data-stu-id="47f81-105">Members</span></span>  
  
|<span data-ttu-id="47f81-106">Член</span><span class="sxs-lookup"><span data-stu-id="47f81-106">Member</span></span>|<span data-ttu-id="47f81-107">Описание</span><span class="sxs-lookup"><span data-stu-id="47f81-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="47f81-108">Указатель на строку символов, завершающуюся нулем, которая содержит пространство имен, в котором находится атрибут.</span><span class="sxs-lookup"><span data-stu-id="47f81-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="47f81-109">Указатель на строку символов, завершающуюся нулем, которая содержит имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="47f81-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="47f81-110">Указатель на строку символов, завершающуюся нулем, которая содержит значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="47f81-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47f81-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="47f81-111">Remarks</span></span>  
 <span data-ttu-id="47f81-112">`IDENTITY_ATTRIBUTE` Структура содержит три указателя на строки символов, заканчивающиеся нулем.</span><span class="sxs-lookup"><span data-stu-id="47f81-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="47f81-113">Эти три строки описывают один атрибут.</span><span class="sxs-lookup"><span data-stu-id="47f81-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="47f81-114">Экземпляр `IDENTITY_ATTRIBUTE` структуры связан с экземпляром структуры [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="47f81-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="47f81-115">Структура содержит фактические строки, а соответствующая `IDENTITY_ATTRIBUTE_BLOB` структура перечисляет смещения для `IDENTITY_ATTRIBUTE` трех строк, перечисленных в структуре. `IDENTITY_ATTRIBUTE`</span><span class="sxs-lookup"><span data-stu-id="47f81-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47f81-116">Требования</span><span class="sxs-lookup"><span data-stu-id="47f81-116">Requirements</span></span>  
 <span data-ttu-id="47f81-117">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47f81-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47f81-118">**Заголовок.** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="47f81-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="47f81-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47f81-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47f81-120">См. также</span><span class="sxs-lookup"><span data-stu-id="47f81-120">See also</span></span>

- [<span data-ttu-id="47f81-121">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="47f81-121">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
- [<span data-ttu-id="47f81-122">Структура IDENTITY_ATTRIBUTE_BLOB</span><span class="sxs-lookup"><span data-stu-id="47f81-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](identity-attribute-blob-structure.md)
- [<span data-ttu-id="47f81-123">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="47f81-123">Fusion Structures</span></span>](fusion-structures.md)
