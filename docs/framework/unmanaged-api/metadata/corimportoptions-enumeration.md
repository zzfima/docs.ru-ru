---
title: Перечисление CorImportOptions
ms.date: 03/30/2017
api_name:
- CorImportOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorImportOptions
helpviewer_keywords:
- CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type:
- apiref
ms.openlocfilehash: 44d1776e2902988353ef4fd58aca20e56203b9da
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442840"
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="6144a-102">Перечисление CorImportOptions</span><span class="sxs-lookup"><span data-stu-id="6144a-102">CorImportOptions Enumeration</span></span>
<span data-ttu-id="6144a-103">Содержит значения флага, управляющие поведением во время импорта сборки за пределы текущей области.</span><span class="sxs-lookup"><span data-stu-id="6144a-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6144a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6144a-104">Syntax</span></span>  
  
```cpp  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="6144a-105">Члены</span><span class="sxs-lookup"><span data-stu-id="6144a-105">Members</span></span>  
  
|<span data-ttu-id="6144a-106">Член</span><span class="sxs-lookup"><span data-stu-id="6144a-106">Member</span></span>|<span data-ttu-id="6144a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6144a-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="6144a-108">Указывает поведение по умолчанию, которое пропускает удаленные записи.</span><span class="sxs-lookup"><span data-stu-id="6144a-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="6144a-109">Указывает, что необходимо перечислить все метаданные.</span><span class="sxs-lookup"><span data-stu-id="6144a-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="6144a-110">Указывает, что необходимо перечислить все определения типов, включая удаленные.</span><span class="sxs-lookup"><span data-stu-id="6144a-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="6144a-111">Указывает, что необходимо перечислить все Месоддефс, включая удаленные.</span><span class="sxs-lookup"><span data-stu-id="6144a-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="6144a-112">Указывает, что необходимо перечислить все Фиелддефс, включая удаленные.</span><span class="sxs-lookup"><span data-stu-id="6144a-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="6144a-113">Указывает, что необходимо перечислить все Пропертидефс, включая удаленные.</span><span class="sxs-lookup"><span data-stu-id="6144a-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="6144a-114">Указывает, что необходимо перечислить все Евентдефс, включая удаленные.</span><span class="sxs-lookup"><span data-stu-id="6144a-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="6144a-115">Указывает, что необходимо перечислить все настраиваемые атрибуты, включая удаленные.</span><span class="sxs-lookup"><span data-stu-id="6144a-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="6144a-116">Указывает, что должны быть перечислены все экспортированные типы, включая удаленные.</span><span class="sxs-lookup"><span data-stu-id="6144a-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6144a-117">Требования</span><span class="sxs-lookup"><span data-stu-id="6144a-117">Requirements</span></span>  
 <span data-ttu-id="6144a-118">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6144a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6144a-119">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="6144a-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6144a-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6144a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6144a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="6144a-121">See also</span></span>

- [<span data-ttu-id="6144a-122">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="6144a-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
