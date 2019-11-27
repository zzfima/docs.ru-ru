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
ms.openlocfilehash: a0cccc0adfc666cc8e373bc1f89c8f6f97068fde
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449313"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a><span data-ttu-id="3f6f0-102">Метод ISymUnmanagedBinder3::GetReaderFromCallback</span><span class="sxs-lookup"><span data-stu-id="3f6f0-102">ISymUnmanagedBinder3::GetReaderFromCallback Method</span></span>
<span data-ttu-id="3f6f0-103">Позволяет пользователю реализовать или предоставить обратный вызов с помощью обратного вызова либо `IID_IDiaReadExeAtRVACallback`, либо `IID_IDiaReadExeAtOffsetCallback`, чтобы получить сведения о каталоге отладки из памяти.</span><span class="sxs-lookup"><span data-stu-id="3f6f0-103">Allows the user to implement or supply via callback either an `IID_IDiaReadExeAtRVACallback` or `IID_IDiaReadExeAtOffsetCallback` to obtain the debug directory information from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f6f0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3f6f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f6f0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3f6f0-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="3f6f0-106">окне Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="3f6f0-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="3f6f0-107">окне Указатель на имя файла.</span><span class="sxs-lookup"><span data-stu-id="3f6f0-107">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="3f6f0-108">окне Указатель на путь поиска.</span><span class="sxs-lookup"><span data-stu-id="3f6f0-108">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="3f6f0-109">окне Значение перечисления [корсимсеарчполициаттрибутес](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) , указывающее политику, используемую при поиске средства чтения символов.</span><span class="sxs-lookup"><span data-stu-id="3f6f0-109">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `callback`  
 <span data-ttu-id="3f6f0-110">окне Указатель на функцию обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="3f6f0-110">[in] A pointer to the callback function.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="3f6f0-111">заполняет Указатель, которому присваивается возвращаемый интерфейс [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="3f6f0-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f6f0-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="3f6f0-112">Return Value</span></span>  
 <span data-ttu-id="3f6f0-113">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="3f6f0-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f6f0-114">Требования</span><span class="sxs-lookup"><span data-stu-id="3f6f0-114">Requirements</span></span>  
 <span data-ttu-id="3f6f0-115">**Заголовок:** Корсим. idl</span><span class="sxs-lookup"><span data-stu-id="3f6f0-115">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f6f0-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="3f6f0-116">See also</span></span>

- [<span data-ttu-id="3f6f0-117">Интерфейс ISymUnmanagedBinder3</span><span class="sxs-lookup"><span data-stu-id="3f6f0-117">ISymUnmanagedBinder3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
