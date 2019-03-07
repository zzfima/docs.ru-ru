---
title: Метод EmitManifest
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28be714a70229b8a4628db2efff0dc2d890e231b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485503"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="ddebb-102">Метод EmitManifest</span><span class="sxs-lookup"><span data-stu-id="ddebb-102">EmitManifest Method</span></span>
<span data-ttu-id="ddebb-103">Выпускает конечный манифест.</span><span class="sxs-lookup"><span data-stu-id="ddebb-103">Emits the final manifest.</span></span> <span data-ttu-id="ddebb-104">Этот метод следует вызывайте после импортирования всех других файлов и настройки всех параметров.</span><span class="sxs-lookup"><span data-stu-id="ddebb-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="ddebb-105">Не вызывайте этот метод для несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="ddebb-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddebb-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ddebb-106">Syntax</span></span>  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddebb-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="ddebb-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ddebb-108">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="ddebb-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="ddebb-109">Получает размер для резервирования в файле сборки, полученные из [функция StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="ddebb-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="ddebb-110">При необходимости получает маркер манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="ddebb-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ddebb-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ddebb-111">Return Value</span></span>  
 <span data-ttu-id="ddebb-112">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="ddebb-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddebb-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ddebb-113">Requirements</span></span>  
 <span data-ttu-id="ddebb-114">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="ddebb-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddebb-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ddebb-115">See also</span></span>
- [<span data-ttu-id="ddebb-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="ddebb-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ddebb-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="ddebb-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ddebb-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="ddebb-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
