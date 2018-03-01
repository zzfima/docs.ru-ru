---
title: "Метод EmitAssembly"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink2.EmitAssembly
- EmitAssembly
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssembly
helpviewer_keywords:
- EmitAssembly method
ms.assetid: 605ff39e-e5cc-4bff-8196-e8d68a9715b9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f012ea89fec0e64bc1639e6c47fb79249c25411a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="emitassembly-method"></a><span data-ttu-id="c009c-102">Метод EmitAssembly</span><span class="sxs-lookup"><span data-stu-id="c009c-102">EmitAssembly Method</span></span>
<span data-ttu-id="c009c-103">Создает сборку.</span><span class="sxs-lookup"><span data-stu-id="c009c-103">Creates the assembly.</span></span> <span data-ttu-id="c009c-104">Этот метод следует вызывайте после закрытия всех остальных файлов за исключением файла сборки.</span><span class="sxs-lookup"><span data-stu-id="c009c-104">Call this method after all other files are closed except for the assembly file.</span></span> <span data-ttu-id="c009c-105">Не вызывайте этот метод при создании непривязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="c009c-105">Do not call this method when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c009c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c009c-106">Syntax</span></span>  
  
```  
HRESULT EmitAssembly(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c009c-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="c009c-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c009c-108">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="c009c-108">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c009c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c009c-109">Return Value</span></span>  
 <span data-ttu-id="c009c-110">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="c009c-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c009c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="c009c-111">Requirements</span></span>  
 <span data-ttu-id="c009c-112">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="c009c-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c009c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c009c-113">See Also</span></span>  
 [<span data-ttu-id="c009c-114">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="c009c-114">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="c009c-115">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="c009c-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="c009c-116">API ALink</span><span class="sxs-lookup"><span data-stu-id="c009c-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
