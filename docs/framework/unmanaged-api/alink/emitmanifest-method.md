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
ms.openlocfilehash: 6df28cd3eaadfe62cd34e20e6e03d5a89e6bb425
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401213"
---
# <a name="emitmanifest-method"></a><span data-ttu-id="0d9b8-102">Метод EmitManifest</span><span class="sxs-lookup"><span data-stu-id="0d9b8-102">EmitManifest Method</span></span>
<span data-ttu-id="0d9b8-103">Выпускает конечный манифест.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-103">Emits the final manifest.</span></span> <span data-ttu-id="0d9b8-104">Этот метод вызывается после импорта все файлы и настройки всех параметров.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-104">Call this method after importing all other files and setting all options.</span></span> <span data-ttu-id="0d9b8-105">Не вызывайте этот метод для несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-105">Do not call this method for unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d9b8-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d9b8-106">Syntax</span></span>  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d9b8-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="0d9b8-107">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0d9b8-108">Идентификатор сборки.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-108">ID of the assembly.</span></span>  
  
 `pdwReserveSize`  
 <span data-ttu-id="0d9b8-109">Получает размер для резервирования в файле сборки, полученные из [функция StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span><span class="sxs-lookup"><span data-stu-id="0d9b8-109">Receives the size to reserve in the assembly file, retrieved from [StrongNameSignatureSize Function](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md).</span></span>  
  
 `ptkManifest`  
 <span data-ttu-id="0d9b8-110">При необходимости получает маркер манифеста сборки.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-110">Optionally receives the assembly manifest token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d9b8-111">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0d9b8-111">Return Value</span></span>  
 <span data-ttu-id="0d9b8-112">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d9b8-113">Требования</span><span class="sxs-lookup"><span data-stu-id="0d9b8-113">Requirements</span></span>  
 <span data-ttu-id="0d9b8-114">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="0d9b8-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d9b8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0d9b8-115">See Also</span></span>  
 [<span data-ttu-id="0d9b8-116">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="0d9b8-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="0d9b8-117">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="0d9b8-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="0d9b8-118">API ALink</span><span class="sxs-lookup"><span data-stu-id="0d9b8-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
