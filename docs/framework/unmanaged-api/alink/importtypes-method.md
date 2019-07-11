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
ms.openlocfilehash: 9876e3ba5ea67442714c2d00b1901c25e54494f2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741637"
---
# <a name="importtypes-method"></a><span data-ttu-id="1e767-102">Метод ImportTypes</span><span class="sxs-lookup"><span data-stu-id="1e767-102">ImportTypes Method</span></span>
<span data-ttu-id="1e767-103">Инициирует импорт типов из каждой области, импортировать с помощью [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="1e767-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e767-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1e767-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e767-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1e767-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1e767-106">Идентификатор сборки для импорта.</span><span class="sxs-lookup"><span data-stu-id="1e767-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1e767-107">Идентификатор файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="1e767-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="1e767-108">Отсчитываемый от нуля область для импорта.</span><span class="sxs-lookup"><span data-stu-id="1e767-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="1e767-109">Получает дескриптор перечислителя для типов в этой области.</span><span class="sxs-lookup"><span data-stu-id="1e767-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="1e767-110">При необходимости получает [интерфейс IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="1e767-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="1e767-111">При необходимости получает число типов в указанной области.</span><span class="sxs-lookup"><span data-stu-id="1e767-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e767-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1e767-112">Return Value</span></span>  
 <span data-ttu-id="1e767-113">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="1e767-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e767-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1e767-114">Requirements</span></span>  
 <span data-ttu-id="1e767-115">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="1e767-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e767-116">См. также</span><span class="sxs-lookup"><span data-stu-id="1e767-116">See also</span></span>

- [<span data-ttu-id="1e767-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="1e767-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="1e767-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="1e767-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="1e767-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="1e767-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
