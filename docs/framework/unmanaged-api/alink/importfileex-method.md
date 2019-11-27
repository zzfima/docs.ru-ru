---
title: Метод ImportFileEx
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
ms.openlocfilehash: bee7db61beb9ed8c00cf584924be690a67d92eac
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446955"
---
# <a name="importfileex-method"></a><span data-ttu-id="49505-102">Метод ImportFileEx</span><span class="sxs-lookup"><span data-stu-id="49505-102">ImportFileEx Method</span></span>
<span data-ttu-id="49505-103">Импортирует указанную сборку или непривязанный модуль.</span><span class="sxs-lookup"><span data-stu-id="49505-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49505-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49505-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="49505-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="49505-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="49505-106">Полное имя файла, из которого необходимо выполнить импорт.</span><span class="sxs-lookup"><span data-stu-id="49505-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="49505-107">Необязательное имя целевого файла.</span><span class="sxs-lookup"><span data-stu-id="49505-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="49505-108">Если значение равно TRUE, используется ImportTypes, в противном случае импорт должен выполняться вручную.</span><span class="sxs-lookup"><span data-stu-id="49505-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="49505-109">Флаги, передаваемые в [метод OpenScope](../metadata/imetadatadispenser-openscope-method.md).</span><span class="sxs-lookup"><span data-stu-id="49505-109">Flags to be passed along to [OpenScope Method](../metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="49505-110">Получает идентификатор импортируемого файла.</span><span class="sxs-lookup"><span data-stu-id="49505-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="49505-111">Получает интерфейс [интерфейса IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) для области импорта сборки.</span><span class="sxs-lookup"><span data-stu-id="49505-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="49505-112">Имеет значение NULL, если файл не является сборкой.</span><span class="sxs-lookup"><span data-stu-id="49505-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="49505-113">Получает число импортированных файлов и (или) областей.</span><span class="sxs-lookup"><span data-stu-id="49505-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49505-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="49505-114">Return Value</span></span>  
 <span data-ttu-id="49505-115">Возвращает S_OK, если метод завершается с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="49505-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49505-116">Требования</span><span class="sxs-lookup"><span data-stu-id="49505-116">Requirements</span></span>  
 <span data-ttu-id="49505-117">Требуется ALink. h.</span><span class="sxs-lookup"><span data-stu-id="49505-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49505-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="49505-118">See also</span></span>

- [<span data-ttu-id="49505-119">Интерфейс IALink2</span><span class="sxs-lookup"><span data-stu-id="49505-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="49505-120">Интерфейс IALink</span><span class="sxs-lookup"><span data-stu-id="49505-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="49505-121">API ALink</span><span class="sxs-lookup"><span data-stu-id="49505-121">ALink API</span></span>](index.md)
