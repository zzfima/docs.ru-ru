---
title: Метод CloseAssembly
ms.date: 03/30/2017
api_name:
- IALink.CloseAssembly
- CloseAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseAssembly
helpviewer_keywords:
- CloseAssembly method
ms.assetid: f66a43bc-a5c5-4190-acbe-63fd27640634
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aa415926f4a818f697812f1a3c5531cb0ab7081b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54510173"
---
# <a name="closeassembly-method"></a><span data-ttu-id="3d1f8-102">Метод CloseAssembly</span><span class="sxs-lookup"><span data-stu-id="3d1f8-102">CloseAssembly Method</span></span>
<span data-ttu-id="3d1f8-103">Завершает операции сборки.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-103">Finalizes assembly operations.</span></span> <span data-ttu-id="3d1f8-104">Этот метод вызывается перед началом новой сборки или модуля, не связанного с данными.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-104">Call this method before beginning a new assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d1f8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d1f8-105">Syntax</span></span>  
  
```  
HRESULT CloseAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d1f8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d1f8-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3d1f8-107">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-107">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d1f8-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3d1f8-108">Return Value</span></span>  
 <span data-ttu-id="3d1f8-109">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d1f8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3d1f8-110">Requirements</span></span>  
 <span data-ttu-id="3d1f8-111">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="3d1f8-111">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d1f8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3d1f8-112">See also</span></span>
- [<span data-ttu-id="3d1f8-113">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="3d1f8-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3d1f8-114">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="3d1f8-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3d1f8-115">API ALink</span><span class="sxs-lookup"><span data-stu-id="3d1f8-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
