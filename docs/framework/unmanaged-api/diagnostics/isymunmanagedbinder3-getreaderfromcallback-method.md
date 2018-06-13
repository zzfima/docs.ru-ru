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
ms.openlocfilehash: 5f44d50f6736e0698fd876eedab78dbf41434af4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426320"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="0a92e-102">Метод ISymUnmanagedBinder3::GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="0a92e-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="0a92e-103">Пользователь может реализовать или указать через обратный вызов, либо `IID_IDiaReadExeAtRVACallback` или `IID_IDiaReadExeAtOffsetCallback` для получения отладочной информации каталога из памяти.</span><span class="sxs-lookup"><span data-stu-id="0a92e-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a92e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0a92e-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0a92e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0a92e-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="0a92e-106">[in] Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="0a92e-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="0a92e-107">[in] Указатель на имя файла.</span><span class="sxs-lookup"><span data-stu-id="0a92e-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="0a92e-108">[in] Указатель на пути поиска.</span><span class="sxs-lookup"><span data-stu-id="0a92e-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="0a92e-109">[in] Значение [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) перечисления, которое указывает политику для использования при выполнении поиска для средства чтения символов.</span><span class="sxs-lookup"><span data-stu-id="0a92e-109">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="0a92e-110">[in] Указатель на функцию обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="0a92e-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="0a92e-111">[out] Указатель, который задается в возвращаемую [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0a92e-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a92e-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0a92e-112">Return Value</span></span>  
 <span data-ttu-id="0a92e-113">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="0a92e-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a92e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0a92e-114">Requirements</span></span>  
 <span data-ttu-id="0a92e-115">**Заголовок:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="0a92e-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a92e-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0a92e-116">See Also</span></span>  
 [<span data-ttu-id="0a92e-117">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="0a92e-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
