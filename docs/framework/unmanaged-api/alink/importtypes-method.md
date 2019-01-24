---
title: Метод ImportTypes
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6591fb4a2b4944dc0d02f70f0f90ffd87e071c47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735010"
---
# <a name="importtypes-method"></a><span data-ttu-id="cc1c2-102">Метод ImportTypes</span><span class="sxs-lookup"><span data-stu-id="cc1c2-102">ImportTypes Method</span></span>
<span data-ttu-id="cc1c2-103">Инициирует импорт типов из каждой области, импортировать с помощью [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="cc1c2-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc1c2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cc1c2-104">Syntax</span></span>  
  
```  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cc1c2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cc1c2-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="cc1c2-106">Идентификатор сборки для импорта.</span><span class="sxs-lookup"><span data-stu-id="cc1c2-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="cc1c2-107">Идентификатор файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="cc1c2-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="cc1c2-108">Отсчитываемый от нуля область для импорта.</span><span class="sxs-lookup"><span data-stu-id="cc1c2-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="cc1c2-109">Получает дескриптор перечислителя для типов в этой области.</span><span class="sxs-lookup"><span data-stu-id="cc1c2-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="cc1c2-110">При необходимости получает [интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="cc1c2-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="cc1c2-111">При необходимости получает число типов в указанной области.</span><span class="sxs-lookup"><span data-stu-id="cc1c2-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc1c2-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cc1c2-112">Return Value</span></span>  
 <span data-ttu-id="cc1c2-113">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="cc1c2-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc1c2-114">Требования</span><span class="sxs-lookup"><span data-stu-id="cc1c2-114">Requirements</span></span>  
 <span data-ttu-id="cc1c2-115">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="cc1c2-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc1c2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="cc1c2-116">See also</span></span>
- [<span data-ttu-id="cc1c2-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="cc1c2-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="cc1c2-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="cc1c2-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="cc1c2-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="cc1c2-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
