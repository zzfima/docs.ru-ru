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
ms.openlocfilehash: 8b7edf1cc642228c4a79c855b51727264f31741c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107985"
---
# <a name="identity_attribute-structure"></a><span data-ttu-id="c793f-102">Структура IDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="c793f-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="c793f-103">Содержит сведения об атрибутах метаданных для экземпляра [идефинитионидентити](idefinitionidentity-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c793f-103">Contains metadata attribute information about an [IDefinitionIdentity](idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c793f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c793f-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="c793f-105">Члены</span><span class="sxs-lookup"><span data-stu-id="c793f-105">Members</span></span>  
  
|<span data-ttu-id="c793f-106">Член</span><span class="sxs-lookup"><span data-stu-id="c793f-106">Member</span></span>|<span data-ttu-id="c793f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c793f-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="c793f-108">Указатель на строку символов, завершающуюся нулем, которая содержит пространство имен, в котором находится атрибут.</span><span class="sxs-lookup"><span data-stu-id="c793f-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="c793f-109">Указатель на строку символов, завершающуюся нулем, которая содержит имя атрибута.</span><span class="sxs-lookup"><span data-stu-id="c793f-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="c793f-110">Указатель на строку символов, завершающуюся нулем, которая содержит значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="c793f-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c793f-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="c793f-111">Remarks</span></span>  
 <span data-ttu-id="c793f-112">Структура `IDENTITY_ATTRIBUTE` содержит три указателя на строки символов, заканчивающиеся символом NULL.</span><span class="sxs-lookup"><span data-stu-id="c793f-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="c793f-113">Эти три строки описывают один атрибут.</span><span class="sxs-lookup"><span data-stu-id="c793f-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="c793f-114">Экземпляр структуры `IDENTITY_ATTRIBUTE` связан с экземпляром структуры [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="c793f-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="c793f-115">Структура `IDENTITY_ATTRIBUTE` содержит фактические строки, а соответствующая структура `IDENTITY_ATTRIBUTE_BLOB` перечисляет смещения для трех строк, перечисленных в структуре `IDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="c793f-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c793f-116">Требования</span><span class="sxs-lookup"><span data-stu-id="c793f-116">Requirements</span></span>  
 <span data-ttu-id="c793f-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c793f-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c793f-118">**Заголовок:** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="c793f-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="c793f-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c793f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c793f-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c793f-120">See also</span></span>

- [<span data-ttu-id="c793f-121">Интерфейс IDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="c793f-121">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
- [<span data-ttu-id="c793f-122">Структура IDENTITY_ATTRIBUTE_BLOB</span><span class="sxs-lookup"><span data-stu-id="c793f-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](identity-attribute-blob-structure.md)
- [<span data-ttu-id="c793f-123">Структуры Fusion</span><span class="sxs-lookup"><span data-stu-id="c793f-123">Fusion Structures</span></span>](fusion-structures.md)
