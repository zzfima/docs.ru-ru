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
ms.openlocfilehash: 5caf432b5de7cb0c8ff0e6f53b3e79a64ecf802e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443317"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="2e51c-102">Перечисление CorRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="2e51c-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="2e51c-103">Задает флаги для элемента управления, на который ссылаются элементы, преобразуемые в их определения для оптимизации кода.</span><span class="sxs-lookup"><span data-stu-id="2e51c-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e51c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2e51c-104">Syntax</span></span>  
  
```  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="2e51c-105">Участники</span><span class="sxs-lookup"><span data-stu-id="2e51c-105">Members</span></span>  
  
|<span data-ttu-id="2e51c-106">Член</span><span class="sxs-lookup"><span data-stu-id="2e51c-106">Member</span></span>|<span data-ttu-id="2e51c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="2e51c-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="2e51c-108">Указывает, что тип ссылки и ссылки на элементы должны быть преобразованы в определения.</span><span class="sxs-lookup"><span data-stu-id="2e51c-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="2e51c-109">Значение по умолчанию (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span><span class="sxs-lookup"><span data-stu-id="2e51c-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="2e51c-110">Указывает, что все ссылаются элементы должны быть преобразованы в определения.</span><span class="sxs-lookup"><span data-stu-id="2e51c-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="2e51c-111">Указывает, что не ссылаются элементы должны быть преобразованы в определения.</span><span class="sxs-lookup"><span data-stu-id="2e51c-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="2e51c-112">Указывает, что только ссылки типа необходимо преобразовать в определения типа.</span><span class="sxs-lookup"><span data-stu-id="2e51c-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="2e51c-113">Указывает, что ссылки на элементы следует преобразовать в определения.</span><span class="sxs-lookup"><span data-stu-id="2e51c-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="2e51c-114">То есть для определения метода или определения полей должны преобразоваться ссылок на элементы.</span><span class="sxs-lookup"><span data-stu-id="2e51c-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e51c-115">Требования</span><span class="sxs-lookup"><span data-stu-id="2e51c-115">Requirements</span></span>  
 <span data-ttu-id="2e51c-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e51c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e51c-117">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="2e51c-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2e51c-118">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e51c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e51c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="2e51c-119">See Also</span></span>  
 [<span data-ttu-id="2e51c-120">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="2e51c-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
