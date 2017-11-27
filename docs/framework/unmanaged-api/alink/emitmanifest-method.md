---
title: "Метод EmitManifest"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EmitManifest
- IALink.EmitManifest
api_location: alink.dll
api_type: COM
f1_keywords: EmitManifest
helpviewer_keywords: EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 03ef815f03a65cbf7e2dc936b21848e206132add
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="emitmanifest-method"></a><span data-ttu-id="fdea4-102">Метод EmitManifest</span><span class="sxs-lookup"><span data-stu-id="fdea4-102">EmitManifest Method</span></span>
<span data-ttu-id="fdea4-103">Выпускает конечный манифест.</span><span class="sxs-lookup"><span data-stu-id="fdea4-103">Emits the final manifest.</span></span> <span data-ttu-id="fdea4-104">Этот метод вызывается после импорта все файлы и настройки всех параметров.</span><span class="sxs-lookup"><span data-stu-id="fdea4-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="fdea4-105">Не вызывайте этот метод для несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="fdea4-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdea4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fdea4-106">Syntax</span></span>  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fdea4-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="fdea4-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="fdea4-108">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="fdea4-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="fdea4-109">Получает размер для резервирования в файле сборки, полученные из [функция StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="fdea4-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="fdea4-110">При необходимости получает маркер манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="fdea4-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fdea4-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fdea4-111">Return Value</span></span>  
 <span data-ttu-id="fdea4-112">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="fdea4-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdea4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="fdea4-113">Requirements</span></span>  
 <span data-ttu-id="fdea4-114">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="fdea4-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdea4-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fdea4-115">See Also</span></span>  
 [<span data-ttu-id="fdea4-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="fdea4-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="fdea4-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="fdea4-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="fdea4-118">ALink-интерфейс API</span><span class="sxs-lookup"><span data-stu-id="fdea4-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
