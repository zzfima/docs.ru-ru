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
ms.openlocfilehash: 756ba2e71ca2e3e817a0a8b89165bb807368c1f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449329"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a><span data-ttu-id="1f4f2-102">Метод ISymUnmanagedBinder2::GetReaderForFile2</span><span class="sxs-lookup"><span data-stu-id="1f4f2-102">ISymUnmanagedBinder2::GetReaderForFile2 Method</span></span>
<span data-ttu-id="1f4f2-103">При наличии интерфейса метаданных и имени файла возвращает правильный интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) , который будет считывать символы отладки, связанные с модулем.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-103">Given a metadata interface and a file name, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface that will read the debugging symbols associated with the module.</span></span>  
  
 <span data-ttu-id="1f4f2-104">Этот метод обеспечивает более широкий поиск файла базы данных программы (PDB), чем метод [ISymUnmanagedBinder:: getreaderforfile:](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1f4f2-104">This method provides a more extensive search for the program database (PDB) file than the [ISymUnmanagedBinder::GetReaderForFile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f4f2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f4f2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f4f2-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1f4f2-106">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="1f4f2-107">окне Указатель на интерфейс импорта метаданных.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-107">[in] A pointer to the metadata import interface.</span></span>  
  
 `fileName`  
 <span data-ttu-id="1f4f2-108">окне Указатель на имя файла.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-108">[in] A pointer to the file name.</span></span>  
  
 `searchPath`  
 <span data-ttu-id="1f4f2-109">окне Указатель на путь поиска.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-109">[in] A pointer to the search path.</span></span>  
  
 `searchPolicy`  
 <span data-ttu-id="1f4f2-110">окне Значение перечисления [корсимсеарчполициаттрибутес](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) , указывающее политику, используемую при поиске средства чтения символов.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-110">[in] A value of the [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) enumeration that specifies the policy to be used when doing a search for a symbol reader.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="1f4f2-111">заполняет Указатель, которому присваивается возвращаемый интерфейс [ISymUnmanagedReader](isymunmanagedreader-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="1f4f2-111">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f4f2-112">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1f4f2-112">Return Value</span></span>  
 <span data-ttu-id="1f4f2-113">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f4f2-114">Требования</span><span class="sxs-lookup"><span data-stu-id="1f4f2-114">Requirements</span></span>  
 <span data-ttu-id="1f4f2-115">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="1f4f2-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1f4f2-116">Заметки</span><span class="sxs-lookup"><span data-stu-id="1f4f2-116">Remarks</span></span>  
 <span data-ttu-id="1f4f2-117">Эта версия метода может искать PDB-файл в областях, отличных от right рядом с модулем.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-117">This version of the method can search for the PDB file in areas other than right next to the module.</span></span> <span data-ttu-id="1f4f2-118">Политику поиска можно контролировать путем объединения [корсимсеарчполициаттрибутес](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="1f4f2-118">The search policy can be controlled by combining [CorSymSearchPolicyAttributes](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md).</span></span> <span data-ttu-id="1f4f2-119">Например, `AllowReferencePathAccess | AllowSymbolServerAccess` ищет PDB-файл рядом с исполняемым файлом и на сервере символов, но не запрашивает реестр или не использует путь в исполняемом файле.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-119">For example, `AllowReferencePathAccess | AllowSymbolServerAccess` looks for the PDB next to the executable file and on a symbol server, but does not query the registry or use the path in the executable file.</span></span> <span data-ttu-id="1f4f2-120">Если указан параметр `searchPath`, поиск в этих каталогах будет выполняться всегда.</span><span class="sxs-lookup"><span data-stu-id="1f4f2-120">If the `searchPath` parameter is provided, those directories will always be searched.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f4f2-121">См. также</span><span class="sxs-lookup"><span data-stu-id="1f4f2-121">See also</span></span>

- [<span data-ttu-id="1f4f2-122">Интерфейс ISymUnmanagedBinder2</span><span class="sxs-lookup"><span data-stu-id="1f4f2-122">ISymUnmanagedBinder2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [<span data-ttu-id="1f4f2-123">Метод GetReaderForFile</span><span class="sxs-lookup"><span data-stu-id="1f4f2-123">GetReaderForFile Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
