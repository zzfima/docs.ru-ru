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
ms.openlocfilehash: e8f9eecd6d6d74717eb7c1e389bfa24e40afc950
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="endmerge-method"></a><span data-ttu-id="b9381-102">Метод EndMerge</span><span class="sxs-lookup"><span data-stu-id="b9381-102">EndMerge Method</span></span>
<span data-ttu-id="b9381-103">Указывает, что все настраиваемые атрибуты были объединены в область выдачи.</span><span class="sxs-lookup"><span data-stu-id="b9381-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9381-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9381-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9381-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9381-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b9381-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="b9381-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9381-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b9381-107">Return Value</span></span>  
 <span data-ttu-id="b9381-108">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="b9381-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9381-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b9381-109">Requirements</span></span>  
 <span data-ttu-id="b9381-110">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="b9381-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9381-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b9381-111">See Also</span></span>  
 [<span data-ttu-id="b9381-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="b9381-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="b9381-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="b9381-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="b9381-114">API ALink</span><span class="sxs-lookup"><span data-stu-id="b9381-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
