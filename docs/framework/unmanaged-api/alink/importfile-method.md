---
title: "Метод ImportFile"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b5d4f93336fe19210086c39b8db6d167b3caa222
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="importfile-method"></a><span data-ttu-id="bb69e-102">Метод ImportFile</span><span class="sxs-lookup"><span data-stu-id="bb69e-102">ImportFile Method</span></span>
<span data-ttu-id="bb69e-103">Импортирует сборок и несвязанных модулей.</span><span class="sxs-lookup"><span data-stu-id="bb69e-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb69e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb69e-104">Syntax</span></span>  
  
```  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb69e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb69e-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="bb69e-106">Полное имя файла для импорта.</span><span class="sxs-lookup"><span data-stu-id="bb69e-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="bb69e-107">Необязательное имя файла вывода, можно использовать для переименования файла, он связан в сборку.</span><span class="sxs-lookup"><span data-stu-id="bb69e-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="bb69e-108">Значение TRUE, если используется ImportTypes, в противном случае импорт должно выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="bb69e-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="bb69e-109">Указатель на маркер, в котором будет храниться уникальный идентификатор файла.</span><span class="sxs-lookup"><span data-stu-id="bb69e-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="bb69e-110">Это может быть файл сборки или файл.</span><span class="sxs-lookup"><span data-stu-id="bb69e-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="bb69e-111">Получает указатель на [imetadataassemblyimport-интерфейс](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md).</span><span class="sxs-lookup"><span data-stu-id="bb69e-111">Receives pointer to [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="bb69e-112">Может иметь значение NULL, если файл не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="bb69e-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="bb69e-113">Указатель на число файлов и/или областей, которые были импортированы.</span><span class="sxs-lookup"><span data-stu-id="bb69e-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb69e-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bb69e-114">Return Value</span></span>  
 <span data-ttu-id="bb69e-115">Возвращает значение S_OK, если метод выполнен успешно.</span><span class="sxs-lookup"><span data-stu-id="bb69e-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb69e-116">Требования</span><span class="sxs-lookup"><span data-stu-id="bb69e-116">Requirements</span></span>  
 <span data-ttu-id="bb69e-117">Требуется alink.h</span><span class="sxs-lookup"><span data-stu-id="bb69e-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb69e-118">См. также</span><span class="sxs-lookup"><span data-stu-id="bb69e-118">See Also</span></span>  
 [<span data-ttu-id="bb69e-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="bb69e-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="bb69e-120">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="bb69e-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="bb69e-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="bb69e-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
