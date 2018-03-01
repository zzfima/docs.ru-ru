---
title: "Метод ISymUnmanagedBinder::GetReaderForFile"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9c50bb4ca36043fc2491c9a0615b682c94c422e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="e29f3-102">Метод ISymUnmanagedBinder::GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="e29f3-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="e29f3-103">Данный интерфейс метаданных и имя файла, возвращает правильную <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> структуру, которая будет считывать символы отладки, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="e29f3-103">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> structure that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="e29f3-104">Этот метод открывает файл базы данных (PDB) программы только в том случае, если оно находится рядом с исполняемым файлом.</span><span class="sxs-lookup"><span data-stu-id="e29f3-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="e29f3-105">Это изменение было внесено в целях безопасности.</span><span class="sxs-lookup"><span data-stu-id="e29f3-105">This change has been made for security purposes.</span></span> <span data-ttu-id="e29f3-106">Если требуется более сложная поиск PDB-файл, используйте [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="e29f3-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e29f3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e29f3-107">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e29f3-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="e29f3-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="e29f3-109">[in] Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="e29f3-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="e29f3-110">[in] Указатель на имя файла.</span><span class="sxs-lookup"><span data-stu-id="e29f3-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="e29f3-111">[in] Указатель на пути поиска.</span><span class="sxs-lookup"><span data-stu-id="e29f3-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e29f3-112">[out] Указатель, который задается в возвращаемую <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e29f3-112">[out] A pointer that is set to the returned <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e29f3-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e29f3-113">Return Value</span></span>  
 <span data-ttu-id="e29f3-114">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="e29f3-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e29f3-115">Требования</span><span class="sxs-lookup"><span data-stu-id="e29f3-115">Requirements</span></span>  
 <span data-ttu-id="e29f3-116">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e29f3-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e29f3-117">См. также</span><span class="sxs-lookup"><span data-stu-id="e29f3-117">See Also</span></span>  
 [<span data-ttu-id="e29f3-118">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="e29f3-118">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [<span data-ttu-id="e29f3-119">Метод GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="e29f3-119">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
