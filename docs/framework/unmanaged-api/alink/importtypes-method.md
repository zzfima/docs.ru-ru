---
title: "Метод ImportTypes"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.ImportTypes
api_location: alink.dll
api_type: COM
f1_keywords: ImportTypes
helpviewer_keywords: ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b8fb83d4e3244010550cb21fedbc6c3b1c5d60d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="importtypes-method"></a><span data-ttu-id="580df-102">Метод ImportTypes</span><span class="sxs-lookup"><span data-stu-id="580df-102">ImportTypes Method</span></span>
<span data-ttu-id="580df-103">Инициирует импорт типов из каждой области, импортированной посредством [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="580df-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="580df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="580df-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="580df-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="580df-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="580df-106">Идентификатор сборки для импорта.</span><span class="sxs-lookup"><span data-stu-id="580df-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="580df-107">Идентификатор файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="580df-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="580df-108">Отсчитываемый от нуля область для импорта.</span><span class="sxs-lookup"><span data-stu-id="580df-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="580df-109">Получает дескриптор перечислителя для типов в этой области.</span><span class="sxs-lookup"><span data-stu-id="580df-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="580df-110">При необходимости получает [IMetaDataImport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="580df-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="580df-111">При необходимости получает число типов в указанной области.</span><span class="sxs-lookup"><span data-stu-id="580df-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="580df-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="580df-112">Return Value</span></span>  
 <span data-ttu-id="580df-113">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="580df-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="580df-114">Требования</span><span class="sxs-lookup"><span data-stu-id="580df-114">Requirements</span></span>  
 <span data-ttu-id="580df-115">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="580df-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="580df-116">См. также</span><span class="sxs-lookup"><span data-stu-id="580df-116">See Also</span></span>  
 [<span data-ttu-id="580df-117">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="580df-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="580df-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="580df-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="580df-119">ALink-интерфейс API</span><span class="sxs-lookup"><span data-stu-id="580df-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
