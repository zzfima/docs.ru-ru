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
ms.openlocfilehash: 27ad89f1910bc7bb08a23c9fdb0d50828fb8b5e6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741435"
---
# <a name="setnonassemblyflags-method"></a><span data-ttu-id="4f1b8-102">Метод SetNonAssemblyFlags</span><span class="sxs-lookup"><span data-stu-id="4f1b8-102">SetNonAssemblyFlags Method</span></span>
<span data-ttu-id="4f1b8-103">Задает флаги, которые не зависящие от сборки.</span><span class="sxs-lookup"><span data-stu-id="4f1b8-103">Sets flags that are not assembly-specific.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f1b8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f1b8-104">Syntax</span></span>  
  
```cpp  
HRESULT SetNonAssemblyFlags(  
    AssemblyFlags afFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f1b8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f1b8-105">Parameters</span></span>  
 `afFlags`  
 <span data-ttu-id="4f1b8-106">Флаги ALink.</span><span class="sxs-lookup"><span data-stu-id="4f1b8-106">ALink flags.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f1b8-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4f1b8-107">Return Value</span></span>  
 <span data-ttu-id="4f1b8-108">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="4f1b8-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f1b8-109">Требования</span><span class="sxs-lookup"><span data-stu-id="4f1b8-109">Requirements</span></span>  
 <span data-ttu-id="4f1b8-110">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="4f1b8-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f1b8-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4f1b8-111">See also</span></span>

- [<span data-ttu-id="4f1b8-112">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="4f1b8-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="4f1b8-113">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="4f1b8-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="4f1b8-114">API ALink</span><span class="sxs-lookup"><span data-stu-id="4f1b8-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
