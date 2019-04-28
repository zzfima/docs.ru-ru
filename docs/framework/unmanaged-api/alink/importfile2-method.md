---
title: Метод ImportFile2
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c6279c790e9b28e5f3bac93d5d0fdd411dd8c0d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61753491"
---
# <a name="importfile2-method"></a><span data-ttu-id="b5048-102">Метод ImportFile2</span><span class="sxs-lookup"><span data-stu-id="b5048-102">ImportFile2 Method</span></span>
<span data-ttu-id="b5048-103">Импортирует сборок и несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="b5048-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="b5048-104">Этот метод аналогичен [метод ImportFile](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), но работает, даже если импортируемого файла не существует на диске.</span><span class="sxs-lookup"><span data-stu-id="b5048-104">This method is like [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5048-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5048-105">Syntax</span></span>  
  
```  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5048-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5048-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="b5048-107">Имя файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="b5048-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="b5048-108">Необязательный выходной имя файла, который может использоваться для переименования файла, так как он связан в сборку.</span><span class="sxs-lookup"><span data-stu-id="b5048-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="b5048-109">Дополнительная область [интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b5048-109">Optional scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="b5048-110">Если значение равно TRUE, используется ImportTypes, в противном случае импорт должен выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="b5048-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="b5048-111">Получает идентификатор для файла или сборки.</span><span class="sxs-lookup"><span data-stu-id="b5048-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="b5048-112">Получает [интерфейс IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="b5048-112">Receives the [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="b5048-113">Значение NULL, если файл не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="b5048-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="b5048-114">Получает найденные файлы и/или импортированные области.</span><span class="sxs-lookup"><span data-stu-id="b5048-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5048-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b5048-115">Return Value</span></span>  
 <span data-ttu-id="b5048-116">Возвращает S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="b5048-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5048-117">Требования</span><span class="sxs-lookup"><span data-stu-id="b5048-117">Requirements</span></span>  
 <span data-ttu-id="b5048-118">Требуется alink.h.</span><span class="sxs-lookup"><span data-stu-id="b5048-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5048-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b5048-119">See also</span></span>

- [<span data-ttu-id="b5048-120">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="b5048-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b5048-121">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="b5048-121">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b5048-122">API ALink</span><span class="sxs-lookup"><span data-stu-id="b5048-122">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
