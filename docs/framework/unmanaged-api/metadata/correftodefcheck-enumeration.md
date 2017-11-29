---
title: "Перечисление CorRefToDefCheck"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorRefToDefCheck
api_location: mscoree.dll
api_type: COM
f1_keywords: CorRefToDefCheck
helpviewer_keywords: CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5144cd3ac261647c04ec7e3e27e28618c94fb439
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="6fa1d-102">Перечисление CorRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="6fa1d-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="6fa1d-103">Задает флаги для элемента управления, на который ссылаются элементы, преобразуемые в их определения для оптимизации кода.</span><span class="sxs-lookup"><span data-stu-id="6fa1d-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fa1d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6fa1d-104">Syntax</span></span>  
  
```  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="6fa1d-105">Члены</span><span class="sxs-lookup"><span data-stu-id="6fa1d-105">Members</span></span>  
  
|<span data-ttu-id="6fa1d-106">Член</span><span class="sxs-lookup"><span data-stu-id="6fa1d-106">Member</span></span>|<span data-ttu-id="6fa1d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6fa1d-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="6fa1d-108">Указывает, что тип ссылки и ссылки на элементы должны быть преобразованы в определения.</span><span class="sxs-lookup"><span data-stu-id="6fa1d-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="6fa1d-109">Значение по умолчанию (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span><span class="sxs-lookup"><span data-stu-id="6fa1d-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="6fa1d-110">Указывает, что все ссылаются элементы должны быть преобразованы в определения.</span><span class="sxs-lookup"><span data-stu-id="6fa1d-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="6fa1d-111">Указывает, что не ссылаются элементы должны быть преобразованы в определения.</span><span class="sxs-lookup"><span data-stu-id="6fa1d-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="6fa1d-112">Указывает, что только ссылки типа необходимо преобразовать в определения типа.</span><span class="sxs-lookup"><span data-stu-id="6fa1d-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="6fa1d-113">Указывает, что ссылки на элементы следует преобразовать в определения.</span><span class="sxs-lookup"><span data-stu-id="6fa1d-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="6fa1d-114">То есть для определения метода или определения полей должны преобразоваться ссылок на элементы.</span><span class="sxs-lookup"><span data-stu-id="6fa1d-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6fa1d-115">Требования</span><span class="sxs-lookup"><span data-stu-id="6fa1d-115">Requirements</span></span>  
 <span data-ttu-id="6fa1d-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fa1d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fa1d-117">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="6fa1d-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="6fa1d-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fa1d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fa1d-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6fa1d-119">See Also</span></span>  
 [<span data-ttu-id="6fa1d-120">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="6fa1d-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
