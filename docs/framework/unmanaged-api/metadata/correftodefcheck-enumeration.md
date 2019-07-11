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
ms.openlocfilehash: 2ae87dd4538a9a8e88591f498c0ce77b51bfa852
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781620"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="44e92-102">Перечисление CorRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="44e92-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="44e92-103">Задает флаги для элемента управления, на который ссылаются элементы, преобразуемые в их определения для оптимизации кода.</span><span class="sxs-lookup"><span data-stu-id="44e92-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44e92-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44e92-104">Syntax</span></span>  
  
```cpp  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="44e92-105">Участники</span><span class="sxs-lookup"><span data-stu-id="44e92-105">Members</span></span>  
  
|<span data-ttu-id="44e92-106">Член</span><span class="sxs-lookup"><span data-stu-id="44e92-106">Member</span></span>|<span data-ttu-id="44e92-107">Описание</span><span class="sxs-lookup"><span data-stu-id="44e92-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="44e92-108">Указывает, что тип ссылки и ссылки на член должно быть преобразовано в определения.</span><span class="sxs-lookup"><span data-stu-id="44e92-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="44e92-109">Это значение по умолчанию (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span><span class="sxs-lookup"><span data-stu-id="44e92-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="44e92-110">Указывает, что все элементы, на которые имеются ссылки, должны преобразовываться к определениям.</span><span class="sxs-lookup"><span data-stu-id="44e92-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="44e92-111">Указывает, что не ссылаются элементы должны быть преобразованы в определения.</span><span class="sxs-lookup"><span data-stu-id="44e92-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="44e92-112">Указывает, что только ссылки на тип должно быть преобразовано в тип определения.</span><span class="sxs-lookup"><span data-stu-id="44e92-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="44e92-113">Указывает, что только ссылки на член должно быть преобразовано в определения.</span><span class="sxs-lookup"><span data-stu-id="44e92-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="44e92-114">То есть ссылки на элементы должны преобразовываться в определения метода или определения полей.</span><span class="sxs-lookup"><span data-stu-id="44e92-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="44e92-115">Требования</span><span class="sxs-lookup"><span data-stu-id="44e92-115">Requirements</span></span>  
 <span data-ttu-id="44e92-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44e92-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44e92-117">**Заголовок.** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="44e92-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="44e92-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44e92-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e92-119">См. также</span><span class="sxs-lookup"><span data-stu-id="44e92-119">See also</span></span>

- [<span data-ttu-id="44e92-120">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="44e92-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
