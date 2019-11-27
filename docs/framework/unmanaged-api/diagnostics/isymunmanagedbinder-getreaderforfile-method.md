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
ms.openlocfilehash: 94cda16466ea5a3d35a478a2ae80281e9414f719
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449362"
---
# <a name="isymunmanagedbindergetreaderforfile-method"></a><span data-ttu-id="53c98-102">Метод ISymUnmanagedBinder::GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="53c98-102">ISymUnmanagedBinder::GetReaderForFile Method</span></span>
<span data-ttu-id="53c98-103">При наличии интерфейса метаданных и имени файла возвращает правильный интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) , который будет считывать символы отладки, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="53c98-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="53c98-104">Этот метод будет открывать файл базы данных программы (PDB) только в том случае, если он находится рядом с исполняемым файлом.</span><span class="sxs-lookup"><span data-stu-id="53c98-104">This method will open the program database (PDB) file only if it is next to the executable file.</span></span> <span data-ttu-id="53c98-105">Это изменение было внесено в целях безопасности.</span><span class="sxs-lookup"><span data-stu-id="53c98-105">This change has been made for security purposes.</span></span> <span data-ttu-id="53c98-106">Если требуется более широкий поиск PDB-файла, используйте метод [ISymUnmanagedBinder2:: GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="53c98-106">If you need a more extensive search for the PDB file, use the [ISymUnmanagedBinder2::GetReaderForFile2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53c98-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="53c98-107">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [out, retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53c98-108">Параметры</span><span class="sxs-lookup"><span data-stu-id="53c98-108">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="53c98-109">окне Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="53c98-109">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="53c98-110">окне Указатель на имя файла.</span><span class="sxs-lookup"><span data-stu-id="53c98-110">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="53c98-111">окне Указатель на путь поиска.</span><span class="sxs-lookup"><span data-stu-id="53c98-111">[in] A pointer to the search path.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="53c98-112">заполняет Указатель, которому присваивается возвращаемый интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="53c98-112">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53c98-113">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="53c98-113">Return Value</span></span>  
 <span data-ttu-id="53c98-114">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="53c98-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53c98-115">Требования</span><span class="sxs-lookup"><span data-stu-id="53c98-115">Requirements</span></span>  
 <span data-ttu-id="53c98-116">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="53c98-116">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53c98-117">См. также</span><span class="sxs-lookup"><span data-stu-id="53c98-117">See also</span></span>

- [<span data-ttu-id="53c98-118">Интерфейс ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="53c98-118">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [<span data-ttu-id="53c98-119">Метод GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="53c98-119">GetReaderForFile2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)
