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
ms.openlocfilehash: 88f594117fffedb6acafef26a9e834dd951ea5bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787528"
---
# <a name="endmerge-method"></a><span data-ttu-id="388d8-102">Метод EndMerge</span><span class="sxs-lookup"><span data-stu-id="388d8-102">EndMerge Method</span></span>
<span data-ttu-id="388d8-103">Указывает, что все пользовательские атрибуты были объединены в область действия Emit.</span><span class="sxs-lookup"><span data-stu-id="388d8-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="388d8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="388d8-104">Syntax</span></span>  
  
```cpp  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="388d8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="388d8-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="388d8-106">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="388d8-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="388d8-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="388d8-107">Return Value</span></span>  
 <span data-ttu-id="388d8-108">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="388d8-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="388d8-109">Требования</span><span class="sxs-lookup"><span data-stu-id="388d8-109">Requirements</span></span>  
 <span data-ttu-id="388d8-110">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="388d8-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="388d8-111">См. также</span><span class="sxs-lookup"><span data-stu-id="388d8-111">See also</span></span>

- [<span data-ttu-id="388d8-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="388d8-112">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="388d8-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="388d8-113">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="388d8-114">API ALink</span><span class="sxs-lookup"><span data-stu-id="388d8-114">ALink API</span></span>](index.md)
