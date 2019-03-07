---
title: Метод EndMerge
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7d4b102485db0199f748f6c5b6c4ab40d21429e9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494419"
---
# <a name="endmerge-method"></a><span data-ttu-id="6ac47-102">Метод EndMerge</span><span class="sxs-lookup"><span data-stu-id="6ac47-102">EndMerge Method</span></span>
<span data-ttu-id="6ac47-103">Указывает, что все настраиваемые атрибуты были объединены в область выдачи.</span><span class="sxs-lookup"><span data-stu-id="6ac47-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ac47-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6ac47-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ac47-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6ac47-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="6ac47-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="6ac47-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ac47-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6ac47-107">Return Value</span></span>  
 <span data-ttu-id="6ac47-108">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="6ac47-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ac47-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6ac47-109">Requirements</span></span>  
 <span data-ttu-id="6ac47-110">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="6ac47-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ac47-111">См. также</span><span class="sxs-lookup"><span data-stu-id="6ac47-111">See also</span></span>
- [<span data-ttu-id="6ac47-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="6ac47-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="6ac47-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="6ac47-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="6ac47-114">API ALink</span><span class="sxs-lookup"><span data-stu-id="6ac47-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
