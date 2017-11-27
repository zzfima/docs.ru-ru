---
title: "Метод ImportFileEx"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.ImportFileEx
api_location: alink.dll
api_type: COM
f1_keywords: ImportFileEx
helpviewer_keywords: ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 71a7bc1ba9f23f1c581ca3528752e04003d9857c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="importfileex-method"></a><span data-ttu-id="7b3df-102">Метод ImportFileEx</span><span class="sxs-lookup"><span data-stu-id="7b3df-102">ImportFileEx Method</span></span>
<span data-ttu-id="7b3df-103">Импортирует указанную сборку или Непривязанный модуль.</span><span class="sxs-lookup"><span data-stu-id="7b3df-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b3df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7b3df-104">Syntax</span></span>  
  
```  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b3df-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7b3df-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="7b3df-106">Полное имя файла, из которого требуется импортировать.</span><span class="sxs-lookup"><span data-stu-id="7b3df-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="7b3df-107">Необязательное имя конечного файла.</span><span class="sxs-lookup"><span data-stu-id="7b3df-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="7b3df-108">Значение TRUE, если используется ImportTypes, в противном случае импорт должно выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="7b3df-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="7b3df-109">Флаги для передачи вдоль [метод OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="7b3df-109">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="7b3df-110">Получает идентификатор импортируемого файла.</span><span class="sxs-lookup"><span data-stu-id="7b3df-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="7b3df-111">Получает области импорта сборки [imetadataassemblyimport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="7b3df-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="7b3df-112">Имеет значение NULL, если файл не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="7b3df-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="7b3df-113">Получает число импортированных файлов и/или областей.</span><span class="sxs-lookup"><span data-stu-id="7b3df-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7b3df-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7b3df-114">Return Value</span></span>  
 <span data-ttu-id="7b3df-115">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="7b3df-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b3df-116">Требования</span><span class="sxs-lookup"><span data-stu-id="7b3df-116">Requirements</span></span>  
 <span data-ttu-id="7b3df-117">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="7b3df-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b3df-118">См. также</span><span class="sxs-lookup"><span data-stu-id="7b3df-118">See Also</span></span>  
 [<span data-ttu-id="7b3df-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="7b3df-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="7b3df-120">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="7b3df-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="7b3df-121">ALink-интерфейс API</span><span class="sxs-lookup"><span data-stu-id="7b3df-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
