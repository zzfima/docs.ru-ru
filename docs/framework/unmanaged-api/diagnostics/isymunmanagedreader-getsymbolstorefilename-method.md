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
ms.openlocfilehash: b3674c4058dba2f6185418b55b35eefb14c312f6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431237"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="b5de7-102">Метод ISymUnmanagedReader::GetSymbolStoreFileName</span><span class="sxs-lookup"><span data-stu-id="b5de7-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="b5de7-103">Предоставляет имя файла на диске для хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="b5de7-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5de7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b5de7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5de7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b5de7-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="b5de7-106">окне Размер буфера `szName`.</span><span class="sxs-lookup"><span data-stu-id="b5de7-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b5de7-107">заполняет Указатель на переменную, которая получает длину имени, возвращаемого в `szName`, включая завершение значения NULL.</span><span class="sxs-lookup"><span data-stu-id="b5de7-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="b5de7-108">заполняет Указатель на переменную, которая получает имя файла хранилища символов.</span><span class="sxs-lookup"><span data-stu-id="b5de7-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b5de7-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b5de7-109">Return Value</span></span>  
 <span data-ttu-id="b5de7-110">S_OK, если метод выполнен. в противном случае E_FAIL или другой код ошибки.</span><span class="sxs-lookup"><span data-stu-id="b5de7-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5de7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b5de7-111">Requirements</span></span>  
 <span data-ttu-id="b5de7-112">**Заголовок:** Корсим. idl, Корсим. h</span><span class="sxs-lookup"><span data-stu-id="b5de7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5de7-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="b5de7-113">See also</span></span>

- [<span data-ttu-id="b5de7-114">Интерфейс ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="b5de7-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
