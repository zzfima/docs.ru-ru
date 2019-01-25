---
title: Метод SetNonAssemblyFlags
ms.date: 03/30/2017
api_name:
- IALink.SetNonAssemblyFlags
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetNonAssemblyFlags
helpviewer_keywords:
- SetNonAssemblyFlags method
ms.assetid: f8ba6fc8-f5aa-4066-ac96-56332758f5ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 78a7dab69e716e1662a277a69c008474d97f9bc4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619653"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="4e6b6-102">Метод SetNonAssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="4e6b6-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="4e6b6-103">Задает флаги, которые не зависящие от сборки.</span><span class="sxs-lookup"><span data-stu-id="4e6b6-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e6b6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4e6b6-104">Syntax</span></span>  
  
```  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e6b6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4e6b6-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="4e6b6-106">Флаги ALink.</span><span class="sxs-lookup"><span data-stu-id="4e6b6-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e6b6-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4e6b6-107">Return Value</span></span>  
 <span data-ttu-id="4e6b6-108">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="4e6b6-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e6b6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4e6b6-109">Requirements</span></span>  
 <span data-ttu-id="4e6b6-110">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="4e6b6-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e6b6-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4e6b6-111">See also</span></span>
- [<span data-ttu-id="4e6b6-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="4e6b6-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="4e6b6-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="4e6b6-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="4e6b6-114">API ALink</span><span class="sxs-lookup"><span data-stu-id="4e6b6-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
