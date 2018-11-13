---
title: Метод ISymUnmanagedBinder::GetReaderForFile
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderForFile
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderForFile
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderForFile method [.NET Framework debugging]
- GetReaderForFile method [.NET Framework debugging]
ms.assetid: 46c06258-831e-47c8-a50a-8650af6b637e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: df6a35dcaebc681aa5463a014d3283c81efea617
ms.sourcegitcommit: 296183dbe35077b5c5e5e74d5fbe7f399bc507ee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2018
ms.locfileid: "50982819"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="fbcd7-102">Метод ISymUnmanagedBinder::GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="fbcd7-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="fbcd7-103">Данный интерфейс метаданных и имя файла, возвращает правильный [ISymUnmanagedReader](isymunmanagedreader-interface.md) интерфейс, который будет считывать символы отладки, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="fbcd7-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="fbcd7-104">Этот метод открывает файл базы данных (PDB) программы только в том случае, если оно находится рядом с исполняемым файлом.</span><span class="sxs-lookup"><span data-stu-id="fbcd7-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="fbcd7-105">Это изменение уже внесено в целях безопасности.</span><span class="sxs-lookup"><span data-stu-id="fbcd7-105">This change has been made for security purposes.</span></span> <span data-ttu-id="fbcd7-106">Если вам требуется более сложный поиск PDB-файл, используйте [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="fbcd7-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbcd7-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fbcd7-107">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbcd7-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="fbcd7-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="fbcd7-109">[in] Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="fbcd7-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="fbcd7-110">[in] Указатель на имя файла.</span><span class="sxs-lookup"><span data-stu-id="fbcd7-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="fbcd7-111">[in] Указатель на пути поиска.</span><span class="sxs-lookup"><span data-stu-id="fbcd7-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="fbcd7-112">[out] Указатель, который имеет значение равное возвращаемому [ISymUnmanagedReader](isymunmanagedreader-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="fbcd7-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbcd7-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="fbcd7-113">Return Value</span></span>  
 <span data-ttu-id="fbcd7-114">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="fbcd7-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbcd7-115">Требования</span><span class="sxs-lookup"><span data-stu-id="fbcd7-115">Requirements</span></span>  
 <span data-ttu-id="fbcd7-116">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fbcd7-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbcd7-117">См. также</span><span class="sxs-lookup"><span data-stu-id="fbcd7-117">See Also</span></span>  
 [<span data-ttu-id="fbcd7-118">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="fbcd7-118">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="fbcd7-119">Метод GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="fbcd7-119">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
