---
title: Метод ISymUnmanagedBinder3::GetReaderFromCallback
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9487cf89d87b5f373302dc49a08c4fabb719e746
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160775"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="060ee-102">Метод ISymUnmanagedBinder3::GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="060ee-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="060ee-103">Пользователь может реализовывать или предоставить с помощью обратного вызова, либо `IID_IDiaReadExeAtRVACallback` или `IID_IDiaReadExeAtOffsetCallback` для получения сведения о каталоге отладки из памяти.</span><span class="sxs-lookup"><span data-stu-id="060ee-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="060ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="060ee-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="060ee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="060ee-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="060ee-106">[in] Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="060ee-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="060ee-107">[in] Указатель на имя файла.</span><span class="sxs-lookup"><span data-stu-id="060ee-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="060ee-108">[in] Указатель на пути поиска.</span><span class="sxs-lookup"><span data-stu-id="060ee-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="060ee-109">[in] Значение [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) перечисления, которое указывает политику, используемую при выполнении поиска для средства чтения символов.</span><span class="sxs-lookup"><span data-stu-id="060ee-109">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="060ee-110">[in] Указатель на функцию обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="060ee-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="060ee-111">[out] Указатель, который имеет значение равное возвращаемому [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="060ee-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="060ee-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="060ee-112">Return Value</span></span>  
 <span data-ttu-id="060ee-113">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="060ee-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="060ee-114">Требования</span><span class="sxs-lookup"><span data-stu-id="060ee-114">Requirements</span></span>  
 <span data-ttu-id="060ee-115">**Заголовок.** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="060ee-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="060ee-116">См. также</span><span class="sxs-lookup"><span data-stu-id="060ee-116">See also</span></span>

- [<span data-ttu-id="060ee-117">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="060ee-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
