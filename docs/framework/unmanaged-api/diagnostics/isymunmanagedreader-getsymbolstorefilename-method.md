---
title: Метод ISymUnmanagedReader::GetSymbolStoreFileName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymbolStoreFileName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymbolStoreFileName
helpviewer_keywords:
- GetSymbolStoreFileName method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymbolStoreFileName method [.NET Framework debugging]
ms.assetid: c84f4846-9bc8-44a4-9a76-e39106d6d8b2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 50cd6d1e3666dd1f15c1e6a6b4f7dcb931b79d8d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777063"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="d8bac-102">Метод ISymUnmanagedReader::GetSymbolStoreFileName</span><span class="sxs-lookup"><span data-stu-id="d8bac-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="d8bac-103">Предоставляет имя файла на диске в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="d8bac-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8bac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d8bac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8bac-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d8bac-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="d8bac-106">[in] Размер `szName` буфера.</span><span class="sxs-lookup"><span data-stu-id="d8bac-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d8bac-107">[out] Указатель на переменную, которая получает длину имени возвращаемого в `szName`, включая завершающимся нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="d8bac-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="d8bac-108">[out] Указатель на переменную, которая получает имя файла в хранилище символов.</span><span class="sxs-lookup"><span data-stu-id="d8bac-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8bac-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d8bac-109">Return Value</span></span>  
 <span data-ttu-id="d8bac-110">Значение S_OK, если метод выполнен успешно; в противном случае — значение E_FAIL или другим кодом ошибки.</span><span class="sxs-lookup"><span data-stu-id="d8bac-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8bac-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d8bac-111">Requirements</span></span>  
 <span data-ttu-id="d8bac-112">**Заголовок.** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d8bac-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8bac-113">См. также</span><span class="sxs-lookup"><span data-stu-id="d8bac-113">See also</span></span>

- [<span data-ttu-id="d8bac-114">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="d8bac-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
