---
title: Метод ImportFileEx2
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx2
helpviewer_keywords:
- ImportFileEx2 method
ms.assetid: 02c789fd-16fc-48c6-9619-56e87e2a37ca
topic_type:
- apiref
ms.openlocfilehash: 7e270dbfc63c03e77cb4b0694296e48c2035b8a6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445688"
---
# <a name="importfileex2-method"></a><span data-ttu-id="de2b1-102">Метод ImportFileEx2</span><span class="sxs-lookup"><span data-stu-id="de2b1-102">ImportFileEx2 Method</span></span>
<span data-ttu-id="de2b1-103">Импортирует сборки и непривязанные модули.</span><span class="sxs-lookup"><span data-stu-id="de2b1-103">Imports assemblies and unbound modules.</span></span> <span data-ttu-id="de2b1-104">Этот метод похож на [Метод ImportFile](importfile-method.md), но работает даже в том случае, если импортируемый файл не существует на диске.</span><span class="sxs-lookup"><span data-stu-id="de2b1-104">This method is like [ImportFile Method](importfile-method.md), but works even if the file being imported does not exist on disk.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de2b1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de2b1-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="de2b1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="de2b1-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="de2b1-107">Имя импортируемого файла.</span><span class="sxs-lookup"><span data-stu-id="de2b1-107">Name of file to be imported.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="de2b1-108">Необязательное имя целевого файла.</span><span class="sxs-lookup"><span data-stu-id="de2b1-108">Optional name of target file.</span></span>  
  
 `pAssemblyScopeIn`  
 <span data-ttu-id="de2b1-109">Необязательный интерфейс интерфейса [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) для области импорта.</span><span class="sxs-lookup"><span data-stu-id="de2b1-109">Optional import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="de2b1-110">Если значение равно TRUE, используется ImportTypes, в противном случае импорт должен выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="de2b1-110">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="de2b1-111">Флаги, передаваемые в [метод OpenScope](../metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="de2b1-111">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="de2b1-112">Получает уникальный идентификатор сборки или файла.</span><span class="sxs-lookup"><span data-stu-id="de2b1-112">Receives unique ID for the assembly or file.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="de2b1-113">Получает интерфейс [интерфейса IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) для области импорта сборки.</span><span class="sxs-lookup"><span data-stu-id="de2b1-113">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="de2b1-114">Может иметь значение NULL, если файл не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="de2b1-114">Can be NULL if the file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="de2b1-115">Получает число импортированных файлов и (или) областей.</span><span class="sxs-lookup"><span data-stu-id="de2b1-115">Receives the number of files and/or scopes imported.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de2b1-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="de2b1-116">Return Value</span></span>  
 <span data-ttu-id="de2b1-117">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="de2b1-117">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de2b1-118">Требования</span><span class="sxs-lookup"><span data-stu-id="de2b1-118">Requirements</span></span>  
 <span data-ttu-id="de2b1-119">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="de2b1-119">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de2b1-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="de2b1-120">See also</span></span>

- [<span data-ttu-id="de2b1-121">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="de2b1-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="de2b1-122">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="de2b1-122">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="de2b1-123">API ALink</span><span class="sxs-lookup"><span data-stu-id="de2b1-123">ALink API</span></span>](index.md)
