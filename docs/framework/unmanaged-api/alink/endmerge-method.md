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
ms.openlocfilehash: 9ba7c2d0c5ea29d5db429139f1831e8d71dd23f3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739145"
---
# <a name="endmerge-method"></a><span data-ttu-id="8780b-102">Метод EndMerge</span><span class="sxs-lookup"><span data-stu-id="8780b-102">EndMerge Method</span></span>
<span data-ttu-id="8780b-103">Указывает, что все настраиваемые атрибуты были объединены в область выдачи.</span><span class="sxs-lookup"><span data-stu-id="8780b-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8780b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8780b-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8780b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8780b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="8780b-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="8780b-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8780b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8780b-107">Return Value</span></span>  
 <span data-ttu-id="8780b-108">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="8780b-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8780b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8780b-109">Requirements</span></span>  
 <span data-ttu-id="8780b-110">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="8780b-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8780b-111">См. также</span><span class="sxs-lookup"><span data-stu-id="8780b-111">See also</span></span>
- [<span data-ttu-id="8780b-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="8780b-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="8780b-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="8780b-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="8780b-114">API ALink</span><span class="sxs-lookup"><span data-stu-id="8780b-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
