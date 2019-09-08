---
title: Метод ImportFile
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f7fee7a91de99e2db69609cbc7c73e22d85d045f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777070"
---
# <a name="importfile-method"></a><span data-ttu-id="f86a1-102">Метод ImportFile</span><span class="sxs-lookup"><span data-stu-id="f86a1-102">ImportFile Method</span></span>
<span data-ttu-id="f86a1-103">Импортирует сборки и непривязанные модули.</span><span class="sxs-lookup"><span data-stu-id="f86a1-103">Imports assemblies and unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f86a1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f86a1-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f86a1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f86a1-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="f86a1-106">Полное имя импортируемого файла.</span><span class="sxs-lookup"><span data-stu-id="f86a1-106">Fully qualified name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="f86a1-107">Необязательное имя выходного файла, которое можно использовать для переименования файла, так как он связан с сборкой.</span><span class="sxs-lookup"><span data-stu-id="f86a1-107">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="f86a1-108">Если значение равно TRUE, используется ImportTypes, в противном случае импорт должен выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="f86a1-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="f86a1-109">Указатель на маркер, где будет храниться уникальный идентификатор файла.</span><span class="sxs-lookup"><span data-stu-id="f86a1-109">Pointer to token where a unique file ID will be stored.</span></span> <span data-ttu-id="f86a1-110">Файл может быть сборкой или файлом.</span><span class="sxs-lookup"><span data-stu-id="f86a1-110">The file can be an assembly or a file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="f86a1-111">Получает указатель на [интерфейс IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f86a1-111">Receives pointer to [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md).</span></span> <span data-ttu-id="f86a1-112">Может иметь значение NULL, если файл не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="f86a1-112">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="f86a1-113">Указатель на число импортированных файлов и (или) областей.</span><span class="sxs-lookup"><span data-stu-id="f86a1-113">Pointer to the count of files and/or scopes that have been imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f86a1-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f86a1-114">Return Value</span></span>  
 <span data-ttu-id="f86a1-115">Если метод завершается с ошибкой, возвращает значение S_OK.</span><span class="sxs-lookup"><span data-stu-id="f86a1-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f86a1-116">Требования</span><span class="sxs-lookup"><span data-stu-id="f86a1-116">Requirements</span></span>  
 <span data-ttu-id="f86a1-117">Требуется ALink. h</span><span class="sxs-lookup"><span data-stu-id="f86a1-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f86a1-118">См. также</span><span class="sxs-lookup"><span data-stu-id="f86a1-118">See also</span></span>

- [<span data-ttu-id="f86a1-119">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="f86a1-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f86a1-120">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="f86a1-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f86a1-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="f86a1-121">ALink API</span></span>](index.md)
