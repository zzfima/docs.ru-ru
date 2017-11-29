---
title: "Метод ImportFileEx2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.ImportFileEx2
api_location: alink.dll
api_type: COM
f1_keywords: ImportFileEx2
helpviewer_keywords: ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c2416a630f9bd763d4d4d31170cc606b160bb854
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="importfileex2-method"></a><span data-ttu-id="5179d-102">Метод ImportFileEx2</span><span class="sxs-lookup"><span data-stu-id="5179d-102">ImportFileEx2 Method</span></span>
<span data-ttu-id="5179d-103">Импортирует сборок и несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="5179d-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="5179d-104">Этот метод аналогичен [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), но работает, даже если в импортируемом файле не существует на диске.</span><span class="sxs-lookup"><span data-stu-id="5179d-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5179d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5179d-105">Syntax</span></span>  
  
```  
HRESULT ImportFileEx2(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5179d-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5179d-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="5179d-107">Имя файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="5179d-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="5179d-108">Необязательное имя конечного файла.</span><span class="sxs-lookup"><span data-stu-id="5179d-108">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="5179d-109">Необязательный Импорт области [imetadataassemblyimport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5179d-109">Optional import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="5179d-110">Значение TRUE, если используется ImportTypes, в противном случае импорт должно выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="5179d-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="5179d-111">Флаги для передачи вдоль [метод OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="5179d-111">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="5179d-112">Получает уникальный идентификатор сборки или файла.</span><span class="sxs-lookup"><span data-stu-id="5179d-112">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="5179d-113">Получает области импорта сборки [imetadataassemblyimport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="5179d-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="5179d-114">Может иметь значение NULL, если файл не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="5179d-114">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="5179d-115">Получает число файлов и/или импортированные области.</span><span class="sxs-lookup"><span data-stu-id="5179d-115">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5179d-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5179d-116">Return Value</span></span>  
 <span data-ttu-id="5179d-117">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="5179d-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5179d-118">Требования</span><span class="sxs-lookup"><span data-stu-id="5179d-118">Requirements</span></span>  
 <span data-ttu-id="5179d-119">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="5179d-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5179d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5179d-120">See Also</span></span>  
 [<span data-ttu-id="5179d-121">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="5179d-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="5179d-122">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="5179d-122">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="5179d-123">ALink-интерфейс API</span><span class="sxs-lookup"><span data-stu-id="5179d-123">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
