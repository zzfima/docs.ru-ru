---
title: "Метод EmitManifest"
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
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 11966eccfdbbdbab29d305915afd904a54f9c57b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="emitmanifest-method"></a><span data-ttu-id="e3336-102">Метод EmitManifest</span><span class="sxs-lookup"><span data-stu-id="e3336-102">EmitManifest Method</span></span>
<span data-ttu-id="e3336-103">Выпускает конечный манифест.</span><span class="sxs-lookup"><span data-stu-id="e3336-103">Emits the final manifest.</span></span> <span data-ttu-id="e3336-104">Этот метод вызывается после импорта все файлы и настройки всех параметров.</span><span class="sxs-lookup"><span data-stu-id="e3336-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="e3336-105">Не вызывайте этот метод для несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="e3336-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3336-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3336-106">Syntax</span></span>  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e3336-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e3336-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="e3336-108">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="e3336-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="e3336-109">Получает размер для резервирования в файле сборки, полученные из [функция StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="e3336-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="e3336-110">При необходимости получает маркер манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="e3336-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3336-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e3336-111">Return Value</span></span>  
 <span data-ttu-id="e3336-112">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="e3336-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3336-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e3336-113">Requirements</span></span>  
 <span data-ttu-id="e3336-114">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="e3336-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3336-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e3336-115">See Also</span></span>  
 [<span data-ttu-id="e3336-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="e3336-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e3336-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="e3336-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="e3336-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="e3336-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
