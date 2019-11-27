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
ms.openlocfilehash: 17f158167d4075783d1aa594fb61cc9e28d30dd7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446981"
---
# <a name="importfile2-method"></a><span data-ttu-id="20358-102">Метод ImportFile2</span><span class="sxs-lookup"><span data-stu-id="20358-102">ImportFile2 Method</span></span>
<span data-ttu-id="20358-103">Импортирует сборки и непривязанные модули.</span><span class="sxs-lookup"><span data-stu-id="20358-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="20358-104">Этот метод похож на [Метод ImportFile](importfile-method.md), но работает даже в том случае, если импортируемый файл не существует на диске.</span><span class="sxs-lookup"><span data-stu-id="20358-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20358-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20358-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="20358-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="20358-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="20358-107">Имя импортируемого файла.</span><span class="sxs-lookup"><span data-stu-id="20358-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="20358-108">Необязательное имя выходного файла, которое можно использовать для переименования файла, так как он связан с сборкой.</span><span class="sxs-lookup"><span data-stu-id="20358-108">Optional output file name that can be used to rename the file as it is linked into the assembly.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="20358-109">Необязательный интерфейс интерфейса [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) с областью действия.</span><span class="sxs-lookup"><span data-stu-id="20358-109">Optional scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="20358-110">Если значение равно TRUE, используется ImportTypes, в противном случае импорт должен выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="20358-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="20358-111">Получает идентификатор для файла или сборки.</span><span class="sxs-lookup"><span data-stu-id="20358-111">Receives the ID for the file or assembly.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="20358-112">Получает интерфейс [интерфейса IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="20358-112">Receives the [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="20358-113">Значение NULL, если файл не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="20358-113">NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="20358-114">Получает найденные файлы и/или импортированные области.</span><span class="sxs-lookup"><span data-stu-id="20358-114">Receives the found of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20358-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="20358-115">Return Value</span></span>  
 <span data-ttu-id="20358-116">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="20358-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20358-117">Требования</span><span class="sxs-lookup"><span data-stu-id="20358-117">Requirements</span></span>  
 <span data-ttu-id="20358-118">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="20358-118">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20358-119">См. также</span><span class="sxs-lookup"><span data-stu-id="20358-119">See also</span></span>

- [<span data-ttu-id="20358-120">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="20358-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="20358-121">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="20358-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="20358-122">API ALink</span><span class="sxs-lookup"><span data-stu-id="20358-122">ALink API</span></span>](index.md)
