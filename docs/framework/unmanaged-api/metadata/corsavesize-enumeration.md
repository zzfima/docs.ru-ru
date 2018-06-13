---
title: Перечисление CorSaveSize
ms.date: 03/30/2017
api_name:
- CorSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSaveSize
helpviewer_keywords:
- CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66f9f95b0cf19acb677daf7f7401d21cc81864a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447611"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="79485-102">Перечисление CorSaveSize</span><span class="sxs-lookup"><span data-stu-id="79485-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="79485-103">Содержит значения, указывающие уровень точности, необходимый при запросе размера операции сохранения.</span><span class="sxs-lookup"><span data-stu-id="79485-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79485-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="79485-104">Syntax</span></span>  
  
```  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="79485-105">Участники</span><span class="sxs-lookup"><span data-stu-id="79485-105">Members</span></span>  
  
|<span data-ttu-id="79485-106">Член</span><span class="sxs-lookup"><span data-stu-id="79485-106">Member</span></span>|<span data-ttu-id="79485-107">Описание</span><span class="sxs-lookup"><span data-stu-id="79485-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="79485-108">Указывает, что возвращаемое значение должно быть точным.</span><span class="sxs-lookup"><span data-stu-id="79485-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="79485-109">Указывает, что возвращаемое значение должно быть приблизительным.</span><span class="sxs-lookup"><span data-stu-id="79485-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="79485-110">Указывает, что удаляемые типы должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="79485-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="79485-111">Требования</span><span class="sxs-lookup"><span data-stu-id="79485-111">Requirements</span></span>  
 <span data-ttu-id="79485-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79485-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79485-113">**Заголовок:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="79485-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="79485-114">**Библиотека:** используется как ресурс в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="79485-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="79485-115">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79485-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79485-116">См. также</span><span class="sxs-lookup"><span data-stu-id="79485-116">See Also</span></span>  
 [<span data-ttu-id="79485-117">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="79485-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
