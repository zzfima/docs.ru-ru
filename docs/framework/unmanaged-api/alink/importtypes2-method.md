---
title: "Метод ImportTypes2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.ImportTypes2
api_location: alink.dll
api_type: COM
f1_keywords: ImportTypes2
helpviewer_keywords: ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47c49253a1e2839939ef4e671f155e4a44d07529
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="importtypes2-method"></a><span data-ttu-id="daaad-102">Метод ImportTypes2</span><span class="sxs-lookup"><span data-stu-id="daaad-102">ImportTypes2 Method</span></span>
<span data-ttu-id="daaad-103">Инициирует импорт типов.</span><span class="sxs-lookup"><span data-stu-id="daaad-103">Initiates the import of types.</span></span> <span data-ttu-id="daaad-104">Вызовите этот метод, чтобы начать импорт типов из каждой области, импортированной посредством [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span><span class="sxs-lookup"><span data-stu-id="daaad-104">Call this method to begin importing types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daaad-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="daaad-105">Syntax</span></span>  
  
```  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="daaad-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="daaad-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="daaad-107">Идентификатор сборки, в который планируется импортировать.</span><span class="sxs-lookup"><span data-stu-id="daaad-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="daaad-108">Идентификатор файла, из которого требуется импортировать.</span><span class="sxs-lookup"><span data-stu-id="daaad-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="daaad-109">Отсчитываемый от нуля область, из которого требуется импортировать.</span><span class="sxs-lookup"><span data-stu-id="daaad-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="daaad-110">Получает дескриптор перечислителя для типов в заданной области.</span><span class="sxs-lookup"><span data-stu-id="daaad-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="daaad-111">При необходимости получает [IMetaDataImport2-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="daaad-111">Optionally receives [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="daaad-112">При необходимости получает число типов в указанной области.</span><span class="sxs-lookup"><span data-stu-id="daaad-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="daaad-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="daaad-113">Return Value</span></span>  
 <span data-ttu-id="daaad-114">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="daaad-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daaad-115">Требования</span><span class="sxs-lookup"><span data-stu-id="daaad-115">Requirements</span></span>  
 <span data-ttu-id="daaad-116">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="daaad-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daaad-117">См. также</span><span class="sxs-lookup"><span data-stu-id="daaad-117">See Also</span></span>  
 [<span data-ttu-id="daaad-118">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="daaad-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="daaad-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="daaad-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="daaad-120">API ALink</span><span class="sxs-lookup"><span data-stu-id="daaad-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
