---
title: "Метод ISymUnmanagedBinder2::GetReaderForFile2"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder2.GetReaderForFile2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d232bfed801a17e1ee47dee7643ae0bf21d338e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="4f87e-102">Метод ISymUnmanagedBinder2::GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="4f87e-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="4f87e-103">Данный интерфейс метаданных и имя файла, возвращает правильную <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> интерфейс, который будет считывать символы отладки, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="4f87e-103">Given a metadata interface and a file name, returns the correct <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="4f87e-104">Этот метод предоставляет расширенный поиск файла базы данных (PDB) программы, чем [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="4f87e-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f87e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f87e-105">Syntax</span></span>  
  
```  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f87e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f87e-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="4f87e-107">[in] Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="4f87e-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="4f87e-108">[in] Указатель на имя файла.</span><span class="sxs-lookup"><span data-stu-id="4f87e-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="4f87e-109">[in] Указатель на пути поиска.</span><span class="sxs-lookup"><span data-stu-id="4f87e-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="4f87e-110">[in] Значение [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) перечисления, которое указывает политику для использования при выполнении поиска для средства чтения символов.</span><span class="sxs-lookup"><span data-stu-id="4f87e-110">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="4f87e-111">[out] Указатель, который задается в возвращаемую <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4f87e-111">[out] A pointer that is set to the returned <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f87e-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="4f87e-112">Return Value</span></span>  
 <span data-ttu-id="4f87e-113">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="4f87e-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f87e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="4f87e-114">Requirements</span></span>  
 <span data-ttu-id="4f87e-115">**Заголовок:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4f87e-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f87e-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f87e-116">Remarks</span></span>  
 <span data-ttu-id="4f87e-117">Эта версия метода можно найти PDB-файл в областях, отличных от рядом с модуля.</span><span class="sxs-lookup"><span data-stu-id="4f87e-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="4f87e-118">Политики поиска можно управлять путем объединения [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="4f87e-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="4f87e-119">Например `AllowReferencePathAccess | AllowSymbolServerAccess` производит поиск PDB рядом с исполняемым файлом и на сервере символов, но не отправить запрос в реестр либо используйте путь в исполняемом файле.</span><span class="sxs-lookup"><span data-stu-id="4f87e-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="4f87e-120">Если `searchPath` параметр указан, всегда найдет эти каталоги.</span><span class="sxs-lookup"><span data-stu-id="4f87e-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f87e-121">См. также</span><span class="sxs-lookup"><span data-stu-id="4f87e-121">See Also</span></span>  
 [<span data-ttu-id="4f87e-122">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="4f87e-122">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 [<span data-ttu-id="4f87e-123">Метод GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="4f87e-123">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
