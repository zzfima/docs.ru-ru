---
title: Перечисление CorRefToDefCheck
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82abeb0ce3db075d794787bb1fcd5bc18321bef2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906182"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="9b092-102">Перечисление CorRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="9b092-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="9b092-103">Задает флаги для элемента управления, на который ссылаются элементы, преобразуемые в их определения для оптимизации кода.</span><span class="sxs-lookup"><span data-stu-id="9b092-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b092-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9b092-104">Syntax</span></span>  
  
```  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="9b092-105">Участники</span><span class="sxs-lookup"><span data-stu-id="9b092-105">Members</span></span>  
  
|<span data-ttu-id="9b092-106">Член</span><span class="sxs-lookup"><span data-stu-id="9b092-106">Member</span></span>|<span data-ttu-id="9b092-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9b092-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="9b092-108">Указывает, что тип ссылки и ссылки на член должно быть преобразовано в определения.</span><span class="sxs-lookup"><span data-stu-id="9b092-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="9b092-109">Это значение по умолчанию (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span><span class="sxs-lookup"><span data-stu-id="9b092-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="9b092-110">Указывает, что все элементы, на которые имеются ссылки, должны преобразовываться к определениям.</span><span class="sxs-lookup"><span data-stu-id="9b092-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="9b092-111">Указывает, что не ссылаются элементы должны быть преобразованы в определения.</span><span class="sxs-lookup"><span data-stu-id="9b092-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="9b092-112">Указывает, что только ссылки на тип должно быть преобразовано в тип определения.</span><span class="sxs-lookup"><span data-stu-id="9b092-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="9b092-113">Указывает, что только ссылки на член должно быть преобразовано в определения.</span><span class="sxs-lookup"><span data-stu-id="9b092-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="9b092-114">То есть ссылки на элементы должны преобразовываться в определения метода или определения полей.</span><span class="sxs-lookup"><span data-stu-id="9b092-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b092-115">Требования</span><span class="sxs-lookup"><span data-stu-id="9b092-115">Requirements</span></span>  
 <span data-ttu-id="9b092-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b092-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b092-117">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9b092-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9b092-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b092-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b092-119">См. также</span><span class="sxs-lookup"><span data-stu-id="9b092-119">See also</span></span>

- [<span data-ttu-id="9b092-120">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="9b092-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
