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
ms.openlocfilehash: 321038a148c27086ca499e2f448eb50cb93525ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405516"
---
# <a name="importtypes-method"></a><span data-ttu-id="f071a-102">Метод ImportTypes</span><span class="sxs-lookup"><span data-stu-id="f071a-102">ImportTypes Method</span></span>
<span data-ttu-id="f071a-103">Инициирует импорт типов из каждой области, импортированной посредством [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="f071a-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f071a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f071a-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="f071a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f071a-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f071a-106">Идентификатор сборки для импорта.</span><span class="sxs-lookup"><span data-stu-id="f071a-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f071a-107">Идентификатор файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="f071a-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="f071a-108">Отсчитываемый от нуля область для импорта.</span><span class="sxs-lookup"><span data-stu-id="f071a-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="f071a-109">Получает дескриптор перечислителя для типов в этой области.</span><span class="sxs-lookup"><span data-stu-id="f071a-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="f071a-110">При необходимости получает [IMetaDataImport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="f071a-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="f071a-111">При необходимости получает число типов в указанной области.</span><span class="sxs-lookup"><span data-stu-id="f071a-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f071a-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f071a-112">Return Value</span></span>  
 <span data-ttu-id="f071a-113">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="f071a-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f071a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="f071a-114">Requirements</span></span>  
 <span data-ttu-id="f071a-115">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="f071a-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f071a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="f071a-116">See Also</span></span>  
 [<span data-ttu-id="f071a-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="f071a-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="f071a-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="f071a-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="f071a-119">API ALink</span><span class="sxs-lookup"><span data-stu-id="f071a-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
