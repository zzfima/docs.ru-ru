---
title: Метод ISymUnmanagedBinder2::GetReaderForFile2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2.GetReaderForFile2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db917820de92b2e347385afc5217c0ca190825cd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776832"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="e7193-102">Метод ISymUnmanagedBinder2::GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="e7193-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="e7193-103">Данный интерфейс метаданных и имя файла, возвращает правильный [ISymUnmanagedReader](isymunmanagedreader-interface.md) интерфейс, который будет считывать символы отладки, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="e7193-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="e7193-104">Этот метод предоставляет расширенный поиск файла базы данных (PDB) программы, чем [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="e7193-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7193-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7193-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7193-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e7193-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="e7193-107">[in] Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="e7193-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="e7193-108">[in] Указатель на имя файла.</span><span class="sxs-lookup"><span data-stu-id="e7193-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="e7193-109">[in] Указатель на пути поиска.</span><span class="sxs-lookup"><span data-stu-id="e7193-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="e7193-110">[in] Значение [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) перечисления, которое указывает политику, используемую при выполнении поиска для средства чтения символов.</span><span class="sxs-lookup"><span data-stu-id="e7193-110">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e7193-111">[out] Указатель, который имеет значение равное возвращаемому [ISymUnmanagedReader](isymunmanagedreader-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e7193-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7193-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e7193-112">Return Value</span></span>  
 <span data-ttu-id="e7193-113">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="e7193-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7193-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e7193-114">Requirements</span></span>  
 <span data-ttu-id="e7193-115">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e7193-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7193-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7193-116">Remarks</span></span>  
 <span data-ttu-id="e7193-117">Эта версия метода можно найти PDB-файл в областях, отличных от рядом с модуля.</span><span class="sxs-lookup"><span data-stu-id="e7193-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="e7193-118">Поиск политики можно управлять путем объединения [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="e7193-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="e7193-119">Например `AllowReferencePathAccess | AllowSymbolServerAccess` производит поиск PDB рядом с исполняемым файлом и с сервера, но не отправки запроса в реестр или использовать путь в исполняемом файле.</span><span class="sxs-lookup"><span data-stu-id="e7193-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="e7193-120">Если `searchPath` параметр указан, всегда найдет эти каталоги.</span><span class="sxs-lookup"><span data-stu-id="e7193-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7193-121">См. также</span><span class="sxs-lookup"><span data-stu-id="e7193-121">See also</span></span>

- [<span data-ttu-id="e7193-122">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="e7193-122">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="e7193-123">Метод GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="e7193-123">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
